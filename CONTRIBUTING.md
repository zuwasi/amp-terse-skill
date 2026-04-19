# Contributing

Thanks for contributing.

## Scope

This repo is intentionally small.

Good contributions:

- better default prompt wording
- clearer documentation
- improved examples for coding, debugging, and review workflows
- tighter rules that reduce verbosity without removing meaning

Avoid:

- turning the skill into meme caveman grammar
- adding speculative modes or complex tooling
- expanding the skill in ways that make it verbose by default

## Repo Structure

- [`compressing-amp-output/SKILL.md`](compressing-amp-output/SKILL.md) contains the skill logic
- [`README.md`](README.md) is the public landing page
- [`USER_GUIDE.md`](USER_GUIDE.md) explains daily usage patterns

## Editing Guidelines

- Preserve meaning over maximum compression.
- Keep examples realistic and short.
- Prefer the smallest correct change.
- Keep the skill readable in plain Markdown.
- Do not add external dependencies for docs or packaging.

## How To Test Changes

1. Copy `compressing-amp-output` into a workspace `.agents/skills/` directory.
2. Start a new Amp thread.
3. Try both modes:
   - `Use compressing-amp-output tight for this thread.`
   - `Use compressing-amp-output dense for this thread.`
4. Check that responses stay:
   - concise
   - readable
   - accurate
   - safe when risk or ambiguity is present

## Pull Requests

Include:

- what changed
- why it improves the skill
- one or two example prompts showing the benefit

If you change behavior, update both [`README.md`](README.md) and [`USER_GUIDE.md`](USER_GUIDE.md) when needed.
