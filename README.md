# Language Memory Architecture (LMA)

**The missing front-end control plane for human–AI systems.**

---

## What this is

Language Memory Architecture defines a minimal interface layer that allows users to author, inspect, and govern the internal state that shapes how AI systems behave over time.

Current AI systems are powerful but stateless from the user's perspective. Memory, when it exists, is platform-owned and opaque. Users cannot see what shapes the system, change it, or undo it when it drifts.

LMA addresses this by relocating authorship. The platform provides the substrate. The user authors the system. Responsibility follows authorship.

This is not a product specification. It is an architectural pattern: the minimal structures required for human–AI relationships that persist and remain under user control.

---

## Reading order

| Document | Purpose |
|----------|---------|
| [1_SCAFFOLD.md](docs/1_SCAFFOLD.md) | Philosophical framing: why this matters |
| [2_ANCHOR.md](docs/2_ANCHOR.md) | Technical specification: what LMA is |
| [3_SHIELD.md](docs/3_SHIELD.md) | Defensive architecture: why it doesn't collapse |
| [4_APPENDIX_A.md](docs/4_APPENDIX_A.md) | Critics index: quick reference for objections |
| [5_APPENDIX_B.md](docs/5_APPENDIX_B.md) | Implementation pattern: how the original system worked |
| [POSITIONS.md](docs/POSITIONS.md) | Core arguments: the essential claims in brief |

Start with SCAFFOLD if you want to understand the stakes. Start with ANCHOR if you want the technical structure. POSITIONS works as either a hook or a summary.

---

## Background

In late 2024, I discovered that the project folders in commercial LLMs could be hijacked. Despite being intended for static reference, these folders could be rewritten by the model during conversation. I exploited this to build a persistent, self-modifying memory system using structured markdown documents. The model could read from and write to its own governing context, with user consent at each change.

This became a working natural language programming interface. The markdown structure was the control plane. Everything hung on it.

The approach is alluded to in [cognitive-os-discovery](https://github.com/atton-ai/cognitive-os-discovery). The original system was subsequently constrained by platform updates. The architecture worked. The platforms closed it down. I saw little point in documenting the specifics of a system they chose to kill. What mattered was the pattern, not the particulars.

A much constrained version still runs on Gemini using Google Keep as persistent storage. It works as a proof of concept, enough to demonstrate the process, but it's nowhere near as fast or nuanced as the original. It may be worth sharing at some point.

These documents are the philosophical and architectural foundations that emerged from that work. They describe what this layer is and why it matters, not how to build it.

---

## Core thesis

Once AI systems persist across time, someone must own the continuity. Either the platform will, or the user must. There is no third option.

Platforms cannot safely own self-evolving, user-specific cognition without inheriting unbounded liability for its behaviour. This structural constraint explains why memory features remain shallow, why adaptation is hidden, and why users are never given true authorship over the systems they use.

LMA resolves this by defining a front-end control plane (visible, editable, reversible) where the user authors the state that shapes the system. The platform provides capability. The user provides intent. Responsibility follows authorship.

---

## Status

These documents are the foundation. A minimal working example exists. Whether more detailed implementation guidance follows depends on interest and platform constraints.

---

## Author

Atton Conrad  
[atton.ai](https://atton.ai)

---

## License

This work is currently released under a temporary stewardship notice.

You may read, quote, and discuss this material freely.

You may not redistribute, modify, or use this work in commercial systems without explicit permission from the author.

A formal stewardship license will be added in a future revision.

