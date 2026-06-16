# glassbox

A [Claude Code](https://claude.com/claude-code) skill that captures one transferable lesson:

> **Don't *describe* an invisible system. Build a glass box of it.**

When someone wants to *understand* a mechanism they can't see — what's happening on the wire, inside an algorithm, between services, across threads — prose and static diagrams are a black box: they ask the learner to take your word for it. A glass box is the opposite: a small, transparent, **runnable** artifact where the **real** mechanism happens in front of them, animated, and they can poke it, break it, slow it down, and read the source that drives it.

The non-negotiable rule: **every pixel is backed by the real thing.** The instant any part is faked, the artifact stops teaching and starts lying.

## The seven pillars

1. **Real, not faked** — drive every animation/number from genuine events of the actual mechanism running.
2. **Make the invisible visible** — a living diagram: actors = nodes, channels = edges, moving data = animated packets. The motion *is* the explanation.
3. **One view per actor** — a log/terminal/panel per participant, so all perspectives are visible at once.
4. **Show the raw truth** — the literal bytes/state next to the pretty view, with an honest note when something is reconstructed.
5. **Let them drive it — including failure** — controls to trigger, pause, **slow down**, inject, and *break* it.
6. **Narrate it** — live plain-English narration reacting to real events, plus a story/metaphor per view.
7. **Zero friction, fully transparent** — zero-dependency, zero-build, one command, source readable top to bottom.

Plus: multiple concrete scenarios on one engine.

## Install

Drop it into your personal skills directory:

```bash
git clone https://github.com/oxfern/glassbox ~/.claude/skills/glassbox
```

Then in Claude Code it auto-triggers on requests like *"show me exactly what X does"*, *"make it alive"*, or *"build an interactive explainer of X"* — or invoke it directly with `/glassbox`.

## What it looks like in practice

The skill was distilled from a reference build: a live, zero-dependency explainer of Server-Sent Events — an animated `producer → server → client` diagram with a terminal per party, raw-wire view, drop/reconnect/resume controls, live narration, and four scenarios. The point isn't SSE; it's the *shape*. Apply the same shape to any invisible mechanism.

See [`SKILL.md`](./SKILL.md) for the full method.
