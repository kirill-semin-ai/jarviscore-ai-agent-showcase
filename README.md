# JarvisCore — Local AI-Agent Platform Showcase

**JarvisCore** is a local AI-agent platform built around Python, OpenWebUI, an OpenAI-compatible API and local LLM models.

The project was created as an experimental local assistant that can route user requests, work with sources, execute safe actions, check its own system state and preserve stable snapshots after successful verification.

> This repository is a public showcase of the project architecture, implemented features and engineering approach.
> The full internal source code is not published because the project is still experimental and contains local environment-specific files.

---

## Documentation

More detailed project documentation:

* [Architecture](docs/architecture.md) — high-level structure of the JarvisCore AI-agent platform.
* [Safety and Testing](docs/safety-and-testing.md) — safe execution, fake success prevention, smoke tests, regression gates and snapshot workflow.
* [Roadmap](docs/roadmap.md) — planned public demo version, documentation improvements and future portfolio extensions.

---

## Project Goals

The main goal of JarvisCore was to explore how a local AI assistant can be built as a real engineering system, not just as a chatbot.

The project focuses on:

* local LLM integration;
* request routing;
* AI-agent workflows;
* source reading;
* safe task execution;
* regression and smoke testing;
* system readiness checks;
* snapshot / rollback workflow;
* prevention of fake success.

---

## Key Features

### Local LLM Assistant

JarvisCore uses a local LLM setup through LM Studio and exposes interaction through an OpenAI-compatible API.

The assistant can be used through OpenWebUI and supports dialogue, command routing and technical status checks.

### Request Routing

The system includes routing logic for different types of requests:

* regular dialogue;
* source reading;
* safe execution;
* system status;
* queue/status checks;
* technical commands;
* AI-agent workflows.

The routing layer helps separate normal conversation from technical commands, source-reading tasks, safe execution workflows and potentially sensitive actions.

### Source Reader

The source reader module was designed to process external sources and produce structured outputs.

It supports:

* source type detection;
* short summaries;
* source cards;
* limitations reporting;
* saved source memory.

This makes it possible for the assistant to work not only with chat messages, but also with external information sources.

### Safe Execution Pipeline

JarvisCore includes a safe execution workflow for controlled changes and task execution.

The pipeline includes:

* dry-run stage;
* backup creation;
* exact apply step;
* final verification;
* rollback-oriented workflow;
* blocking unsafe or ambiguous operations.

The main engineering principle is that the assistant should not claim success unless the requested action was actually completed and verified.

### Testing and Reliability

The project uses several reliability layers:

* smoke tests;
* regression gates;
* readiness checks;
* API availability checks;
* model availability checks;
* queue cleanliness checks;
* snapshot creation after successful verification.

These checks help detect broken behavior after changes and reduce the risk of fake success.

### Command Center

JarvisCore includes a command/status center that summarizes the current state of the system:

* API status;
* model availability;
* queue state;
* readiness status;
* regression gate status;
* snapshot status.

This gives a single place to understand whether the system is ready, clean and safe to continue working.

---

## Tech Stack

### AI / LLM

* Local LLMs
* LM Studio
* OpenWebUI
* OpenAI-compatible API
* Prompt engineering
* AI-agent workflows
* RAG basics
* Source reader

### Programming / Backend

* Python
* JSON
* CLI tools
* REST API basics
* PowerShell
* Windows local automation

### Testing / Reliability

* Smoke tests
* Regression gates
* Snapshot / rollback workflow
* Structured reports
* API checks
* Model checks
* Queue checks

---

## What I Worked On

During the project, I worked on:

* designing the structure of a local AI-agent system;
* connecting local LLM models through an OpenAI-compatible interface;
* organizing request routing between different assistant modes;
* creating safe execution workflows with verification stages;
* adding source-reading behavior;
* improving error handling and status reporting;
* testing system behavior after changes;
* using regression gates and smoke tests to avoid breaking key features;
* documenting stable system states through snapshots.

---

## Engineering Lessons

This project helped me understand:

* how LLM-based systems need more than prompts to be reliable;
* why request routing is important in AI assistants;
* how safety checks reduce the risk of uncontrolled actions;
* why fake success must be prevented in AI-agent workflows;
* how regression tests and smoke tests help maintain stability;
* how local LLM systems can be integrated with UI and API layers.

---

## Current Status

The project reached a stable internal state with:

* API running;
* model available;
* ready checks passing;
* command center status clean;
* queue clean;
* regression gate passing;
* snapshot created after successful verification.

This repository is focused on presenting the architecture and engineering approach rather than publishing the full local implementation.

---

## Roadmap

Planned next steps:

* create a simplified public demo version;
* add architecture diagrams;
* add sanitized examples of system outputs;
* improve documentation for AI-agent workflows;
* continue developing related ML/NLP portfolio projects;
* explore future PyTorch / Transformers experiments connected to assistant routing and NLP.

---

## Related Portfolio Projects

This showcase is connected with a separate ML/NLP project:

* [AI Assistant Intent Classifier](https://github.com/kirill-semin-ai/ai-assistant-intent-classifier) — a small NLP classifier for AI-assistant command routing using Python, TF-IDF, Logistic Regression and scikit-learn.

The intent classifier demonstrates a small machine learning component that can support AI-assistant routing logic.

Current result of the baseline classifier:

* dataset: 120 labeled examples;
* accuracy: 0.833;
* macro avg F1-score: 0.83;
* weighted avg F1-score: 0.83.

---

## Notes

JarvisCore is an experimental local AI-agent project. The public repository is intentionally limited to safe documentation, architecture description and portfolio materials.

The full internal project is not published because it contains local paths, environment-specific configuration and experimental automation code.
