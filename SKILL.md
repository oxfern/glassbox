---
name: glassbox
description: |
  Turn an invisible or abstract system into a "glass box" — a small, transparent,
  runnable artifact that makes the REAL mechanism visible, live and pokeable
  (animated actor diagram + per-actor terminals + raw-truth view + interactive
  controls + live narration) instead of explaining it in prose or static diagrams.
  Use when the user wants to genuinely SEE or understand how something works — a
  protocol, algorithm, data structure, concurrency/distributed-systems concept,
  network/auth handshake, state machine, rendering pipeline, GC, compiler pass,
  and so on. Triggers on "show me exactly what X does", "make it alive",
  "visualize the data flowing", "build an interactive demo/explainer of X", or
  any request to understand a mechanism that words alone won't land.
version: 1.0.0
user_invocable: true
---

# glassbox

**Don't describe an invisible system. Build a glass box of it.**

When someone wants to *understand* a mechanism they can't see — what's happening on the wire, inside an algorithm, between services, across threads — prose and static diagrams are a black box: they ask the learner to take your word for it. A glass box is the opposite. It's a small, transparent, **runnable** artifact where the **real** mechanism happens in front of them, animated, and they can poke it, break it, slow it down, and read the source that drives it.

The non-negotiable rule: **every pixel is backed by the real thing.** The animation is driven by genuine events from the actual mechanism running, and the source is readable enough that the learner can open it and see the real thing in plain code. The moment any part is faked, the artifact stops teaching and starts lying.

This is the method, not a topic. It was distilled from a real build — a live, zero-dependency explainer of Server-Sent Events (an animated producer → server → client diagram, a terminal per party, a raw-wire view, drop/reconnect controls, narration, several scenarios). Study its *shape*, never copy its subject.

## The seven pillars (the recipe)

1. **Real, not faked.** Run the genuine mechanism — a real server, a real implementation of the algorithm, real state transitions — and drive every animation, number, and log line from its actual events. If it genuinely cannot run locally, implement the *actual* logic faithfully and clearly label what is simulated and what is literal. Never hardcode an animation that isn't tied to a real event.

2. **Make the invisible visible — animate the flow.** Render the system as a *living* diagram: actors are nodes, channels/relationships are edges, and the things that move (messages, packets, tokens, state, pointers) are animated along those edges in real time. The motion *is* the explanation. Trigger it on a deliberate user action ("GO") so cause and effect are felt, not just observed.

3. **One view per actor.** Give each participant its own log / terminal / panel so the learner sees every perspective simultaneously and watches how they interleave — the "what is each party doing *right now*" view. Seeing the same moment from N sides is where the mental model forms.

4. **Show the raw truth.** Next to the pretty view, expose the literal underlying representation — the wire bytes, the raw state object, the actual instructions, the exact frame. Ground the abstraction in what's really there. When you must reconstruct rather than capture the literal bytes/state, say so honestly in the UI.

5. **Let them drive it — including failure.** Controls to trigger, pause, **slow down (a speed control is essential — let it crawl)**, inject input, and *deliberately break it* (disconnect, drop, timeout, error, corrupt). The edge cases and the recovery are usually the real lesson, and a learner who can cause them owns the concept.

6. **Narrate it.** A live narrator line that reacts to real events in plain English as they happen ("you just X — notice the server did Y, *without* a new request"), plus a short story or metaphor per view to frame it. Teach in the moment, in human language. (Apply this by default — it's a standing preference.)

7. **Zero friction, fully transparent.** Zero dependencies, zero build, one command to run, source readable top-to-bottom. No bundlers or heavy frameworks hiding the very mechanism you're teaching. The learner should be able to clone, run instantly, and read the whole thing.

**Plus — multiple concrete scenarios on one engine.** Build the mechanism once, then show it through several relatable examples (each isolated, e.g. its own page/tab/mode). Different framings make the abstract concept click for different people; the shared engine keeps it honest.

## Workflow when invoked

1. **Name the target.** What invisible mechanism is this, and what specific "aha" is the learner missing? Write that down — everything serves it.
2. **Find the cast.** Identify the actors (→ nodes) and exactly what moves between them (→ animated packets). That's your diagram.
3. **Pick the lightest stack that runs instantly and keeps the mechanism in readable source.** Default: a zero-dependency local server + vanilla HTML/CSS/JS with an SVG diagram. But match the domain — sometimes a single HTML file, a CLI with a TUI, or a notebook is the right glass box. Avoid anything that needs a build step.
4. **Build in order:** living diagram → per-actor panels → raw-truth view → interactive controls (including failure modes) → live narration → multiple scenarios.
5. **Verify against the real thing.** Drive the actual artifact (e.g. a headless browser) and check the underlying wire/state, not just that it renders. Exercise the failure paths. Capture evidence.

## Anti-patterns (these kill a glass box)

- Faked or hardcoded animations not tied to real events.
- A static diagram or a wall of prose dressed up as "interactive."
- Hiding the mechanism behind a build step or a heavyweight framework.
- Autoplay with no controls, and no way to trigger failures.
- Happy path only — no raw/ground-truth view, no edge cases, no recovery.
- One canned example where several framings would land it.

## North star

A great glass box is one a curious person opens, clicks **GO**, watches the real thing come alive, slows it down, breaks it on purpose, reads the narrator, then opens the source and says "oh — *that's* all it is." Build that.
