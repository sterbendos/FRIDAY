# Roadmap

## Milestone 0: Foundation

Goal:

- define scope, docs, constraints, and project structure

Exit criteria:

- project docs exist
- active tasks are tracked
- architecture and MVP are documented

## Milestone 1: Speaking Caine

Goal:

- make Caine able to speak text aloud on demand

Build:

- TTS adapter
- simple CLI or service endpoint: text in, speech out
- voice settings config

Exit criteria:

- local command can make FRIDAY speak reliably
- logs record each spoken output

## Milestone 2: Hearing

Goal:

- enable microphone input and speech-to-text

Build:

- microphone capture
- push-to-talk or wake trigger
- transcript pipeline
- routing from transcript to Caine/OpenRouter

Exit criteria:

- user can talk to FRIDAY and hear a spoken reply
- false activations are manageable

## Milestone 3: Vision

Goal:

- give FRIDAY desktop awareness and optional presence sensing

Build:

- screenshot capture
- active window context
- watched folders/files
- optional webcam presence state

Exit criteria:

- FRIDAY can summarize current screen or repo context
- FRIDAY can tell whether the user is likely present

## Milestone 4: Proactivity

Goal:

- let FRIDAY initiate useful conversations

Build:

- scheduler with jitter
- rules engine
- cooldowns and quiet hours
- event-triggered suggestions

Exit criteria:

- FRIDAY can ask useful, short questions without becoming noisy
- proactive events are explainable and logged

## Milestone 5: Engineering Copilot Mode

Goal:

- integrate deeply with Caine/OpenClaw skills for engineering tasks

Build:

- task routing to known skills
- repo detection
- build/test watcher
- spoken summaries for engineering actions

Exit criteria:

- FRIDAY can help with active repos using speech, screen context, and local files

## Milestone 6: Safe Self-Improvement

Goal:

- allow the system to improve itself safely

Build:

- proposal pipeline for code changes
- review/approval gate
- sandbox or branch workflow
- evaluation checks before activation

Exit criteria:

- FRIDAY can propose or prepare self-improvements without silently deploying them
