# JarvisCore Roadmap

This document describes the planned next steps for the JarvisCore showcase project and related portfolio development.

JarvisCore is currently presented as a public showcase of a local AI-agent platform. The next goal is to make the project easier to understand for recruiters, technical reviewers and potential internship teams.

---

## Current Public Status

The public repository currently includes:

* project overview;
* high-level architecture description;
* safety and testing documentation;
* explanation of the main engineering ideas behind JarvisCore.

The full internal source code is not published because the project is still experimental and contains local environment-specific files.

---

## Short-Term Goals

### 1. Improve Public Documentation

Planned improvements:

* add a simple architecture diagram;
* add sanitized examples of system outputs;
* add example status reports;
* add example source reader output;
* add example safe execution report;
* improve README structure and navigation.

The goal is to make the repository understandable even without access to the full internal codebase.

---

### 2. Add Sanitized Examples

Future examples may include:

* sample API status report;
* sample command center report;
* sample source reader output;
* sample regression gate result;
* sample safe execution result.

All examples should be cleaned from local paths, private data, logs and environment-specific details.

---

### 3. Create a Public Demo Version

A simplified public demo version may include:

* minimal request router;
* simple intent classification;
* mock local LLM response;
* safe execution simulation;
* example JSON reports;
* small command-line interface.

The purpose of the demo version is to show the engineering approach without exposing the full internal project.

---

## Related Portfolio Project

### AI Assistant Intent Classifier

The next planned portfolio project is a small NLP project connected to the JarvisCore idea.

The project will classify user messages into several intent categories:

* regular dialogue;
* information search;
* source reading;
* technical command;
* AI-agent task;
* unsafe or sensitive request.

Planned stack:

* Python;
* pandas;
* scikit-learn;
* TF-IDF;
* Logistic Regression or Naive Bayes;
* train/test split;
* basic metrics;
* README documentation.

Future improvements may include:

* more training examples;
* error analysis;
* confusion matrix;
* simple API endpoint;
* PyTorch or Transformers version.

---

## Medium-Term Goals

### 1. Add More ML/NLP Components

Possible future improvements:

* intent classification;
* text classification;
* embeddings;
* simple RAG prototype;
* prompt routing experiments;
* evaluation of assistant responses.

---

### 2. Improve Testing Approach

Possible improvements:

* add sample unit tests;
* add simple regression test examples;
* add fake success prevention examples;
* add input/output contract examples;
* document test cases in a structured format.

---

### 3. Add Visual Diagrams

Possible diagrams:

* high-level architecture;
* request routing flow;
* safe execution pipeline;
* source reader flow;
* snapshot / rollback workflow.

Diagrams will help explain the project faster during internship or junior-position applications.

---

## Long-Term Goals

Long-term learning and development goals:

* improve Python engineering skills;
* study machine learning fundamentals;
* study NLP and Transformers;
* learn PyTorch more deeply;
* build small ML projects for portfolio;
* understand how LLM systems are deployed and tested;
* grow toward Junior AI Engineer, Junior LLM Engineer or ML/NLP Intern roles.

---

## Portfolio Direction

The portfolio should eventually include:

1. JarvisCore AI-agent showcase.
2. AI Assistant Intent Classifier.
3. Small text classification project.
4. Basic PyTorch / Transformers experiment.
5. Resume and links to GitHub repositories.

The goal is to show not only interest in AI, but also practical work with Python, local LLMs, request routing, safety checks, testing and documentation.
