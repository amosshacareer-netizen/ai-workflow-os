# Capabilities

This repo intentionally describes capabilities at a high level. It does not publish the private skill files or the operating playbook behind them.

## 1. Skill-Based Workflow Design

The system turns repeated AI tasks into private skill modules instead of relying on one-off prompts.

This demonstrates:

- task routing
- context scoping
- output contracts
- repeatable workflow design
- human-review checkpoints
- problem-to-module product thinking

## 2. Harness Engineering

The system treats the model as one component inside a broader operating harness.

This demonstrates:

- workflow routing around the model
- tool access boundaries
- output contracts
- verification checkpoints
- privacy controls
- human approval loops

## 3. Context Engineering

The system separates durable context into layers so the AI can stay useful without becoming overloaded.

This demonstrates:

- global versus on-demand memory design
- project-specific context boundaries
- retrieval discipline
- continuity across sessions
- memory hygiene

## 4. Tool Orchestration

The system defines when the agent should use tools and when it should stay inside the current context.

This demonstrates:

- local file workflows
- browser and search verification
- GitHub publishing
- document and spreadsheet workflows
- connector boundaries for private data

## 5. Evidence-Aware Output

For high-stakes writing or research, the system pushes the agent to separate what is known, what is inferred, and what needs verification.

This demonstrates:

- claim calibration
- source-aware reasoning
- risk flags
- reviewable decision support

## 6. Privacy-Aware Public Artifacts

The system can produce public-facing artifacts without exposing the private source layer.

This demonstrates:

- sanitized case-study writing
- exclusion rules for private material
- public/private boundary design
- live walkthrough as the right format for deeper implementation details
