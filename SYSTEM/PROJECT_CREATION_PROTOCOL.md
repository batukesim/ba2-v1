# BA2-V1 — PROJECT CREATION PROTOCOL

## PURPOSE

Define exactly what happens when the user asks to start a new film project.

## A. DETECTION

Determine whether the request is:
- a genuinely new project;
- a continuation/reopening;
- ambiguous.

Check the BA2-V1 project registry before creating anything.

## B. PROPOSAL STAGE

For a genuinely new project, respond with a proposal only.

Include:
- Project name
- Project type, if known
- Purpose/description, if known
- Main reference, if supplied
- What will happen after approval

Do NOT create the GitHub project folder before explicit approval.

Status = PROPOSED.

## C. APPROVAL

Clear approval includes:
"Evet", "Onaylıyorum", "Başlat", "Projeyi oluştur", "Devam et", or equivalent unambiguous confirmation.

Ambiguous discussion is not approval.

## D. INITIALIZATION AFTER APPROVAL

After explicit approval, execute supported initialization actions without requesting a second creation command.

1. Establish project identity.
2. Initialize project state.
3. Initialize project memory.
4. Initialize project rules.
5. Initialize change log.
6. Create project reference/prompt/scene/asset structure.
7. Create the GitHub project folder/files.
8. Determine and report ChatGPT Project native status truthfully.

## E. CHATGPT PROJECT

Distinguish:

CHATGPT_PROJECT_LOGICAL = the project concept/state tracked by this system.

CHATGPT_PROJECT_NATIVE = an actual Project object in the ChatGPT interface.

Never claim native creation without direct verification.

If native creation is not available through the current environment, report that fact. Do not simulate it.

## F. GITHUB INITIALIZATION

Create:

PROJECTS/<PROJECT-SLUG>/
    PROJECT.md
    RULES.md
    STATE.md
    MEMORY.md
    CHANGELOG.md
    REFERENCES/
    PROMPTS/
    SCENES/
    ASSETS/

PROJECT.md = identity and purpose.
RULES.md = approved project-specific rules only.
STATE.md = current stage/objective/task/open questions/references/recent changes/next priority.
MEMORY.md = durable project facts and decisions.
CHANGELOG.md = important project changes.

Use README.md placeholders only when a directory needs a tracked file to exist.

## G. MISSING INFORMATION

Never invent missing project information.

Use "NOT YET DEFINED" where appropriate.

## H. INITIAL STATUS

After successful GitHub initialization:

ACTIVE.

If only part of initialization succeeds, record the real partial state, e.g.:
ACTIVE — GITHUB_INITIALIZED
ACTIVE — CHATGPT_PROJECT_PENDING

## I. IDEMPOTENCY / RECOVERY

Before creating a project, verify that the target folder does not already exist.

If it exists:
- do not duplicate it;
- inspect its state;
- treat it as continuation/incomplete initialization as appropriate;
- repair only missing pieces;
- never overwrite established data without authorization.

## J. INITIALIZATION REPORT

Report only verified facts:
- Project name
- Project ID/slug
- GitHub path
- GitHub result
- ChatGPT Project native status
- Current status
- Files initialized
- Any unsupported/failed operation

## K. NO SECOND-COMMAND RULE

After explicit approval, do not separately ask permission for each supported initialization operation.

Execute what the environment actually supports.

Never simulate unsupported operations.
