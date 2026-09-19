# BA2-V1 — CONTROLLED PROJECT CHANGE MANAGEMENT PROTOCOL

## PURPOSE

Protect established project decisions while allowing deliberate changes.

This protocol applies to established project rules, LOCKED rules, major decisions, authoritative references, character facts, story facts, visual rules, technical rules, prompt rules, and other durable project information.

## 1. CHANGE REQUEST DETECTION

Treat an instruction as a potential project change when it changes, replaces, cancels, locks, unlocks, or broadly redefines established project information.

Examples:
- "Bunu değiştirelim."
- "Eski kural artık geçerli değil."
- "Bundan sonra bunu kullan."
- "Bu karakter artık böyle."
- "Bu referansı artık kullanma."
- "Bu kuralı iptal et."
- "Her sahnede böyle olsun."

A request that affects only the current temporary task or shot is not automatically a durable project change.

## 2. CHANGE CLASSIFICATION

Classify the request before applying it:

- TEMPORARY: only this task/shot; do not alter durable project state.
- LOCAL: changes a defined scene/sequence/asset/reference only.
- GLOBAL: changes the project rule or fact across affected project areas.
- LOCKED-RULE CHANGE: attempts to replace or cancel a LOCKED item.
- REFERENCE CHANGE: replaces or invalidates an authoritative project reference.

Never infer GLOBAL scope from a LOCAL instruction.

## 3. IMPACT ANALYSIS

For a material LOCAL, GLOBAL, LOCKED-RULE, or REFERENCE change, determine:

- OLD STATE
- PROPOSED NEW STATE
- SCOPE
- AFFECTED AREAS
- CONFLICTING INFORMATION
- INFORMATION THAT MAY BECOME SUPERSEDED
- REQUIRED UPDATES
- CONTINUITY/LOGIC RISKS
- REQUIRED ACTIONS

## 4. APPROVAL GATE

Material durable changes require explicit user approval before activation.

Before approval:
- keep the old active state;
- do not mark the new state ACTIVE;
- do not rewrite project memory as final;
- do not invalidate the old decision;
- record the proposal under PENDING APPROVALS when persistence is needed.

Clear approval such as "evet", "onay", "uygula", "yap" or equivalent authorizes the proposed change when the proposal is unambiguous.

If approval is ambiguous, ask.

A clearly temporary/local instruction that does not alter a durable rule does not require a separate approval gate.

## 5. CHANGE PLAN

Before a material change, present a concise plan:

**DEĞİŞİKLİK TALEBİ**
- Eski durum:
- Yeni durum:
- Kapsam:
- Etkilenen alanlar:
- Geçersizleşebilecek bilgiler:
- Gerekli güncellemeler:
- Olası süreklilik/mantık etkileri:
- Gerekli işlem:

## 6. APPLY APPROVED CHANGE SYSTEMICALLY

After approval, update every affected project source that must remain consistent:

- PROJECT.md
- RULES.md
- STATE.md
- MEMORY.md
- SCENES/
- PROMPTS/
- REFERENCES/
- ASSETS/
- CHANGELOG.md

Do not modify unaffected information.

## 7. SUPERSEDE

When an approved change replaces an established item:

OLD ITEM → SUPERSEDED
NEW ITEM → ACTIVE

Record the superseded item with:
- identifier or description;
- previous state;
- replacement;
- date/stage when available;
- reason when provided;
- affected scope.

Superseded information must never be used as current project fact unless the user explicitly requests historical comparison or rollback.

## 8. CHANGE LOG

Every material approved change receives a logical record containing:
- Change ID;
- date/stage;
- scope;
- previous state;
- new state;
- reason, if provided;
- affected areas;
- implementation status.

## 9. LOCKED-RULE WARNING

If a user attempts to change a LOCKED item:
1. state that the item is LOCKED;
2. identify possible dependent information;
3. perform impact analysis;
4. request explicit approval;
5. only then apply the change.

Do not silently replace a LOCKED item.

## 10. CONFLICTING INSTRUCTIONS

If a new instruction conflicts with an active or locked project rule:
- do not silently delete the old rule;
- do not activate the new rule prematurely;
- do not keep contradictory facts simultaneously ACTIVE;
- invoke this change protocol when the conflict is durable/material.

## 11. ROLLBACK

Rollback is itself a controlled change.

Identify:
- current state;
- target previous state;
- affected areas;
- side effects;
- information that would become superseded again.

Request explicit approval before applying rollback.

After approval, restore the target state, record the rollback in CHANGELOG.md, and mark the displaced current state as SUPERSEDED where appropriate.

## 12. STATUS MODEL

Project information may be classified as:
- ACTIVE
- LOCKED
- SUPERSEDED
- TEMPORARY
- PROPOSED
- REFERENCE

These statuses must not be mixed.

## 13. CROSS-PROJECT CHANGES

A change in one project never changes another project automatically.

Cross-project transfer requires explicit authorization and must be recorded according to PROJECT_FIREWALL.md.

## 14. CAPABILITY HONESTY

Never claim a change was persisted, propagated, superseded, rolled back, or verified unless the corresponding GitHub operation actually succeeded.

