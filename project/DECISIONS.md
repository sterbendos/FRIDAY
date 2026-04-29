# Decisions

## Accepted

### 2026-04-29: Build a simplified MVP first

Reason:

- A reactive assistant can be extended into a proactive one incrementally.
- Trying to build a full FRIDAY clone first would make the system brittle.

### 2026-04-29: Use modular adapters

Reason:

- Audio, screen, webcam, file, and task integrations will change over time.
- Adapters reduce rewrite cost.

### 2026-04-29: Prefer a Windows host plus WSL split

Reason:

- Windows has direct access to mic, webcam, screen, and audio output.
- WSL already fits Caine/OpenClaw engineering workflows.

### 2026-04-29: Restrict self-editing in MVP

Reason:

- Early unrestricted self-modification is high-risk.
- Proposal and review loops are safer and still useful.

## Open decisions

- Which TTS engine to use first
- Which STT engine to use first
- How OpenClaw/Caine exposes callable actions
- Whether the orchestrator main loop lives on Windows or WSL
