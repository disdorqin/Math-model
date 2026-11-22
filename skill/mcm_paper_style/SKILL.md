# MCM/ICM Paper Style (O-Award Learned)

Use this skill when drafting, revising, or reviewing an MCM or ICM paper for the user. The full evidence base lives in `~/workspace/mcm-library/` (72 downloaded O-Award papers, per-paper reading cards in `notes/`, and the rolling style guide in `style/style-guide.md`). Read the style guide before drafting and update it after each new reading pass.

## Decompose the problem into a chain

- Break the problem into a chain of sub-steps where each step's output is exactly the next step's input, and name the quantity that passes across each interface.

- Prefer simple, standard methods combined cleanly over one complex model, and put the complexity in the interfaces rather than in the models.

- Use one of four interface patterns to join sub-models: quantity transfer, calibration from measured data, a shared variable system across models, or distribution transfer.

- Keep evaluation models out of the solver: let scoring and ranking models judge results, not drive the optimization.

- Name and brand the overall model and each stage, and mirror the stages one to one in the Summary.

## Write the Summary as compressed logic

- Open with one context sentence that states the system and the tension, never with a method.

- Give each sub-problem its own block that starts with a task verb, states the named method in one clause, and ends with a headline number.

- Close with a quantified robustness sentence, then add a keywords line that names the methods.

- Report results as numbers or intervals with a benchmark, and rank recommendations when the problem asks for them.

## Justify assumptions and validate twice

- Write each load-bearing assumption as a short argument with a reason, a therefore-clause that softens it, or a later test, and never leave the most load-bearing assumption as a bare list item.

- Run two kinds of validation: a perturbation or scenario test (Monte Carlo draws, node or edge deletion, noise injection) and a sensitivity analysis that attaches a number or a bound to every claim.

- Restrict headline sensitivity claims to parameters a decision maker can actually move.

- Use ablation runs to prove a mechanism is necessary: remove one component at a time and report the change.

- State weaknesses, rejected models, and null results in the paper and, when they matter, in the Summary itself.

## Design figures as part of the argument

- Place a framework flowchart before the equations, usually by page four, and keep each flowchart box to eight words or fewer with text at least 70 percent of body size.

- Keep one palette across the whole paper: one main color for the primary structure, red reserved only for critical or failed elements, one color for success or repaired states, and grey for background geography or context.

- Make the key solution figure carry the argument: highlight critical edges or nodes in red, print headline counts or budgets on the figure itself, and end its caption with a reading instruction that tells the reader what to do with the figure.

- Write short captions of five to twelve words for ordinary figures and long captions only for key solution figures.

- Group small multiples to create analytical depth, print values at bar ends, and avoid 3D charts unless the data is truly three-dimensional.

- Give result sections finding-style headings rather than method-style headings.

## Check the draft against the library

- Compare the draft's figure set, Summary, and sensitivity section against the frequency findings in the style guide before calling it done.

- Pull the library papers that use a needed chart type or method and re-read those pages before drawing that figure or writing that section.

- Record each new reading pass in `~/workspace/mcm-library/notes/` and fold new findings into the style guide with their source paper numbers.
