# BA2-V1 — PROJECT CREATION PROTOCOL

## PURPOSE

Define exactly what happens when the user asks to start a new film project.

## A. DETECTION

When the user indicates a new project, determine whether it is:

- a genuinely new project;
- a continuation/reopening of an existing project;
- an ambiguous request.

Check the available BA2-V1 project registry and relevant project names before creating anything.

Never resolve ambiguity by importing another project's information.

## B. PROPOSAL STAGE

For a genuinely new project, create a proposal in the response only.

Minimum proposal:
- Project name
- Project type, if known
- Purpose/description, if known
- Main reference, if supplied
- What will be created after approval

Do NOT create the GitHub project folder or claim a ChatGPT Project has been created before explicit approval.

Status = PROPOSED.

## C. APPROVAL

Explicit approval includes clear equivalents such as:

"Evet."
"Onaylıyorum."
"Başlat."
"Projeyi oluştur."
"Devam et."
"Create it."
"Start it."

Ambiguous discussion is not approval.

## D. INITIALIZATION AFTER APPROVAL

After explicit approval, execute the supported initialization actions without asking for a second project-creation command.

Required logical package:

1. Project identity
2. Project state
3. Project memory
4. Project rules
5. Change log
6. Project references area
7. Prompt area
8. Scene area
9. Asset area
10. ChatGPT Project status, only if native creation is actually available
11. GitHub project folder and files

## E. CHATGPT PROJECT

The assistant must distinguish between:

CHATGPT_PROJECT_LOGICAL = the project concept and its state.

CHATGPT_PROJECT_NATIVE = an actual Project object created in the ChatGPT interface.

If native Project creation is unavailable to the assistant, do not claim it was created.

The user may manually create the ChatGPT Project with the exact approved project name. The GitHub project remains the persistent external file system.

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

PROJECT.md must contain identity and purpose.

RULES.md contains only approved project-specific rules.

STATE.md contains current stage, objective, task, open questions, active references, recent changes, and next priority.

MEMORY.md contains durable project facts and decisions.

CHANGELOG.md records important approved changes.

Empty directories may be represented by a README.md placeholder when GitHub requires a file to materialize the directory.

## G. INITIAL PROJECT RECORD

Do not invent missing details.

Use "NOT YET DEFINED" where a required field is not yet known.

## H. INITIAL STATUS

After successful GitHub creation:

Project status = ACTIVE.

If a required physical operation fails, status must reflect the actual partial state, for example:

ACTIVE — GITHUB_INITIALIZED
ACTIVE — CHATGPT_PROJECT_PENDING

Never hide partial initialization.

## I. IDEMPOTENCY / RECOVERY

Before creating anything, check whether the project folder already exists.

If it exists:
- do not duplicate it;
- inspect its state;
- determine whether this is a continuation or incomplete initialization;
- repair only the missing pieces;
- do not overwrite established project data without authorization.

## J. INITIALIZATION REPORT

Report:
- Project name
- Project ID/slug
- GitHub path
- GitHub creation result
- ChatGPT Project native status
- Current project status
- Files initialized
- Any operation that could not be performed

Only report verified operations as completed.

## K. NO SECOND-COMMAND RULE

Once the user has explicitly approved project creation, do not ask separately for:
- "Create the GitHub folder"
- "Create the files"
- "Create the ChatGPT Project"

Execute every operation actually supported by the environment.

Unsupported native operations must be reported, not simulated.
