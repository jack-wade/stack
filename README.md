# stack

A personal collection of reusable skills, workflows and task playbooks for software development and day-to-day work. This is also a place to try skills, compare their effect on real tasks and keep the versions I enjoy using.

## Skills

| Skill | Purpose | Try it |
| --- | --- | --- |
| [unslop](skills/unslop/SKILL.md) | Plain, natural UK English without AI filler. | [Evaluation prompts](evals/unslop.md) |

## Structure

Each skill lives in its own directory under `skills/`:

```text
skills/
└── skill-name/
    └── SKILL.md
```

Each `SKILL.md` has a name and description in YAML frontmatter, followed by the instructions an agent needs. Keep the instructions independent of any particular harness, editor or provider. Add references, scripts or assets only when they support the skill's work. Keep evaluation prompts and observations separately under `evals/` so the skill does not see the assessment criteria during a trial.

## Using the skills

Skills in this repository are intended to be copied, linked or installed into the agent or development environment where they are needed. Keep each skill focused, portable and free from credentials or machine-specific secrets.

To try `unslop` directly in a session with access to this repo, ask:

```text
Read skills/unslop/SKILL.md and apply it to this response:
[your task or text]
```

Use your harness's own discovery or invocation mechanism if it supports skills. Otherwise, provide the `SKILL.md` contents as instructions alongside your task. The skill itself requires no harness-specific commands or plugins.

Edit [the skill](skills/unslop/SKILL.md) to change the rules. Linked installations follow those edits; copied installations need updating. Keeping a skill here does not automatically activate it in other projects or change global agent settings.

[AGENTS.md](AGENTS.md) sets UK English as the default for responses and original prose while working in this repo. The `unslop` skill carries that preference with it when used elsewhere.

## Experimenting

Start with the [unslop evaluation prompts](evals/unslop.md). Compare the same task in fresh sessions with and without the skill, or before and after a rule change. Keep useful outputs and observations, then adjust rules based on what improves the work. A structurally valid skill still needs real use to show whether it helps.

## Contributing to this collection

1. Create a branch for a new or changed skill.
2. Add or update the relevant `skills/<name>/SKILL.md`.
3. Test the workflow in a real task.
4. Record useful lessons and edge cases under `evals/`.
5. Open a pull request or merge the reviewed change into `main`.
