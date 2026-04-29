# FRIDAY

FRIDAY is a proactive desktop AI assistant for Caine/OpenClaw.

The goal is not to build "full Iron Man FRIDAY" first. The goal is to build a safe MVP that can:

- hear the user
- see the desktop and optional webcam
- speak back out loud
- notice context and start conversations sometimes
- help with engineering work on the PC/WSL setup
- leave room for future growth

## MVP in one sentence

Build a local orchestrator around Caine so he can observe, decide, and speak, instead of only waiting for typed prompts.

## Core idea

Today Caine is mostly reactive.

The MVP makes him event-driven:

- inputs come from microphone, screen, webcam, files, and timers
- a controller decides whether to stay quiet, notify, ask, or act
- outputs go to speech, logs, and existing OpenClaw skills

## Initial scope

The first version should support:

- push-to-talk or wake-trigger voice input
- text-to-speech replies
- desktop/screen awareness
- optional webcam presence detection
- proactive check-ins on a schedule with cooldowns
- engineering assistant workflows through existing file access
- a shared project memory so multiple agents can continue the work

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
