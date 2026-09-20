# BA2-v1 — SAFE DELETE OPERATIONS POLICY

## Purpose
Define the safe deletion boundary for BA2-v1 GitHub project storage.

## Protected paths — never deletable through assistant/API operations
- `SYSTEM/**`
- `README.md`
- any repository file whose basename starts with `MASTER_`
- any repository file whose basename is `MASTER.md`
- any repository file explicitly marked `PROTECTED` by the system policy

These files may be manually deleted by the user in GitHub, but assistant/API delete operations must deny them.

## Deletable scope
- `PROJECTS/**`
- dedicated test files explicitly identified as test artifacts
- test branches such as `api-test*`, when a branch-delete operation is available

## deleteFile contract
Inputs:
- `path`
- `sha`
- `branch`
- `message`

Required checks:
1. Normalize the path.
2. Reject path traversal.
3. Reject any protected path.
4. Verify the current SHA.
5. Delete only the requested file.
6. Return the actual GitHub result.

## deleteBranch contract
Input:
- `branch`

Required checks:
1. Reject `main` and other protected branches.
2. Delete only the requested branch.
3. Return the actual GitHub result.

## deleteProject contract
Input:
- `project_path`
- `branch`
- `delete_registry_entry`

Required checks:
1. Project path must resolve strictly under `PROJECTS/<slug>/`.
2. Inspect the project tree before deletion.
3. Delete only project-scoped files.
4. Never touch `SYSTEM/**` or `README.md`.
5. Update the project registry only when requested and safe.
6. Verify resulting paths.

## deleteTestSet contract
Input:
- `scope`
- `branch`

Allowed scope:
- explicitly identified test artifacts or test branches only.

Never delete a production project as part of a test cleanup.

## Git History
A normal delete removes the file from the active branch tree; the file remains in GAT commit history. History purge is a separate, manual-only operation.

## Verification
Never report deletion success without a successful GitHub result and post-operation verification.
