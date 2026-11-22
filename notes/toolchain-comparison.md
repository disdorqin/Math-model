# 提取工具链对照实测（2026-11-22）

目的：给精读换掉 pdftotext 单工具，重点看公式、表格、图注的保真度。本机条件：CPU、共享内存约 6 GB、Python 3.12 虚拟环境 `~/workspace/tools/venv`。

## 测试样本

- `papers/O-award/2025-D-2516219.pdf` 第 13 页：公式密集（式 17–21），且带红色水印印章图。
- `papers/O-award/2022-B-2200084.pdf` 第 9 页（图片化的 Algorithm 1 伪代码框）与第 10 页（Table 2 数据表）。
- 地面真值：两页均已渲染成 PNG 人工核对（PyMuPDF，110 dpi）。

## 逐项对照

### 正文与结构

- pymupdf4llm 胜：输出 Markdown，标题、列表、阅读顺序干净，段落不再被版面切断。
- pdftotext：` -layout` 保留双栏/缩进的空间排布，但段落被硬换行打碎，需要人工拼读。

### 表格（2200084 第 10 页，Table 2）

- pymupdf4llm 输出真实 Markdown 表格，五列对齐、数值无误：

```text
|the Name of the Dam|Minimum|Minimum Water Level|Average|Maximum|
|Glen Canyon Dam|65m|110m|142m|216m|
|Hoover Dam|79m|119m|158m|221m|
```

- pdftotext 只给出空格对齐的文本行，表头跨两行错位，进分析前必须手工重排。表格一项 pymupdf4llm 完胜。

### 显示公式（2516219 第 13 页，式 17–21）

- 两个工具都恢复不出 LaTeX，这是底线事实。
- pdftotext `-layout` 保住了公式的二维排布（分子在上、分母在下、求和上下限定位），人读可重构。例如式 (19)：

```text
∆I =  I(Gpre ) − I(Gpost ) / I(Gpre )        (19)
```

（原文为分式，layout 输出中分子分母分行呈现，结构可辨。）

- pymupdf4llm 把公式线性化，且在本页翻车：水印印章被当作图片区，输出了 `<!-- Start of picture text -->` 块，正文被重复三遍、求和符号变替换字符 `�`、式 (19) 被压成一行乱码。`ignore_images=True` 复测无改善。
- 例外：2200084 第 9 页的伪代码框本身是图片，pymupdf4llm 的 picture-text 线性化反而逐行可读（步骤 1–19 顺序完整），pdftotext 的空间排布版超标号堆叠更乱。此类图片框 pymupdf4llm 略优。

### 图注

- pymupdf4llm 胜：图注紧贴图表、作为独立行保留（如 "Table 2: List of Water Level Constraints"），pdftotext 中图注常与正文行粘连。

### 速度

- pdftotext：整页近乎瞬时。
- pymupdf4llm：含加载约 1.3–5.4 秒/页（实测三页），全篇 25 页可接受，不适合全库 229 篇无差别重跑，只按需对精读篇目跑。

## 淘汰记录（如实）

- **docling**：安装失败。依赖的 torch 2.15 wheel（539 MB）在本机网络上 6 次尝试均中断（只下到 187 MB），pip 明确报网络错误。未进入运行实测。
- **marker-pdf**：未安装。它与 docling 同为 torch 依赖，且需另下数 GB 的 Surya 模型权重；在本机已证实的网络条件与共享内存下不具备可行性，按重量淘汰，未做运行实测。
- **MinerU**：未安装。同样依赖 torch 与多模型权重下载（GPU 优先设计），淘汰理由同上，未做运行实测。

## 结论：混合工具链（已固化进 skill `paper_deep_reading`）

1. 全文骨架用 pymupdf4llm 出 Markdown（结构、表格、图注靠它）。
2. 公式页用 pdftotext `-layout` 复提，靠二维排布重构公式。
3. 承重公式必须渲染成图人工核对（地面真值），任何一家的文本提取都不许单独作准。
4. 水印页出现重复段/替换字符时，以 pdftotext 与渲染图为准，并在笔记中标注提取缺陷。
