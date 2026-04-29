# MVP Definition

## Product summary

FRIDAY is a proactive assistant layer for Caine/OpenClaw.

It sits between the user, local devices, and Caine's existing skills. Its job is to turn a reactive coding assistant into a multimodal assistant that can notice, ask, speak, and help without waiting for a typed message every time.

## Simplified MVP

If we simplify aggressively, the MVP is just this:

1. Listen for the user.
2. Observe the machine state.
3. Decide whether to respond.
4. Speak the response out loud.
5. Hand actual task execution to Caine/OpenClaw.

## What the MVP must do

- Hear:
  - capture microphone audio
  - convert speech to text
  - detect when the user is addressing FRIDAY

- See:
  - inspect the active screen or periodic screenshots
  - inspect selected folders/files
  - optionally use webcam presence detection to know whether the user is around

- Speak:
  - convert text responses to speech
  - support interruptions and short spoken messages

- Think:
  - use an LLM through OpenRouter for intent classification, response generation, and proactive reasoning
  - route execution requests to Caine/OpenClaw skills

- Act proactively:
  - run timer-based or event-based checks
  - ask useful questions sometimes
  - avoid being annoying by using cooldowns, quiet hours, and confidence thresholds

## What "proactive" means in MVP

Proactive does not mean "constantly talking."

For MVP, proactive means:

- if the user appears present and idle, FRIDAY may ask a short question
- if a watched build/test/job fails, FRIDAY may report it
- if calendar/task context exists later, FRIDAY may remind or suggest next steps
- if the screen shows engineering work, FRIDAY may offer a relevant action

## Best first use cases

The first practical use cases should be:

1. Voice command:
   - "FRIDAY, open the repo and check the failing tests."

2. Spoken engineering assistant:
   - FRIDAY sees the active repo, sends the task to Caine, then reads back a short result.

3. Presence-aware prompt:
   - webcam says the user is present, system is idle, cooldown expired, FRIDAY asks:
   - "Do you want me to review the current repo or keep watching quietly?"

4. Event-driven notification:
   - watched process exits with an error, FRIDAY says:
   - "The build failed. Do you want the error summary?"

## Recommended AI role

Use AI for decision-making and conversation, not for everything.

Good AI uses in MVP:

- speech-to-text if local models are not good enough
- intent recognition
- proactive question generation
- screen summary
- response drafting
- task routing

Do not let AI directly self-modify core behavior without review in MVP.

## Self-editing position

Self-editing is possible later, but the safe MVP version is:

- FRIDAY can propose code changes
- Caine can implement them in a branch or task workspace
- changes require review or explicit approval before activation

This keeps the system useful without creating a fragile autonomous loop.
