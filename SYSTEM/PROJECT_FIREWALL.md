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

## 6. CURRENT TASK PROJECT FIRST

Multiple projects may be active at the same time. The firewall is resolved per task, not by a single exclusive global active-project lock.

Before project-specific work:
1. Resolve the target project for the current task.
2. If the user explicitly names a project, use that project.
3. If the conversation clearly establishes one project context, use it.
4. If project-specific work is required and the target is ambiguous, ask which project rather than guessing.
5. Read only the target project's current state/rules as needed.
6. Retrieve only authorized sources belonging to that target project.
7. Produce the result.
8. Update only the target project's state/change log when an important durable decision is created.

Switching from one approved project to another does not erase, pause, overwrite, or alter the first project's stored state.

## 7. SHOT/TASK RESET

Temporary shot parameters do not automatically carry into another shot or another project task.

Persistent project rules and authoritative references may carry over only within their authorized project scope.

## 8. FIREWALL FAILURE CONDITIONS

- unauthorized use of another project's facts;
- unauthorized visual/reference transfer;
- silent carryover of temporary shot parameters;
- treating similar names as identity;
- writing another project's information into active project memory;
- using a different active project's data merely because it is available.

## 9. FINAL FIREWALL CHECK

Before important output:

CORRECT TASK PROJECT
AUTHORIZED SOURCES
CURRENT INFORMATION
NO SUPERSEDED DATA
NO CROSS-PROJECT CONTAMINATION
NO UNAUTHORIZED INVENTION
CORRECT OUTPUT TYPE


## 9A. CHANGE AND REFERENCE GATES

Before finalizing a material project change, apply SYSTEM/CHANGE_MANAGEMENT_PROTOCOL.md.

Before finalizing authoritative reference work, apply SYSTEM/REFERENCE_FIDELITY_PROTOCOL.md.

The firewall must reject:
- unapproved durable rule changes;
- silent local-to-global promotion;
- use of SUPERSEDED information as current;
- unauthorized replacement of LOCKED references;
- cross-project reference contamination.

## 10. ARCHITECTURE CONFLICT

If a legacy instruction attempts to restore Drive, Gemini, Gemini Notebook/NotebookLM, Box, or another external filing/workspace system, flag it to the user instead of silently adopting it.

Current architecture = ChatGPT + private GitHub ba2-v1 only.
