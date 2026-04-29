# Architecture

## System shape

Use a modular architecture so FRIDAY can expand without rewriting the core.

## Main components

### 1. Orchestrator

The orchestrator is the central loop.

Responsibilities:

- receives events from all inputs
- builds context
- decides whether to ignore, notify, ask, or execute
- calls Caine/OpenClaw or the LLM
- sends text to TTS
- writes logs and memory

### 2. Input adapters

Adapters turn raw signals into normalized events.

Planned adapters:

- `voice_listener`
- `screen_watcher`
- `webcam_presence`
- `filesystem_watcher`
- `scheduler`
- `system_state`

### 3. Perception layer

This layer summarizes what is happening.

Examples:

- speech transcript from microphone input
- screen summary from screenshot analysis
- presence state from webcam
- active project or file context
- process/test/build status

### 4. Decision engine

This is the "should I speak now?" layer.

It uses:

- rules
- cooldowns
- priorities
- user state
- optional LLM judgment

Outputs:

- `stay_quiet`
- `speak_message`
- `ask_question`
- `queue_task_for_caine`
- `notify_text_only`

### 5. Action layer

This is where useful work happens.

Examples:

- call OpenRouter model
- call OpenClaw/Caine skills
- run approved local tools
- speak through TTS
- store memory/state

## Suggested runtime split

Because Caine is already in WSL with file access, use a split setup:

- Windows host:
  - microphone
  - webcam
  - screen capture
  - TTS audio output

- WSL/service layer:
  - orchestrator logic
  - task routing
  - OpenClaw integration
  - memory/state
  - repo engineering workflows

This keeps hardware access simple while preserving existing OpenClaw workflows.

## Suggested MVP stack

Use simple, replaceable pieces:

- Language: Python
- API access: OpenRouter-compatible HTTP client
- STT:
  - local first if practical, such as Whisper/Faster-Whisper
  - cloud fallback if needed
- TTS:
  - Windows TTS first for speed
  - optional better voice later
- Screen capture:
  - `mss` or equivalent
- Webcam presence:
  - OpenCV-based simple presence detection
- Scheduling:
  - APScheduler or a simple async timer loop
- Storage:
  - JSON or SQLite for MVP memory/state
- File watching:
  - `watchdog`

## Why not "random cron" alone

A pure random cron job will feel noisy.

Better model:

- baseline timer with random jitter
- only trigger if presence is true
- only trigger if quiet hours are false
- only trigger if cooldown expired
- only trigger if something useful changed or there is a reason to speak

## Safety constraints

MVP safety rules:

- no silent self-modifying production changes
- no speaking continuously
- no destructive file actions without approval
- all proactive actions logged
- explicit on/off controls for camera/mic/proactivity

## Growth path

This architecture leaves room for:

- better memory
- richer desktop automation
- multi-agent planning
- safer self-improvement loops
- personalized speaking style
- long-term project assistance
