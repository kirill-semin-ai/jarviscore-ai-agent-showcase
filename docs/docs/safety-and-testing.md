# Safety and Testing in JarvisCore

This document describes the safety, verification and reliability approach used in JarvisCore.

JarvisCore was designed not only as a local AI assistant, but also as an experimental AI-agent system with safety checks, verification stages and rollback-oriented development.

---

## Why Safety Matters

AI-agent systems can produce incorrect, incomplete or unsafe actions if they are allowed to execute commands without control.

The main safety idea in JarvisCore is:

> The assistant should not claim success unless the requested action was actually completed and verified.

This principle helps prevent fake success and makes the system more reliable during iterative development.

---

## Safe Execution Pipeline

JarvisCore uses a controlled safe execution workflow for sensitive or technical actions.

The pipeline includes:

1. Request classification
2. Safety checks
3. Dry-run stage
4. Backup creation
5. Exact apply step
6. Final verification
7. Report generation
8. Snapshot-ready state

---

## 1. Request Classification

Before an action is processed, the system determines what type of request it is.

Examples:

* regular dialogue;
* source reading;
* system status request;
* safe execution request;
* technical command;
* potentially unsafe operation.

This helps avoid running technical logic for simple chat messages and prevents unsafe requests from being executed automatically.

---

## 2. Safety Checks

Safety checks are used to block actions that are ambiguous, too broad or potentially dangerous.

Examples of safety rules:

* avoid uncontrolled file changes;
* avoid unsafe paths;
* avoid destructive actions;
* avoid pretending that an action succeeded when it did not;
* require verification after important operations.

---

## 3. Dry-Run Stage

Before applying changes, the system can describe what would be changed.

The dry-run stage helps check the planned action before execution.

This reduces the risk of accidental or uncontrolled modifications.

---

## 4. Backup and Rollback-Oriented Workflow

Before applying important changes, JarvisCore uses a backup-oriented approach.

The goal is to preserve a known working state before modifications.

This supports rollback-oriented development and makes experiments safer.

---

## 5. Final Verification

After an action is applied, JarvisCore performs verification.

Examples of verification checks:

* Python compile checks;
* API availability checks;
* model availability checks;
* command center status;
* queue cleanliness checks;
* smoke tests;
* regression gates.

The assistant should only report success after verification passes.

---

## Smoke Tests

Smoke tests are quick checks that verify whether the main system behavior still works.

Examples:

* API responds correctly;
* model is available;
* status command works;
* safe execution success path works;
* safe execution failure path works;
* source reader returns structured output.

Smoke tests help detect obvious breakages early.

---

## Regression Gates

Regression gates are used to check that important functionality was not broken after changes.

A regression gate can include:

* route checks;
* API checks;
* command checks;
* source reader checks;
* safe execution checks;
* status/matrix checks;
* fake success prevention checks.

Regression gates make the project more stable during frequent updates.

---

## Fake Success Prevention

One of the main engineering principles of JarvisCore is preventing fake success.

Fake success means that the assistant says an action was completed when it was not actually performed or verified.

JarvisCore avoids this through:

* explicit status checks;
* structured reports;
* verification after actions;
* failure messages when a task cannot be completed;
* avoiding silent errors.

---

## Snapshot Workflow

After successful verification, the project can create a stable snapshot.

Snapshots are used to preserve known working states.

This helps:

* reduce risk during experimentation;
* document verified milestones;
* return to a stable state if something breaks;
* separate experimental changes from confirmed stable states.

---

## Reliability Summary

JarvisCore uses several reliability layers:

* request classification;
* safety checks;
* dry-run behavior;
* backup-oriented workflow;
* final verification;
* smoke tests;
* regression gates;
* fake success prevention;
* snapshot / rollback workflow.

This approach helped me understand how AI-agent systems can be made more reliable, controlled and easier to debug.
