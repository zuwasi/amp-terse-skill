# User Guide

This guide explains how to use `compressing-amp-output` in daily Amp work.

## Quick Start

Use this as your default thread opener:

```text
Use compressing-amp-output tight for this thread. Default to concise answers and short updates. Expand only for risk, ambiguity, or when I ask why.
```

That gives you the main benefit of token reduction without making replies cryptic.

## Choose a Mode

### Tight

Use `tight` for most work.

- normal English
- short answers
- short progress updates
- enough detail for most coding tasks

Recommended for:

- feature work
- bug fixes
- routine debugging
- most code questions

Starter prompt:

```text
Use compressing-amp-output tight for this thread. Be concise, act first, keep progress updates short, and expand only if the change is risky or subtle.
```

### Dense

Use `dense` when you want maximum compression during high-volume implementation.

- shorter fragments allowed
- symbols like `->` and `=` are OK
- less narration than `tight`

Recommended for:

- repetitive edit/test loops
- bulk cleanup work
- short review findings
- sessions where speed matters more than explanation

Starter prompt:

```text
Use compressing-amp-output dense for this thread. Keep replies extremely concise. Act first, minimize narration, and expand only for irreversible changes, security risk, hidden tradeoffs, or if I ask for detail.
```

## Daily Patterns

### Coding

```text
Use compressing-amp-output tight for this thread. Be concise, act first, keep progress updates short, and expand only if the change is risky or subtle.
```

### Debugging

```text
Use compressing-amp-output tight. Lead with the most likely root cause, include the decisive evidence, and keep explanation brief unless the bug is subtle.
```

### Reviews

```text
Use compressing-amp-output dense. Review this change with findings first, one bullet per issue, include severity and file refs, no summary unless needed.
```

### High-Volume Implementation

```text
Use compressing-amp-output dense for this thread. Maximum signal, minimum words. Short progress updates only. No filler, no restating the task, no broad explanations. Expand only when safety or correctness requires it.
```

## When to Turn It Off

Do not force compression when you need teaching-quality explanation.

Turn it off or ask for expansion when:

- learning a new framework
- comparing multiple designs
- handling security-sensitive changes
- dealing with subtle concurrency, data-loss, or migration risks
- doing deep root-cause analysis

Example:

```text
Keep compressing-amp-output tight, but explain the reasoning fully before making the change.
```

## How It Behaves

The skill tries to compress style without removing meaning.

It keeps:

- exact code
- commands
- file paths
- identifiers
- error messages
- versions
- conditions and caveats that change meaning

It removes or reduces:

- greetings
- praise
- repeated restatement of the task
- transition phrases
- narration that does not help you act

## Good Prompts

```text
Use compressing-amp-output tight. Fix this failing test.
```

```text
Use compressing-amp-output dense. Review this diff and list findings only.
```

```text
Use compressing-amp-output tight. Be terse, but expand if the risk is high.
```

```text
Use compressing-amp-output tight. Keep the answer short unless you need to explain a tradeoff.
```

## Common Mistakes

### Too Dense for Learning

If replies start feeling cryptic, switch back to `tight`.

```text
Use compressing-amp-output tight instead of dense for this thread.
```

### Too Short for Risky Work

If the task is risky, tell Amp to expand before acting.

```text
Use compressing-amp-output tight, but explain any risky or irreversible step before doing it.
```

### Too Verbose Again

If Amp drifts toward long explanations, restate the constraint.

```text
Stay in compressing-amp-output tight. Keep replies short unless I ask for more detail.
```

## Recommended Default

If you want one prompt for most sessions, use this:

```text
Use compressing-amp-output tight for this thread. Default to concise answers and short updates. Expand only for risk, ambiguity, or when I ask why.
```
