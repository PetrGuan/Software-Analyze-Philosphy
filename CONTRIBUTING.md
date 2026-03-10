# Contributing

Thanks for helping improve Software Analysis Mindsets.

## Workflow

1. Fork the repository.
2. Create a feature branch from `main`.
3. Make focused changes with clear commits.
4. Open a pull request against `main`.

Example:

```bash
git clone https://github.com/<your-username>/Software-Analyze-Philosphy.git
cd Software-Analyze-Philosphy
git checkout -b feat/add-lovelace-mindset
```

## What to Contribute

- Add new analysis mindsets under the correct topic folder (`architecture/`, `debugging/`, `performance/`, `strategy/`, `testing/`).
- Improve existing mindset files for clarity, accuracy, and practical usefulness.
- Fix broken links, formatting issues, and inconsistencies between command files and docs.

## Content Guidelines

- Keep writing concrete and actionable.
- Use examples tied to real engineering scenarios.
- Keep terminology consistent with existing mindset files.
- Prefer small, reviewable pull requests over large rewrites.

## Claude Code Command File Format

Command files in `.claude/commands/*.md` should follow this structure:

```md
---
description: "Short explanation of when to use this command"
argument-hint: "[file, function, or module to analyze]"
---

# Title

Instruction content...
```

Recommended conventions:

- Include YAML frontmatter at the top.
- Keep `description` clear about intent and use-case.
- Keep `argument-hint` concise and concrete.
- Provide step-by-step analysis instructions.
- End with a deterministic report template.

## Pull Request Expectations

Before opening a PR, confirm:

- Markdown renders correctly.
- Internal links resolve.
- Added or updated mindset files are reflected in `README.md` when relevant.
- CI checks pass.

## Reporting Issues

Use GitHub issue templates for:

- Bug reports (broken links, formatting, or command behavior)
- New mindset proposals

## Code of Conduct

By participating, you agree to follow `CODE_OF_CONDUCT.md`.
