# BA2-v1 — SAFE DELETE OPERATIONS POLICY

## Purpose
Define the safe deletion boundary for BA2-v1 GitHub project storage.

## Protected paths — never deletable through ChatGPT/API operations
- `SYSTEM/**`
- root `README.md`
- any repository file whose basename starts with `MASTER_`
- any repository file whose basename is `MASTER.md`
- any repository file explicitly marked `PROTECTED` by system policy

These files may be manually deleted by the user directly in GitHub. They must never be deleted, removed, or overwritten by a ChatGPT-issued delete instruction or API delete operation.

## Root README rule
`README.md` at repository root is a permanent protected master/system file.
- ChatGPT must reject any request to delete it.
- Delete operations must return a protected-path error before calling GitHub.
- Restoration/maintenance writes are allowed when necessary to preserve the protected file.
- Permanent deletion is manual-only through GitHub UI.

## Deletable scope
- `PROJECTS/**`
- explicitly identified test artifacts
- test branches such as `api-test*`, when branch-delete is available

## deleteFile contract
Inputs:
- `path`
- `sha`
- `branch`
- `message`

Required checks:
1. Normalize the path.
2. Reject path traversal.
3. Reject every protected path, including root `README.md`.
4. Verify the current SHA.
5. Delete only the requested file.
6. Return the actual GitHub result.

## deleteBranch contract
Inputs:
- `branch`

Required checks:
1. Reject `main` and other protected branches.
2. Delete only the requested branch.
3. Return the actual GitHub result.

## deleteProject contract
Inputs:
- `project_path`
- `branch`
- `delete_registry_entry`

Required checks:
1. Project path must resolve strictly under `PROJECTS/<slug>/`.
2. Inspect project tree before deletion.
3. Delete only project-scoped files.
4. Never touch `SYSTEM/**` or root `README.md`.
5. Update the project registry only when requested and safe.
6. Verify resulting paths.

## deleteTestSet contract
Inputs:
- `scope`
- `branch`

Allowed scope:
- explicitly identified test artifacts
- explicitly identified test branches

Never delete a production project as part of test cleanup.

## Git history
A normal delete removes the file from the active branch tree but does not purge Git history. History purge is a separate manual-only operation.

## Verification
Never report deletion success without an actual successful GitHub result and post-operation verification.
