# NASIS

**N-AI Security Intelligence System**

A local, offline AI assistant for penetration testers.

## Status

In active development and not yet released publicly. This folder holds the project overview and documentation; the code is not published here yet.

## Why NASIS

Cloud AI assistants are convenient, but pentest data (targets, findings, client details) should not leave the machine. NASIS runs entirely on local hardware, so there is **no cloud dependency**.

## What it does

* Assists during penetration tests with conversational analysis
* Explains attack chains step by step
* Provides security insights grounded in a knowledge base (RAG)
* Keeps a human in the loop: the assistant proposes, the operator confirms

## Modes

| Mode | Purpose |
| --- | --- |
| analyst | Analyze findings, logs, and scan output |
| tutor | Explain concepts and walk through techniques |
| coder | Write and review scripts and tooling |
| assistant | General day-to-day help |
| red_team | Offensive planning and technique support |
| blue_team | Detection, triage, and defensive support |

## Architecture at a glance

* **Language models:** run locally through Ollama
* **Knowledge base:** retrieval-augmented generation (RAG) over security material such as ATT&CK, CVE data, Sigma rules, cheat sheets, and public writeups
* **Interfaces:** terminal-first, with a text user interface (TUI).
* **Safety:** generated code runs in a constrained sandbox, and commands require operator confirmation

## Tech stack

* **Language and models:** Python, with local models served through Ollama
* **Retrieval:** FAISS (dense) plus SQLite full-text search (lexical) for hybrid RAG
* **Interface:** terminal UI built with Rich and prompt_toolkit
* **Web search:** self-hosted SearXNG, so searches stay private

## Roadmap

- [x] Local LLM chat with multiple modes
- [x] RAG knowledge base
- [x] Sandboxed execution of generated code
- [x] Tools (Agentic Workflow, Bench, Template, audit..etc)
- [x] Search Engine
- [ ] Train Cyber LLM for Blue and Red Teaming
- [ ] Computer use and independency 
- [ ] Full Test
- [ ] Documentation and demo videos
- [ ] Publish!

## Responsible use

NASIS is built for authorized security testing, labs, CTFs, and learning. Use it only on systems you own or have written permission to test.
