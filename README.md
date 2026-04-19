![license: MIT](https://img.shields.io/badge/license-MIT-green.svg)
![amp skill](https://img.shields.io/badge/amp-skill-blue.svg)
![modes](https://img.shields.io/badge/modes-tight%20%7C%20dense-orange.svg)
![status](https://img.shields.io/badge/status-ready-brightgreen.svg)

# Amp Terse Skill

Lower tokens. Keep meaning.

`compressing-amp-output` is an Amp skill for lower-token, lower-fluff coding sessions without full caveman-style grammar.

It is designed for people who want:

- shorter progress updates
- direct answers
- less narration during implementation work
- readable debugging and review output

## Why This Exists

Most token-saving prompt styles over-compress the writing and start damaging readability.

This repo takes a narrower approach:

- remove fluff
- keep exact technical meaning
- stay readable during coding, debugging, and review
- expand only when safety or subtle reasoning requires it

## What It Does

The skill changes response style, not reasoning quality.

- `tight` mode keeps normal English and trims filler.
- `dense` mode compresses harder, but stays readable.
- The skill expands automatically when safety, ambiguity, or subtle reasoning matters.

## Before And After

### Normal Verbose Style

```text
Sure, I’d be happy to help. The issue is most likely caused by a stale cache key in the auth middleware, which means the token refresh path is reusing the wrong entry. I recommend updating the key builder and then verifying both login and refresh flows.
```

### Tight Mode

```text
Root cause is the stale cache key in auth middleware. Update the key builder, then verify login and token refresh.
```

### Dense Mode

```text
Root cause = stale auth cache key. Fix key builder. Verify login + refresh.
```

## Quick Start

Default thread opener:

```text
Use compressing-amp-output tight for this thread. Default to concise answers and short updates. Expand only for risk, ambiguity, or when I ask why.
```

## Install Snippets

Copy the skill folder into `.agents/skills/` in the workspace where you want to use it.

### PowerShell

```powershell
New-Item -ItemType Directory -Force .agents\skills | Out-Null
Copy-Item -Recurse -Force .\compressing-amp-output .\.agents\skills\
```

### Bash

```bash
mkdir -p .agents/skills
cp -R ./compressing-amp-output ./.agents/skills/
```

## Repository Layout

- [`compressing-amp-output/SKILL.md`](compressing-amp-output/SKILL.md) - the skill itself
- [`USER_GUIDE.md`](USER_GUIDE.md) - daily workflow and examples
- [`CONTRIBUTING.md`](CONTRIBUTING.md) - contribution workflow
- [`LICENSE`](LICENSE) - MIT license
- [`PUBLISHING.md`](PUBLISHING.md) - GitHub publish steps and release notes
- [`REPO_METADATA.md`](REPO_METADATA.md) - copy-ready repo description and tagline

## Install

Amp discovers skills from `.agents/skills/` inside a workspace.

To install this skill into a workspace:

1. Copy the `compressing-amp-output` folder into `.agents/skills/`
2. Start a new Amp thread, or ask Amp to use the skill in the current thread

Target path:

```text
.agents/skills/compressing-amp-output/SKILL.md
```

If you are publishing this repo, the usual workflow is:

1. Clone or copy the repo
2. Copy `compressing-amp-output` into your target workspace `.agents/skills/`
3. Start a new Amp thread and invoke the skill

For publish-ready GitHub commands and metadata, see [`PUBLISHING.md`](PUBLISHING.md) and [`REPO_METADATA.md`](REPO_METADATA.md).

## Use

Examples:

```text
Use compressing-amp-output tight for this thread.
```

```text
Use compressing-amp-output dense for this task.
```

```text
Use compressing-amp-output tight. Expand only for risk, ambiguity, or if I ask why.
```

## Example Prompts

Coding:

```text
Use compressing-amp-output tight for this thread. Be concise, act first, keep progress updates short, and expand only if the change is risky or subtle.
```

Debugging:

```text
Use compressing-amp-output tight. Lead with the most likely root cause, include the decisive evidence, and keep explanation brief unless the bug is subtle.
```

Review:

```text
Use compressing-amp-output dense. Review this change with findings first, one bullet per issue, include severity and file refs, no summary unless needed.
```

## Best Use Cases

- implementation-heavy sessions
- repetitive fix/test loops
- debugging when you want the likely cause fast
- code review when you want findings first

## Less Ideal Use Cases

- teaching or onboarding
- architecture exploration
- subtle root-cause analysis where the explanation matters
- security-sensitive tasks that need explicit reasoning

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Design Goal

Write like a senior engineer in a hurry: calm, exact, brief.
