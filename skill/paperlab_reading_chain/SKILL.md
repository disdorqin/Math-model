# PaperLab Reading Chain (Triage to Micro)

Use this skill when a paper deserves more than a skim and you need a defensible, source-verified analysis: what it changes versus prior work, whether its equations hold together, and whether its experiments carry its claims. Adapted from the open-source `paper` skill in m0NSYuke/PaperLab (MIT), source: https://github.com/m0NSYuke/PaperLab/blob/main/.agents/skills/paper/SKILL.md — the reading chain, the equation-priority rule, and the audit steps come from that skill; its PaperLab backend, JSON schema, and publishing machinery are dropped, and the wording is rewritten for this workspace.

## Run the chain in order, macro before micro

- Do the triage pass first: read the abstract, the overview figure, the contribution list, the main results table, and the conclusion, then write down the problem, the core change, and the headline result with the protocol that produced it.

- Set a depth (deep, selective, or skim) after triage and say why. Depth decides how far down the chain you go; it never relaxes the evidence rules.

- In the macro step, name the direct predecessors the paper builds on, and for each distinctive component write one delta row: how prior work does it, what this paper changes, and which ablation or controlled comparison shows the change matters. Mark a component load-bearing only when such evidence exists and you can cite it; otherwise mark it untested.

- In the micro step, give every important equation a priority of derive, understand, or skip. Work each derive-priority derivation completely, step by step, and label any step you supply yourself as teaching, not as the authors' text.

- In the experiment audit step, write one row per central claim: which experiments carry it, how strongly, whether baselines share data, steps, and tuning budget, and which experiment is missing.

- In the limits step, keep three groups visibly apart: what the authors acknowledge, what a reviewer would question, and open questions that matter for the reader's purpose.

## Trace every number to its page

- Put every important factual assertion in a claim with its evidence, and tag missing evidence explicitly instead of smoothing it over.

- Before finishing, run a consistency pass: every number in your triage, deltas, and audit must already appear in a claim, an experiment record, or a verified quote, and the same quantity must carry the same value and unit everywhere.

- Verify significant equations and every comparison number against the rendered PDF pages, because extraction flattens formulas and can silently move a number.

- Never bypass a failed check by downgrading evidence or deleting a number's source. Correct the analysis, or report the evidence limitation honestly.

- Separate paper facts, your interpretation, external background, and uncertainty in the output, and state the extraction tool's limits when they bind (for example a formula that only survives as a rendered image).
