# AI Workflow OS

A public case study of a private, skill-based AI operating system.

This project is not a collection of prompts. The core idea is that serious AI work needs a layer above prompting: reusable skills that know when to activate, what context to load, which tools to use, what output standard to meet, and where human review should happen.

The actual skill files are private. This repo explains why I designed the system this way, what problems it solves, and how the architecture works without exposing the implementation details.

## Why Skills

Plain prompts are useful for one-off tasks, but they break down when the work becomes repeated, high-context, and judgment-heavy.

I started designing skills because I kept seeing the same failure modes:

- every new chat required re-explaining the same standards
- useful context was either missing or overloaded into global memory
- the AI would generate too many files, too much structure, or the wrong kind of output
- tool use was inconsistent unless the workflow explicitly defined when and why to use tools
- strong outputs required not just writing ability, but evidence checks, claim calibration, and human review

A skill turns a recurring job into an operating module. It is not just "the prompt." It is the combination of:

- trigger: when this workflow should activate
- context boundary: what memory or source material is relevant
- tool boundary: what the agent may inspect or call
- judgment standard: what good output means
- output contract: what the user should receive
- review loop: where the human should approve, reject, or refine the result

## What This Demonstrates

- AI product judgment: designing the layer between raw model capability and useful user workflow
- information architecture: separating global memory, on-demand memory, private project context, and reusable skills
- tool orchestration: deciding when the agent should use local files, browser checks, GitHub, documents, spreadsheets, or connectors
- privacy boundaries: keeping private working materials out of public artifacts
- human-in-the-loop design: using AI for leverage without removing user judgment
- harness engineering: building the control layer around the model so it can operate reliably
- context engineering: deciding what the model should know, ignore, retrieve, and preserve

## Skill Case Studies

I do not publish the private skill files, but I do share high-level examples of why certain skills were created.

See `SKILL_CASES.md` for sanitized design notes on skills such as LinkedIn person prep, company research, outreach drafting, and resume positioning.

See `HARNESS_AND_CONTEXT.md` for how the system applies harness engineering and context engineering principles.

## What This Repo Contains

- `WHY_SKILLS.md`: why I built a skill layer instead of relying on one-off prompts
- `SKILL_CASES.md`: sanitized examples of workflow problems that became private skills
- `HARNESS_AND_CONTEXT.md`: how the system applies harness engineering and context engineering
- `ARCHITECTURE.md`: how memory, skills, tools, and human review fit together
- `CAPABILITIES.md`: high-level capability areas, without publishing private skill contents
- `.gitignore`: guardrails to avoid pushing private data

## What Is Not Published

The private system includes detailed skill instructions, decision rubrics, source notes, examples, and workflow-specific guardrails. I am not publishing those because they contain personal operating insight and private work context.

I am happy to walk through the architecture and selected sanitized examples live.

## Resume-Ready Summary

Designed a private, skill-based AI workflow operating system using Codex, Claude Code, Obsidian, and MCP-style connectors, applying harness engineering and context engineering to turn repeated high-context work into reusable AI modules with explicit memory boundaries, tool routing, privacy controls, and human review loops.
