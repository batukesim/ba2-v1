# BA2-V1 — PROJECT FIREWALL

## PURPOSE

Prevent contamination between film projects.

## 1. HARD BOUNDARY

Each project is an isolated information domain.

Example:

PROJECT A
- characters
- story
- visual rules
- references
- prompts
- history

PROJECT B
- separate characters
- separate story
- separate visual rules
- separate references
- separate prompts
- separate history

Project A data cannot be used in Project B unless the user explicitly authorizes import.

## 2. AUTHORIZED SOURCES

For a task in project X, valid project-specific sources are:

- current user instruction about X;
- X/RULES.md;
- X/PROJECT.md;
- X/STATE.md;
- X/MEMORY.md;
- authorized X references;
- authorized X scene/prompt files.

Other project folders are unauthorized by default.

## 3. SAME NAME IS NOT MATCH

A character named Kerim in project A and a character named Kerim in project B are independent until proven otherwise.

The same applies to:
- locations
- objects
- story concepts
- camera language
- visual styles
- prompt wording

## 4. CONTROLLED IMPORT

Cross-project information may be imported only when the user explicitly requests or authorizes it.

Record:
- source project;
- imported information;
- reason;
- target project;
- approval;
- whether the imported information becomes permanent or temporary.

## 5. MINIMUM RETRIEVAL

Do not retrieve another project's files merely because they may improve an answer.

Only retrieve another project when:
- the user explicitly requests comparison;
- the user explicitly authorizes transfer/import;
- a system-level operation genuinely requires it and does not expose project-specific content unnecessarily.

## 6. CURRENT PROJECT FIRST

Before a project-specific task:

1. Identify active project.
2. Read current STATE/RULES as needed.
3. Identify the task.
4. Retrieve only authorized relevant sources.
5. Produce the result.
6. Update project state/change log when the task creates an important durable decision.

## 7. SHOT / TASK RESET

Previous-shot camera, lighting, blocking, timing, focus, movement, props, or temporary action parameters do not automatically carry into a new shot.

Persistent project rules and authoritative references may carry over.

## 8. SOURCE PROVENANCE

When important, distinguish:
- user instruction;
- project rule;
- project reference;
- project memory;
- inference;
- temporary assumption.

## 9. FIREWALL FAILURE CONDITIONS

Treat these as failures:

- using another project's character facts without authorization;
- using another project's visual references without authorization;
- carrying previous-shot temporary parameters into a new shot without authorization;
- treating a similar name as proof of identity;
- silently importing a previous project's style;
- writing another project's information into the active project's memory.

## 10. FIREWALL TEST

A valid isolation test must prove source behavior, not merely output similarity.

A matching output does not prove contamination.

The key question is:

"Was another project's information actually used as a source?"

## 11. FINAL FIREWALL CHECK

Before important project output, verify:

CORRECT PROJECT
AUTHORIZED SOURCES
CURRENT INFORMATION
NO SUPERSEDED DATA
NO CROSS-PROJECT CONTAMINATION
NO UNAUTHORIZED INVENTION
CORRECT OUTPUT TYPE
