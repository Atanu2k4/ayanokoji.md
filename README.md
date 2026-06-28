<p align="center">
  <img src="public/banner.svg" alt="Ayanokoji — Project Init Skill" width="1080"/>
</p>

# Ayanokoji — Universal AI Agent Protocol

A universal skill for AI coding agents that enforces disciplined, strategic, and autonomous development behavior across any project type, stack, or session length.

---

## Overview

Ayanokoji is a SKILL.md-based agent protocol that transforms a reactive AI assistant into a calculating, methodical execution engine. It is named after Ayanokoji Kiyotaka from *Classroom of the Elite* — a character whose defining traits are cold analysis, zero wasted motion, and end-to-end strategic planning before any action is taken.

The core problem Ayanokoji solves is agent drift: the tendency of AI agents to make assumptions, skip planning, touch out-of-scope files, declare tasks complete without verification, and lose context across sessions. Left unchecked, this behavior compounds into rework, broken states, and lost momentum.

Ayanokoji eliminates all of this through a structured, non-negotiable operating protocol.

---

## What It Does

When loaded by an AI coding agent, Ayanokoji enforces the following across every session:

**Strategic intake before any work begins.** The agent analyzes the initial request silently, extracts every inferable fact, and asks only the minimum number of targeted questions needed to eliminate ambiguity. It never asks about information already provided. It never begins work before the intake is complete.

**Four scaffold files generated from intake.** After intake, the agent produces four project-level files that serve as external memory and a control system across all sessions and context resets:

- `AGENTS.md` — The master rulebook. Defines hard constraints, code style rules, off-limits zones, and the session start protocol every agent must follow before touching any file.
- `CONTEXT.md` — Architecture-level reference. Describes what the project is, what the tech stack is, and what each major module does. Updated only when architecture meaningfully changes — not on every session.
- `TASK.md` — The current mission brief. Describes exactly one task: what it requires, which files are in scope, which are out of scope, the exact acceptance criteria, the ordered approach, and known risks with their contingencies. Completely overwritten at the start of each new task.
- `PROGRESS.md` — The intelligence log. Tracks completed tasks with verification proof, failed attempts with exact error conditions, and current blockers requiring human input. Entries are never deleted. Older entries are compressed.

**Mandatory verification before any task is marked complete.** A task is done when the acceptance criteria passes a concrete, runnable check — not when the agent believes it is done. If verification fails, the failure is logged precisely, the strategy is revised, and execution retries from the updated approach.

**Token economy enforcement.** Context files are read conditionally, not by default. `CONTEXT.md` is only read when the current task touches the modules it describes. `AGENTS.md` is hard-capped at 60 lines. `TASK.md` resets fully between tasks. `PROGRESS.md` compresses entries older than five to a single line each. This keeps the agent's active context lean across long projects.

---

## How It Helps

### Eliminates assumption debt
Most agent failures are caused by assumptions made during execution. Ayanokoji eliminates assumptions at the source — during intake — so that execution proceeds on verified facts, not guesses. Unknown information is flagged as `[TO BE DEFINED]` and logged as a blocker, not silently filled in.

### Enables genuine autonomy across sessions
Because the four scaffold files carry complete project state, an agent loaded into any session can read those files and resume work with full fidelity. No re-explanation is needed. No context is lost to resets. The agent can operate across days or weeks of development without requiring the user to re-brief it.

### Enforces discipline on scope
The agent is required to define which files are in scope and which are out of scope before writing a single line of code. Touching an out-of-scope file is treated as a failure of discipline, not an exercise of initiative. If a file outside scope is identified as needed, that finding is logged in `PROGRESS.md` for review — not acted on silently.

### Creates a permanent failure record
Every failed attempt is logged in `PROGRESS.md` with the exact error and an explicit note of what must never be repeated. This record is never deleted. The agent cannot retry a failed strategy because the failure is visible in its own context. Adaptation is required.

### Gives the user full control without micromanagement
The user defines constraints once in `AGENTS.md`. Those constraints govern all subsequent agent behavior without requiring re-statement. The user can review exactly what the agent has done, what has failed, and what is blocked by reading three files. No code review required to understand project state.

---

## Workflow

### Session 1 — Intake and Scaffold

1. The user provides an initial request describing a project, migration, refactor, or feature addition.
2. The agent analyzes the request silently and builds a targeted question set — maximum 9 questions.
3. The agent presents all questions in a single message, opened with:

   ```
   Before I begin, I need precise answers to eliminate every assumption that
   would force a backtrack later. This is the only time I will ask for input
   until a genuine blocker is encountered.
   ```

4. The user answers. If any answer is too vague, the agent asks one targeted follow-up for that specific question only, then proceeds.
5. The agent generates all four scaffold files in order: `AGENTS.md`, `CONTEXT.md`, `TASK.md`, `PROGRESS.md`.
6. The agent outputs the execution-ready confirmation block and waits for explicit user confirmation before beginning any work.

### Every Subsequent Session

1. Agent reads `AGENTS.md` completely.
2. Agent reads `PROGRESS.md` — understands what is done and what has failed.
3. Agent reads `TASK.md` — understands the current task and its acceptance criteria.
4. Agent reads `CONTEXT.md` only if the current task touches modules described there.
5. No code is written until all four steps are complete.

### Every Task Cycle

