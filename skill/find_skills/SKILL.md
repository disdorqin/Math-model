# Find Skills (Discover and Vet Agent Skills)

Use this skill when the user asks how to do something an installable skill might already cover, asks you to find a skill for a task, or wants to extend what you can do. Adapted from the open-source `find-skills` skill by Vercel Labs (MIT), source: https://github.com/vercel-labs/skills/blob/main/skills/find-skills/SKILL.md — the discovery order and quality checks come from that skill; the install target and the governance rules are localized to this workspace.

## Search in this order

- Name the capability gap first in one sentence: the task, the input, and the output a good skill would produce.

- Check the skills.sh leaderboard (https://skills.sh/) before searching, because it ranks skills by installs and surfaces the battle-tested options first.

- Search with the Skills CLI: run `npx skills find [query]` with a specific keyword, and add `--owner <owner>` when a publisher is known. Popular sources include `vercel-labs/agent-skills` and `ComposioHQ/awesome-claude-skills`.

- When the CLI and the leaderboard miss, search GitHub and the awesome-agent-skills collections on the web for the task's keywords plus SKILL.md.

## Vet before you recommend

- Never recommend a skill from search results alone. Read its SKILL.md or README and confirm it contains a real workflow, not a stub or a landing page.

- Check three quality signals: install count on skills.sh, whether the publisher is a known source, and the repository's GitHub stars. Treat anything under roughly 100 installs or stars with caution and say so.

- Present each surviving option with what it does, its install count and source, and its install command or page link, then let the user pick.

## Install under this workspace's governance

- Install the chosen skill into `~/workspace/custom-skills/<skill_name>/` as a `skill.yaml` plus `SKILL.md` pair in the local template format, adapting the wording when needed and noting the source link inside the SKILL.md. The upstream route is `npx skills add <owner/repo@skill> -g -y`; use it only when the user wants the skill in that ecosystem's own location instead.

- Keep at most one or two skills per function. When a new find overlaps an installed custom skill, compare them head to head, keep the better one, remove the weaker one, and tell the user what was replaced.

- When no skill passes vetting, say so plainly and offer to write a local skill from the task instead of installing a shell.
