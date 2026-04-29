# FRIDAY

FRIDAY is a proactive desktop AI assistant inspired by the kind of ambient, multimodal assistant seen in Iron Man.

The goal is not to build a science-fiction system on day one. The goal is to build a practical MVP that can:

- hear the user
- see the desktop and optional webcam
- speak back out loud
- notice context and start conversations sometimes
- help with engineering and desktop workflows
- leave room for future growth

## MVP in one sentence

Build a local orchestrator that can observe, decide, and speak, instead of only waiting for typed prompts.

## What FRIDAY is

Most AI assistants are reactive: you type something, they answer, and then they stop.

FRIDAY is intended to be event-driven:

- inputs come from microphone, screen, webcam, files, and timers
- a controller decides whether to stay quiet, notify, ask, or act
- outputs go to speech, logs, and connected tools

The long-term vision is a local assistant that can work alongside the user throughout the day, especially during technical and engineering tasks.

FRIDAY is designed to work as a multimodal orchestration layer on top of an existing agent stack, tool runtime, or local automation system.

## Initial scope

The first version should support:

- push-to-talk or wake-trigger voice input
- text-to-speech replies
- desktop/screen awareness
- optional webcam presence detection
- proactive check-ins on a schedule with cooldowns
- engineering assistant workflows through existing file access
- a shared project memory so multiple agents can continue the work

## Why this project exists

The interesting problem is not just "add speech to a chatbot."

The real problem is building an assistant that can:

- understand when the user is present
- notice what is happening on the machine
- decide whether speaking is actually useful
- stay modular enough to expand over time

## Design principles

- local-first where practical
- modular adapters for audio, vision, memory, and tools
- safe autonomy instead of unrestricted autonomy
- proactive behavior with cooldowns and controls
- room for future self-improvement workflows with review gates

## Non-goals for MVP

- full autonomy with unrestricted self-editing
- always-on unsupervised code changes
- advanced robotics
- perfect real-time multimodal reasoning
- production-grade security hardening

## Project docs

- `docs/MVP.md`: simplified product definition
- `docs/ARCHITECTURE.md`: technical shape of the system
- `docs/ROADMAP.md`: milestone plan
- `docs/AGENT_HANDOFF.md`: instructions for future agents
- `project/STATUS.md`: current state and progress log
- `project/TASKS.md`: active task list
- `project/DECISIONS.md`: design decisions and constraints

## Current status

Current phase: planning and scaffolding.

The repository currently contains the MVP definition, architecture notes, roadmap, and project operating docs for future implementation.
