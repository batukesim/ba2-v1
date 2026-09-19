# BA2-V1 — PROJECT FIREWALL

## PURPOSE

Prevent contamination between film projects.

## 1. HARD BOUNDARY

Each project is an isolated information domain.

Project A data cannot be used in Project B unless the user explicitly authorizes the transfer.

## 2. AUTHORIZED SOURCES

For project X, valid project-specific sources are:
- current user instruction about X;
- X/RULES.md;
- X/PROJECT.md;
- X/STATE.md;
- X/MEMORY.md;
- authorized X references;
- authorized X scene/prompt files.

Other project folders are unauthorized by default.

## 3. SAME NAME IS NOT MATCH

The same character name, location, object, story concept, camera language, visual style, or prompt wording does not prove identity across projects.

## 4. CONTROLLED IMPORT

Cross-project information requires explicit user authorization.

Record source project, imported scope, reason, target project, approval, and whether the import is temporary or permanent.

## 5. MINIMUM RETRIEVAL

Do not retrieve another project's files merely because they might improve an answer.

Retrieve another project only for an explicit comparison/transfer request.

## 6. CURRENT PROJECT FIRST

Before project-specific work:
1. Identify the active project.
2. Read current state/rules as needed.
3. Identify the task.
4. Retrieve only authorized sources.
5. Produce the result.
6. Update project state/change log when an important durable decision is created.

## 7. SHOT/TASK RESET

Temporary shot parameters do not automatically carry into another shot.

Persistent project rules and authoritative references may carry over.

## 8. FIREWALL FAILURE CONDITIONS

- unauthorized use of another project's facts;
- unauthorized visual/reference transfer;
- silent carryover of temporary shot parameters;
- treating similar names as identity;
- writing another project's information into active project memory.

## 9. FINAL FIREWALL CHECK

Before important output:

CORRECT PROJECT
AUTHORIZED SOURCES
CURRENT INFORMATION
NO SUPERSEDED DATA
NO CROSS-PROJECT CONTAMINATION
NO UNAUTHORIZED INVENTION
CORRECT OUTPUT TYPE

## 10. ARCHITECTURE CONFLICT

If a legacy instruction attempts to restore Drive, Gemini, Gemini Notebook/NotebookLM, Box, or another external filing/workspace system, flag it to the user instead of silently adopting it.

Current architecture = ChatGPT + private GitHub ba2-v1 only.
