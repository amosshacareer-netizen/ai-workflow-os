# Harness Engineering and Context Engineering

This project is best understood as a small AI harness around general-purpose models.

The model is powerful, but the useful product is the system around it: the skill layer, memory boundaries, tool routing, output contracts, privacy rules, and human review loops.

## Harness Engineering

Harness engineering means designing the environment that makes a model useful, repeatable, and safe enough for real work.

In this system, the harness includes:

- skill routing: deciding which private workflow module should handle the task
- tool boundaries: deciding when the agent can use local files, browser checks, GitHub, documents, spreadsheets, or connectors
- output contracts: defining what useful work should look like for each task type
- verification checkpoints: forcing the system to check facts when the answer depends on current or external information
- privacy controls: preventing private source material from leaking into public artifacts
- human review loops: keeping judgment-heavy decisions under user control

The key idea is that the AI is not treated as a magic text generator. It is treated as one component inside a controlled operating system.

## Context Engineering

Context engineering means deciding what the model should know at the moment of work.

The system avoids two common failure modes:

- too little context: the model forgets the user's standards, goals, and prior decisions
- too much context: the model becomes overloaded with stale, irrelevant, or noisy information

The system handles this by separating context into layers:

- global memory for stable cross-task preferences
- on-demand memory for domain-specific standards
- project notes for private source material
- handoff notes for short-term continuity
- skills for recurring operating procedures

This makes context load intentional instead of accidental.

## Why This Matters

For repeated, high-context work, quality does not come only from a better model or a longer prompt.

Quality comes from the surrounding system:

- what context is loaded
- what context is excluded
- which tools are available
- what output is expected
- what must be verified
- what stays private
- where the human makes the final call

That is the layer this project explores.

## Example Pattern

```text
User asks for a recurring job
        |
        v
Skill selects the operating frame
        |
        v
Relevant memory is loaded, irrelevant context is excluded
        |
        v
Tools are used only when the task requires them
        |
        v
Output follows a task-specific contract
        |
        v
Human reviews judgment, tone, and risk
```

The implementation details remain private, but this is the system logic behind the public case study.

