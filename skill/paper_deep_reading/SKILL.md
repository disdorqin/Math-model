# Paper Deep Reading (Toolchain and Note Template)

Use this skill when deep-reading a paper from the user's library (default: `~/workspace/mcm-library/papers/`) at understanding level: not a method card, but why the paper is built the way it is. It pairs with `paperlab_reading_chain` (the audit methodology); this skill is the operational half: extraction commands, formula handling, and the note template. The side-by-side tool test behind these choices is in `~/workspace/mcm-library/notes/toolchain-comparison.md`.

## Extract with the hybrid toolchain

- Extract the whole paper to Markdown first with pymupdf4llm from the local venv: run `~/workspace/tools/venv/bin/python -c "import pymupdf4llm,sys; open(sys.argv[2],'w').write(pymupdf4llm.to_markdown(sys.argv[1]))" <paper.pdf> <out.md>`. This gives clean headings, reading order, and real Markdown tables, which pdftotext cannot.

- Re-extract every formula-dense page with `pdftotext -f N -l N -layout <paper.pdf> -` and read the formulas from that output: its two-dimensional layout keeps numerators over denominators, so fractions and sums stay reconstructable.

- Render any page that carries a load-bearing formula to an image and read the formula from the image before writing about it: run `~/workspace/tools/venv/bin/python -c "import fitz,sys; d=fitz.open(sys.argv[1]); d[int(sys.argv[2])-1].get_pixmap(dpi=130).save(sys.argv[3])" <paper.pdf> <page> <out.png>`, then read the PNG. Neither text extractor recovers true LaTeX; the rendered page is the ground truth.

- Watch for the watermark trap in this library: many PDFs carry a diagonal stamp image, and pymupdf4llm then emits a duplicated, garbled picture-text block around it. When a passage repeats or fills with replacement characters, trust the pdftotext layout output and the rendered page, and note the defect in the reading note.

- State the extraction limits in the note whenever they bind: which pages or formulas could only be read from a rendered image, and which conclusions are provisional because of it.

## Read in passes, slowest first where it matters

- Name the reading mode before starting (triage, deep read, review, implement, or teach) and finish one mode before switching.

- Give the paper one full pass over the Markdown for structure and argument, then a second slow pass over the model and experiment sections with the formula toolchain above.

- Keep three voices separate in the note: what the authors claim, your judgment with its reason, and what the paper does not say.

## Write the note in the six-part template

- Restated problem: what the paper quietly redefines the problem to be, underneath the surface statement.

- Method rationale chain: why this combination of methods, what quantity crosses each interface between components, and what breaks if one component is swapped out.

- Load-bearing formulas: pick the two to four formulas the paper stands on, state each in words and symbols, and mark each as verified against the rendered page or as read from extraction only.

- Experimental proof power: which comparison, perturbation, or closing argument actually carries the conclusion, which step is decorative, and which experiment is missing.

- Weaknesses: where a reviewer would push, including assumptions with no justification and numbers that appear without a source.

- Transferable insight: one concrete sentence on what to carry into the user's own paper or model, with the source paper's team number attached.

- Save deep-read notes to `~/workspace/mcm-library/notes/deep-reads.md` (append, one headed section per paper) unless the user names another destination, and fold durable lessons into the topic guides under `~/workspace/mcm-library/style/` rather than leaving them only in the note.
