# Architecture

The system is built around a private skill layer that sits between the user and the model.

```text
                    User goal
                        |
                        v
              Skill selection / routing
                        |
      +-----------------+-----------------+
      |                 |                 |
      v                 v                 v
 Relevant memory   Tool boundary    Output contract
      |                 |                 |
      +-----------------+-----------------+
                        |
                        v
                Human-reviewable work
```

## Layer 1: User Goal

The user does not need to restate the full workflow every time. A short request should be enough for the system to infer the recurring job type.

Examples of job types include research, writing, planning, outreach, document work, or repo publishing.

## Layer 2: Skill Selection

The agent selects a private skill based on the task type. The skill defines the operating procedure for that kind of work.

This is the main difference from ordinary prompting. Instead of treating every request as a fresh chat, the system routes it through a reusable task frame.

## Layer 3: Relevant Memory

The system separates memory into layers:

- global memory: stable preferences that apply broadly
- on-demand memory: domain-specific standards
- project notes: private source material for the current work
- handoff notes: short current-state continuity between sessions

This avoids both extremes: forgetting everything and loading everything.

## Layer 4: Tool Boundary

Different tasks need different tools. The skill layer defines when tools are appropriate and when they are not.

Examples:

- use local files when source material is already in the workspace
- use browser/search when facts may have changed
- use GitHub only for repo and publishing work
- use document or spreadsheet tools only when the artifact requires them
- avoid broad private-data searches unless the user explicitly points to the source

## Layer 5: Output Contract

Each skill defines what useful output looks like. This prevents the agent from creating a beautiful but useless wall of text, or from creating many files when the user only needs a decision.

The output contract usually defines:

- level of detail
- evidence expectations
- format
- what should be left out
- where human judgment is needed

## Layer 6: Human Review

The system is not trying to remove the user from judgment-heavy work. It is designed to make review faster and better.

The agent structures the work, surfaces tradeoffs, checks evidence where possible, and produces a reviewable artifact. The human still decides whether the positioning, tone, and risk level are right.

