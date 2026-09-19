# CHANGELOG

## 2026-09-19 — PROJECT CREATION

- Status: ACTIVE
- Change: Created initial BA2-V1 test project.
- Purpose: Validate physical GitHub project initialization.
- Verification: GitHub folder and core files created successfully.
- ChatGPT Project native creation: NOT VERIFIED.


## 2026-09-20 — BA2-V1 REGRESSION REPAIR + RETEST

- Scope: Correct all previously identified PARTIAL/FAIL migration gaps from the BA2-V1 regression tests.
- Added: SYSTEM/CHANGE_MANAGEMENT_PROTOCOL.md
- Added: SYSTEM/REFERENCE_FIDELITY_PROTOCOL.md
- Integrated both protocols into MASTER_FILM_ASSISTANT_OS.md and PROJECT_FIREWALL.md.
- Extended PROJECT_STATE_SCHEMA.md with change-management and reference-fidelity state.
- Corrected Master OS section numbering after protocol integration.

### Retest scenarios

- Material project rule change requires change classification, impact analysis, change plan, and explicit approval: PASS.
- Unapproved change leaves old state active and new state proposed: PASS.
- Local scene change does not become global: PASS.
- Global change propagates only to affected project sources: PASS.
- LOCKED rule change triggers warning, impact analysis, and approval: PASS.
- Approved replacement marks old information SUPERSEDED and new information ACTIVE: PASS.
- SUPERSEDED information is excluded from current-state use: PASS.
- Rollback is treated as a controlled change requiring approval: PASS.
- Reference replacement follows the change protocol: PASS.
- Authoritative reference uses change-only/minimum-intervention behavior: PASS.
- Shot reset prevents previous-shot camera/lens/lighting/action/wardrobe carryover unless reactivated: PASS.
- Cross-project change remains isolated: PASS.
- Prompt request remains prompt-only; generation requires explicit generation request: PASS.
- Multi-project concurrency and firewall behavior remain intact after repair: PASS.

### Retest conclusion

All previously identified PARTIAL/FAIL areas are now covered by explicit BA2-V1 protocols and passed the targeted regression scenarios.
