# Agent Handoff

## Project intent

Build FRIDAY as a proactive multimodal layer around Caine/OpenClaw.

Caine already exists and can access files through WSL/main-PC integration. The gap is that he is reactive and text-bound. This project adds hearing, seeing, speaking, and proactive behavior.

## Hard constraints

- Keep the architecture modular.
- Preserve room for future expansion.
- Prefer safe autonomy over unrestricted autonomy.
- Do not enable uncontrolled self-editing in early milestones.
- Design for Windows host plus WSL integration.

## Current assumptions

- Existing OpenClaw/Caine system already has multiple skills.
- The assistant should be able to access local files and engineering context.
- The assistant may use webcam presence detection to decide whether to speak.

## What future agents should update

When work is completed, update:

1. `project/STATUS.md`
2. `project/TASKS.md`
3. `project/DECISIONS.md`

If a milestone changes, also update:

4. `docs/ROADMAP.md`

## Update protocol

Each agent should:

1. read `README.md`
2. read `project/STATUS.md`
3. read `project/TASKS.md`
4. check `project/DECISIONS.md`
5. append a short note to `project/STATUS.md` after meaningful work

## Decision rules

- Prefer the smallest useful working slice.
- Build host-device integrations behind adapters.
- Keep proactive behavior rule-based first, then layer AI judgment.
- Every always-on feature must have a disable switch.
- Every autonomous code-change path must require review in MVP.

## Near-term implementation priority

1. speech output
2. microphone input
3. screen awareness
4. presence-aware proactive loop
5. engineering task routing
6. safe self-improvement workflow