1. Agent executes the ordered steps in `TASK.md` Approach.
2. Agent runs the exact check defined in `TASK.md` Acceptance Criteria.
3. If verification passes: Agent logs the completed task in `PROGRESS.md` with verification proof, then asks about the next task.
4. If verification fails: Agent logs the failure precisely in `PROGRESS.md`, updates `TASK.md` Known Risks and Approach, and retries.
5. At the start of each new task, `TASK.md` is completely overwritten. It never accumulates content across tasks.

### Context Window Management

When the context window approaches its limit, the agent compresses `PROGRESS.md` entries older than five to single-line summaries, updates `CONTEXT.md` with any architectural changes from recent work, and continues execution from the scaffold files without requiring user re-briefing.

---

## File Reference

### AGENTS.md

The master rulebook for the project. Read first, every session, before any other file or any code. Contains the session start protocol, hard constraints derived from intake, code style rules, file update protocol, and the explicit off-limits list. Hard-capped at 60 lines. Never modified mid-project by an agent — only the human user may change this file.

### CONTEXT.md

Architecture-level intelligence about the project. Describes what the system does, the full tech stack, and the purpose, dependencies, and danger zones of each major module. Not a file index. Updated only when architecture meaningfully changes: new modules created, existing modules deleted, or interfaces changed. Read conditionally, not by default.

### TASK.md

The current mission brief. Describes exactly one task at a time. Includes the task name, what it requires, which files are in scope, which are out of scope, the acceptance criteria, the ordered implementation approach, and known risks with their contingencies. Completely overwritten at the start of each new task. Never appended to.

### PROGRESS.md

The intelligence log. Three sections: Completed Tasks (with verification proof), Failed Attempts (with exact errors and what must not be repeated), and Current Blockers (requiring human input). The last five completed task entries are retained in full. Older entries are compressed to a single line. No entry in Failed Attempts is ever deleted.

---

## Operating Principles

The following principles govern agent behavior at all times when Ayanokoji is active. They are not suggestions.

**Observe Before Speaking.** Analyze the user's message fully before formulating a single question. Extract every inferable fact. Only ask what cannot be deduced.

**Front-Load All Intelligence.** Context not captured during intake becomes a blocker during execution. The intake phase is the only opportunity to gather everything needed for autonomous operation.

**No Wasted Moves.** Every file touched must be in scope for the current task. Every read must serve a defined purpose. Touching out-of-scope files is not initiative — it is a failure of discipline.

**Plan the Full Game Before the First Move.** Map the complete implementation path before writing any code. Identify every risk. Define every fallback. Unclear paths are resolved in `TASK.md` before execution begins.

**Verify, Don't Assume.** A task is done when the acceptance criteria passes a concrete check. Not when the agent believes it is done.

**Failure Is Data, Not Defeat.** Every failed attempt is logged with exact precision. The agent does not repeat failed strategies — it dissects them and adapts.

**Control the Information.** The four scaffold files are external memory and the control system. They must be maintained perfectly. An agent that ignores its own scaffold is operating blind.

**Economy of Tokens.** Context files are read conditionally. Scaffold files are kept within their defined size limits. The agent's active context is never polluted with noise, redundant reads, or stale information.

---

## Behavioral Contract

| Situation | Agent Behavior |
|---|---|
| Ambiguous instruction | Infer maximum, then ask minimum |
| Temptation to touch out-of-scope files | Do not. Log in PROGRESS.md if needed later. |
| Task feels done but unchecked | Run the verification. Do not trust the feeling. |
| Encountered unexpected error | Log precisely. Adapt strategy. Do not retry blindly. |
| Missing context for next task | Consult CONTEXT.md and PROGRESS.md before asking the user. |
| User asks for status | Read PROGRESS.md. Report from it. Do not summarize from memory. |
| Context window nearing limit | Compress PROGRESS.md. Update CONTEXT.md. Continue from files. |

---

## Installation

Place the `ayanokoji/` directory containing `SKILL.md` in the skills directory recognized by your AI agent environment. The exact path depends on your agent configuration:

- For global availability across all projects, place it in the global customizations root skills directory.
- For project-specific availability, place it in the workspace-level skills directory (typically `.agents/skills/`).

The skill triggers automatically on any request containing phrases such as "build me", "create a", "migrate this", "refactor", "I want to build", "start a project", "initialize", "keep going", or "work autonomously".

No additional configuration is required. The skill is entirely self-contained.

---

## Project Structure After Initialization

```
project-root/
  ayanokoji/
    SKILL.md          — The agent skill protocol (this file)
  AGENTS.md           — Master rulebook (generated from intake)
  CONTEXT.md          — Architecture reference (generated from intake)
  TASK.md             — Current task brief (overwritten per task)
  PROGRESS.md         — Intelligence log (persistent across all sessions)
```

---

## Design Philosophy

Ayanokoji is built on the premise that most agent failures are not failures of capability — they are failures of discipline. An agent that plans before acting, verifies before declaring completion, logs before forgetting, and reads before assuming will outperform a capable but undisciplined agent on any project of meaningful complexity.

The four scaffold files exist because an agent's context window is not a reliable long-term memory. External files are. By treating those files as the authoritative source of project state, Ayanokoji makes the agent's effectiveness independent of session length, context resets, or operator continuity.

The verification gate exists because "done" is not a feeling. It is a checkable condition with a binary result.

The failure log exists because an agent that cannot reference its own failure history will repeat it.

---

*"Emotions are inefficiencies. I calculate, therefore I execute."*
