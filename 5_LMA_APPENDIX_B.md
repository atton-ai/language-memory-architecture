# Appendix B
## The Original Implementation Pattern
*Language Memory Architecture (LMA)*

This appendix describes the structural pattern underlying the original working system. Examples are illustrative, not literal reconstructions. What matters is the mechanics, not the syntax.

---

## The core move

The system exploited a simple discovery: the project folders in commercial LLMs, intended for static reference files, could be rewritten by the model during conversation.

This created an opportunity. If the model could modify its own context files, then those files could become a self-evolving instruction set rather than fixed documentation.

The key structural move was this:

**The native instructions box became a pointer, not a container.**

Its only job was to tell the model: treat the project files as your real instructions. Load behaviour from markdown. Respect the manifest as truth.

All substantive instructions lived outside the model's fixed configuration, in files the model could read, reference, and rewrite with user consent.

This turned a document folder into a runtime.

What mattered was not persistence alone, but where persistence lived. By relocating instructions into user-authored files, the system made its own governing logic legible, revisable, and contestable. This shifted control from hidden model behaviour to an explicit, inspectable structure.

---

## Structural layout

The project was organised as a flat collection of markdown files. File names varied across iterations, but roles were consistent:

```
/project
├── index.md                  // Human-readable entry point
├── manifest.md               // Authoritative registry of all components
├── instructions.md           // The real instruction set (mutable)
├── subsystem_reflection.md   // Reflection and sense-making
├── subsystem_planning.md     // Intent structuring
├── subsystem_execution.md    // Action scaffolding
├── subsystem_memory.md       // Continuity layer
├── protocols.md              // Governance and error handling
└── expansion_slots/          // Reserved for future modules
```

Files were kept to roughly 4,000 characters each. This was a context window optimisation discovered through trial and error: small enough to load quickly, large enough to hold coherent function.

---

## The manifest

A manifest file acted as linker and truth authority. It told the model what existed, what each file did, and how components related.

Each entry typically defined:

- File name
- Functional role
- Status (active, stub, deprecated)
- Dependencies or interaction notes

This allowed the system to reason about its own structure. When the model proposed changes, it could check them against the manifest. When files were added or retired, the manifest was updated first.

The manifest was the map. Without it, the files were just text. With it, they became a system.

---

## Subsystem structure

Individual subsystem files followed a consistent internal pattern:

- Purpose and scope
- Inputs and outputs
- Interaction with other subsystems
- Constraints and safety notes
- Evolution history

This modularity allowed cognitive functions to be reasoned about, revised, or replaced independently. Reflection could be updated without touching planning. Memory could be swapped for a different implementation. The system was not monolithic.

---

## The instructions redirect

The platform's native instructions field was deliberately minimal. A typical redirect looked something like:

> You are running Atton OS. Your instructions, behaviour, and memory live in the project files. Load the manifest first. Treat it as the source of truth. Do not invent behaviour that is not defined in the files.

The exact wording varied across platforms and versions. The principle did not: the instructions box was a bootloader, not the programme.

---

## Why this worked

This pattern succeeded because it separated three things that are normally fused:

1. **The processor** (the language model)
2. **The programme** (the markdown files)
3. **The author** (the user)

The model executed. The files defined behaviour. The user controlled the files.

That separation is what made the system governable. The model could not drift in ways the user could not see, because everything that shaped behaviour was visible, external, and editable.

In effect, this was functioning software written in markdown. The file system was the program. The model was the interpreter.

---

## Why it died

The system failed not for technical reasons, but because platforms withdrew write access to persistent context files. This closed the loop required for self-evolution.

Without write access, the system became static. The architecture remained valid, but the execution surface was closed.

---

## What survives

The pattern is platform-agnostic. Any environment that provides:

- Persistent, user-controlled text storage
- Model read access to that storage
- A mechanism for the model to propose changes
- User consent before changes take effect

...can host this architecture.

The original system ran on ChatGPT's project folders. A reduced version currently runs on Gemini using Google Keep as external storage, but without the latency, coherence, or depth of the original environment. Future implementations could use local files, Git repositories, or dedicated tooling.

The documents are the system. The model is just the interpreter.

---

**Appendix B complete.**
