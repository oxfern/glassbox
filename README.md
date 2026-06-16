# glassbox

**Don't *describe* an invisible system. Build a glass box of it.**

A method for making any invisible or abstract mechanism genuinely understandable — by turning it into a small, transparent, **runnable** artifact where the *real* thing happens in front of you: animated, pokeable, and readable all the way down to the source.

It's packaged as an installable skill, but the idea isn't about any one tool — and it isn't even about code. It's a way of teaching anything you can't directly see: a network protocol, an algorithm, a data structure, a distributed-systems handshake, a memory model, a state machine. A person can follow it. Any AI agent can follow it. It's just a method.

> The one non-negotiable rule: **every pixel is backed by the real thing.** The animation is driven by the actual mechanism running, and the source is readable enough to confirm it. The instant any part is faked, the artifact stops teaching and starts lying.

## The seven pillars

1. **Real, not faked** — drive every animation/number from genuine events of the actual mechanism running.
2. **Make the invisible visible** — a living diagram: actors = nodes, channels = edges, moving data = animated packets. The motion *is* the explanation.
3. **One view per actor** — a log/terminal/panel per participant, so all perspectives are visible at once.
4. **Show the raw truth** — the literal bytes/state next to the pretty view, with an honest note when something is reconstructed.
5. **Let them drive it — including failure** — controls to trigger, pause, **slow down**, inject, and *break* it.
6. **Narrate it** — live plain-English narration reacting to real events, plus a story/metaphor per view.
7. **Zero friction, fully transparent** — zero-dependency, zero-build, one command, source readable top to bottom.

Plus: multiple concrete scenarios on one engine.

## Use it however you like

- **As a way of thinking / a checklist.** Next time you have to explain something invisible, run the seven pillars instead of reaching for slides and hand-waving.
- **As a prompt for any AI agent.** Hand the method (or [`SKILL.md`](./SKILL.md)) to any capable model and ask it to build a glass box of your concept. Nothing here is tool-specific.
- **As an installable skill.** It drops into whatever coding agent or editor you use:
  ```bash
  npx skills add oxfern/glassbox
  ```

## Reference build

The method was distilled from a real one: a live, zero-dependency explainer of Server-Sent Events — an animated `producer → server → client` diagram with a terminal per party, a raw-wire view, drop/reconnect/resume controls, live narration, and four scenarios. The point was never SSE; it was the *shape*. Apply the same shape to any invisible mechanism.

See [`SKILL.md`](./SKILL.md) for the full method.
