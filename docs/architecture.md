# JarvisCore Architecture

This document describes the high-level architecture of JarvisCore as a local AI-agent platform.

JarvisCore was designed as an experimental local assistant built around a local LLM, OpenAI-compatible API, OpenWebUI and a set of safety and verification layers.

---

## High-Level Architecture

JarvisCore consists of several main layers:

1. User Interface Layer
2. API Layer
3. Request Routing Layer
4. AI / LLM Layer
5. Tool and Source Processing Layer
6. Safe Execution Layer
7. Testing and Verification Layer
8. Snapshot / Rollback Layer

---

## 1. User Interface Layer

The user interacts with the assistant through OpenWebUI.

OpenWebUI is used as a local chat interface connected to the assistant through an OpenAI-compatible API.

Main responsibilities:

* receive user messages;
* display assistant responses;
* provide a simple chat-based workflow;
* allow interaction with local LLM-powered features.

---

## 2. API Layer

JarvisCore exposes an OpenAI-compatible API interface.

This layer allows the system to work with tools and interfaces that expect an OpenAI-style chat completion endpoint.

Main responsibilities:

* receive chat completion requests;
* route user messages to the correct internal logic;
* return structured assistant responses;
* support local model interaction.

---

## 3. Request Routing Layer

The routing layer determines how each user request should be processed.

Examples of routes:

* regular dialogue;
* source reading;
* safe execution;
* status / readiness checks;
* queue checks;
* technical commands;
* AI-agent workflows.

The goal of the routing layer is to avoid treating every request as a simple chat message. Different types of requests require different processing logic, safety checks and verification steps.

---

## 4. AI / LLM Layer

The LLM layer connects JarvisCore with local language models through LM Studio and an OpenAI-compatible interface.

Main responsibilities:

* generate natural language responses;
* support assistant reasoning;
* process user instructions;
* assist with source summaries;
* support AI-agent workflows.

The project focuses on local LLM usage rather than cloud-only inference.

---

## 5. Tool and Source Processing Layer

This layer contains modules that work with external or internal information sources.

The source reader is responsible for:

* reading links and sources;
* detecting source type;
* producing short summaries;
* saving source cards;
* reporting limitations honestly.

This layer is important for RAG-like behavior and source-grounded answers.

---

## 6. Safe Execution Layer

The safe execution layer was designed to prevent uncontrolled actions.

It includes:

* dry-run stage;
* backup creation;
* exact apply step;
* final verification;
* rollback-oriented workflow;
* blocking unsafe or ambiguous operations.

The main idea is that the assistant should not claim success unless the action was actually completed and verified.

---

## 7. Testing and Verification Layer

JarvisCore includes several verification mechanisms:

* smoke tests;
* regression gates;
* readiness checks;
* API availability checks;
* model availability checks;
* queue cleanliness checks;
* command center status checks.

This layer helps detect broken behavior after changes and prevents fake success.

---

## 8. Snapshot / Rollback Layer

After successful checks, JarvisCore can create stable snapshots.

The snapshot approach helps preserve known working states and makes it possible to return to a stable version if a later change breaks the system.

Main responsibilities:

* preserve stable states;
* support rollback-oriented development;
* document verified milestones;
* reduce risk during iterative development.

---

## Architecture Summary

JarvisCore is not only a chatbot. It is an experimental local AI-agent platform with multiple engineering layers:

* local LLM integration;
* request routing;
* source reading;
* safe execution;
* verification gates;
* status monitoring;
* snapshot-based stability workflow.

The project helped me understand how LLM-based systems can be made more reliable through routing, safety checks, structured reports and regression testing.
