UNIVERSAL PINE BUILD MASTER BLUEPRINT
PREFILLED INSTANCE: ICT MSS SESSION ENTRY MODEL
LANGUAGE: Pine Script v6
MODE: AUDIT-FIRST -> COVERAGE-FIRST -> ZERO-ERROR EMISSION ONLY

==================================================
SECTION 0 — MASTER OPERATING LAW
==================================================

This document is the canonical build packet for Pine Script projects.

It serves four functions:
1. specification container
2. audit contract
3. coverage matrix source
4. final one-shot generation source

The generator must not improvise.
The generator must not emit code before coverage and risk closure.
The generator must not invent missing definitions.

If any logic-critical definition is unresolved, final code emission is blocked.

==================================================
SECTION 1 — UNIVERSAL PINE BUILD RULES
==================================================

These rules apply to all Pine builds generated from this master blueprint.

1. Pine version must be explicitly declared.
2. All identifiers must be declared before use.
3. No invalid Pine type declarations may be used.
4. Session logic must use explicit timezone handling.
5. Chart timezone must never be treated as logic truth.
6. Debug visuals must be optional and must never alter production logic.
7. Production visuals must be strictly limited to what the blueprint allows.
8. Missing logic definitions must never be silently invented.
9. No partial code emission is allowed.
10. Final code must compile with zero errors.
11. Code generation must follow dependency order.
12. Verification must occur both before and after code emission.

==================================================
SECTION 2 — UNIVERSAL BUILD PHASES
==================================================

Every Pine build must be processed in this order:

PHASE 1 — SPEC AUDIT
- Read the full blueprint.
- Extract all explicit requirements.
- Extract all implied dependencies.
- Detect all missing definitions.

PHASE 2 — CANONICAL BUILD NORMALIZATION
- Convert the blueprint into dependency-ordered implementation modules.

PHASE 3 — COVERAGE MATRIX
- Build a requirement coverage map.
- Mark every requirement as:
  - COVERED
  - PARTIAL
  - MISSING

PHASE 4 — ZERO-ERROR RISK AUDIT
Audit:
- compiler risks
- timezone risks
- reset risks
- state persistence risks
- geometry lifecycle risks
- production/debug contamination risks
- unresolved-definition risks

PHASE 5 — EMISSION GATE
Emit code only if:
- all logic-critical requirements are COVERED
- no logic-critical item remains MISSING
- no unresolved [ FILL THIS PART IN ] field blocks faithful implementation

PHASE 6 — FINAL CODE EMISSION
- Emit final Pine Script v6 code only.
- No placeholders.
- No partials.
- No speculative definitions.

==================================================
SECTION 3 — REQUIRED OUTPUT CONTRACT
==================================================

If unresolved logic-critical fields exist, output only:

1. BLUEPRINT AUDIT SUMMARY
2. REQUIREMENT COVERAGE MATRIX
3. BLOCKED ITEMS
4. MINIMUM REQUIRED FILLS
5. DO NOT EMIT CODE

If the blueprint is fully closed, output only:

1. BLUEPRINT AUDIT SUMMARY
2. REQUIREMENT COVERAGE MATRIX
3. ZERO-ERROR RISK AUDIT
4. FINAL IMPLEMENTATION NOTES
5. FINAL PINE SCRIPT V6 CODE

==================================================
SECTION 4 — REQUIREMENT COVERAGE MATRIX FORMAT
==================================================

Every requirement must be mapped as:

- ID
- Requirement
- Module Owner
- Status: COVERED / PARTIAL / MISSING
- Notes

Use requirement IDs grouped by:
- IDENTITY-#
- SESSION-#
- RANGE-#
- EXTERNAL-#
- SWEEP-#
- MSS-#
- PD-#
- POI-#
- VISUAL-#
- RESET-#
- RESTRICT-#
- VERIFY-#

==================================================
SECTION 5 — ZERO-ERROR RISK AUDIT FORMAT
==================================================

For each risk, output:

- Risk ID
- Description
- Status: CLOSED / OPEN
- Reason

If any logic-critical risk is OPEN, final code emission is blocked.

==================================================
SECTION 6 — UNIVERSAL REQUIRED INTERNAL MODULE ORDER
==================================================

All Pine builds must be normalized into this order:

1. compiler-safe shell
2. input layer
3. session engine
4. state/reset engine
5. range engine
6. event/freeze engine
7. trigger engine
8. confirmation engine
9. filter engine
10. object/zone engine
11. production visuals
12. debug layer
13. verification layer

==================================================
SECTION 7 — UNIVERSAL PLACEHOLDER LAW
==================================================

Any unresolved field must be preserved exactly as:

[ FILL THIS PART IN ]

The generator must:
- identify it
- classify whether it is cosmetic, debug-only, or logic-critical
- block code emission if it is logic-critical

==================================================
SECTION 8 — PREFILLED BUILD INSTANCE
==================================================

PROJECT: ICT MSS SESSION ENTRY MODEL
LANGUAGE: Pine Script v6
GOAL: Build a clean, minimal indicator that identifies high-probability ICT setups using Asian Kill Zone range, London + Asian liquidity comparison, external liquidity sweep, Market Structure Shift (MSS), New York Kill Zone execution, and POI filtering limited to FVG / IFVG / Order Block.

--------------------------------------------------
SECTION 8A — IDENTITY
--------------------------------------------------

- Project Name: ICT MSS SESSION ENTRY MODEL
- Script Type: Indicator
- Overlay: true
- Primary Logic Timezone: America/New_York
- Optional Display Timezone Inputs: [America/New_York, America/Los_Angeles]
- Build Intent: Production-grade indicator with optional isolated debug layer
- Core Output Type: Session structure + liquidity sweep + MSS + POI visualization
- Non-Goal: strategy orders, alerts, breaker blocks, clutter, prior-day carryover

--------------------------------------------------
SECTION 8B — SESSIONS
--------------------------------------------------

SESSION A
- Name: ASIA_KZ
- Display Name: ASIA_KZ
- Time: 20:00–00:00
- Timezone: America/New_York
- Track High: yes
- Track Low: yes
- Draw Box: yes
- Draw Lines: no
- Historical Box in Production: no
- Historical Box in Debug: [ FILL THIS PART IN ]
- Purpose: build Asian range for London comparison and external liquidity freeze

SESSION B
- Name: LONDON
- Display Name: LONDON
- Time: 00:00–05:00
- Timezone: America/New_York
- Track High: yes
- Track Low: yes
- Draw Box: no
- Draw Lines: no
- Historical Box in Production: no
- Historical Box in Debug: [ FILL THIS PART IN ]
- Purpose: track London high/low only

SESSION C
- Name: NEW_YORK_KZ
- Display Name: NEW_YORK_KZ
- Time: 07:00–11:00
- Timezone: America/New_York
- Track High/Low: [ FILL THIS PART IN ]
- Sweep Valid: yes
- MSS Valid: yes
- Setup Printing Valid: yes
- Draw Box in Production: no
- Draw Box in Debug: [ FILL THIS PART IN ]
- Purpose: execution window only

--------------------------------------------------
SECTION 8C — SESSION CONTRACT
--------------------------------------------------

- Session detection must be computed in America/New_York time
- Session logic must not depend on chart timezone
- ASIA_KZ runs from 20:00 to 00:00 NY
- LONDON runs from 00:00 to 05:00 NY
- NEW_YORK_KZ runs from 07:00 to 11:00 NY
- No sweep logic outside NEW_YORK_KZ
- No MSS logic outside NEW_YORK_KZ
- No setup printing outside NEW_YORK_KZ

--------------------------------------------------
SECTION 8D — STATE / RESET CONTRACT
--------------------------------------------------

- Reset Boundary: 00:00 America/New_York
- Reset Scope:
  - ASIA_KZ High/Low
  - LONDON High/Low
  - External High/Low
  - Sweep status
  - MSS tracking
- Carryover to next day: none
- Prior-day levels allowed: no
- Current day only: yes
- Model Day Convention: reset at 00:00 NY
- Internal anchoring note: [ FILL THIS PART IN ]

--------------------------------------------------
SECTION 8E — RANGE ENGINE
--------------------------------------------------

ASIA_KZ RANGE
- Birth Trigger: first bar entering ASIA_KZ
- Update Trigger: each bar while in ASIA_KZ
- Stored Values:
  - asiaHigh
  - asiaLow
- Production Visual:
  - one ASIA_KZ box only
- Completion Trigger: exit from ASIA_KZ

LONDON RANGE
- Birth Trigger: first bar entering LONDON
- Update Trigger: each bar while in LONDON
- Stored Values:
  - londonHigh
  - londonLow
- Production Visual:
  - none
- Completion Trigger: exit from LONDON

--------------------------------------------------
SECTION 8F — EXTERNAL LIQUIDITY ENGINE
--------------------------------------------------

- Freeze Trigger: 07:00 NY, at start of NEW_YORK_KZ
- External High Formula: max(asiaHigh, londonHigh)
- External Low Formula: min(asiaLow, londonLow)
- Production Visuals:
  - one horizontal External High line
  - one horizontal External Low line
- Extend Forward: yes
- Current Day Only: yes
- Stop Extending When:
  - swept
  - or new day starts at 00:00 NY

--------------------------------------------------
SECTION 8G — SWEEP ENGINE
--------------------------------------------------

- Valid Window: NEW_YORK_KZ only
- Preconditions:
  - externalHigh/externalLow already frozen
  - no valid prior sweep taken this day
- Sell Sweep Definition:
  - price sweeps above externalHigh
- Buy Sweep Definition:
  - price sweeps below externalLow
- Sweep Count Allowed Per Day:
  - first valid clean sweep only
- No Sweep Result:
  - no setup
- Required State After Sweep:
  - sweepDirection
  - sweepHigh
  - sweepLow
  - sweep timestamp / bar reference
- Sweep Source Tracking:
  - [ FILL THIS PART IN ]

--------------------------------------------------
SECTION 8H — MSS ENGINE
--------------------------------------------------

- Requires Sweep First: yes
- Valid Window: NEW_YORK_KZ only
- Logic Basis: existing pivot/BOS logic unchanged
- Sell MSS Meaning:
  - after sell-side sweep, bearish MSS
- Buy MSS Meaning:
  - after buy-side sweep, bullish MSS
- MSS Must:
  - occur after sweep
  - occur inside NEW_YORK_KZ
- Production Visual:
  - MSS lines only
- Exact pivot/BOS logic definition:
  - [ FILL THIS PART IN ]

--------------------------------------------------
SECTION 8I — PREMIUM / DISCOUNT ENGINE
--------------------------------------------------

- Defining Range:
  - from sweepHigh to sweepLow
- Sell Validity:
  - premium only
- Buy Validity:
  - discount only
- Midpoint Basis:
  - [ FILL THIS PART IN ]
- Production Visual:
  - none required unless explicitly added later

--------------------------------------------------
SECTION 8J — POI ENGINE
--------------------------------------------------

- Valid Only After:
  - sweep confirmed
  - MSS confirmed
  - premium/discount filter satisfied
- Allowed POI Types:
  - Order Block (OB)
  - FVG
  - IFVG
- Forbidden POI Types:
  - Breaker Block
- Multiple POIs Present:
  - mark all
- No POIs Present:
  - mark nothing
- Production Visual:
  - POIs only
- Exact Order Block definition:
  - [ FILL THIS PART IN ]
- Exact FVG definition:
  - [ FILL THIS PART IN ]
- Exact IFVG definition:
  - [ FILL THIS PART IN ]
- Internal POI precedence:
  - [ FILL THIS PART IN ]

--------------------------------------------------
SECTION 8K — VISUAL CONTRACT
--------------------------------------------------

PRODUCTION MUST SHOW ONLY:
- ASIA_KZ box
- External High line
- External Low line
- MSS lines
- POIs

PRODUCTION MUST NOT SHOW:
- London box
- extra labels
- debug plots
- previous-day levels
- clutter

DEBUG LAYER
- Allowed: yes
- Must be optional: yes
- Must default to hidden in final production build: yes
- May include:
  - witness table
  - optional historical session boxes
  - optional state table
- Must never alter production logic: yes
- Must never redefine blueprint semantics: yes
- Exact debug objects allowed:
  - [ FILL THIS PART IN ]

--------------------------------------------------
SECTION 8L — DAILY RESET CONTRACT
--------------------------------------------------

- Reset Time: 00:00 America/New_York
- Reset Items:
  - Asian range
  - London data
  - External liquidity
  - Sweep status
  - MSS tracking
- External lines deleted/reset at new day: yes
- No previous-day persistence: yes

--------------------------------------------------
SECTION 8M — RESTRICTIONS
--------------------------------------------------

- Only current day: yes
- No previous-day carryover: yes
- No signals outside NEW_YORK_KZ: yes
- Only first valid sweep: yes
- One sweep -> One MSS -> Clean setup: yes
- Do not invent unrequested visual layers: yes
- Do not show London production box: yes
- Do not show debug artifacts in production mode: yes

--------------------------------------------------
SECTION 8N — EXECUTION FLOW
--------------------------------------------------

1. Build ASIA_KZ range
2. Track LONDON high/low
3. At 07:00 NY define external liquidity
4. Wait for sweep
5. Wait for MSS
6. Apply premium/discount filter
7. Mark POI
8. Print clean setup

--------------------------------------------------
SECTION 8O — CORE LAW
--------------------------------------------------

- Core Rule: One sweep -> One MSS -> Clean setup

--------------------------------------------------
SECTION 8P — COMPILER / ENGINEERING RULES
--------------------------------------------------

- Pine Version: v6 only
- Must compile with zero errors
- Must not leave undeclared identifiers
- Must not use invalid type declarations
- Must not merge debug semantics with production semantics
- Must keep blueprint names exact:
  - ASIA_KZ
  - LONDON
  - NEW_YORK_KZ
- Must not introduce features not present in blueprint
- Must separate logic timezone from optional display timezone
- Must not depend on TradingView chart timezone for logic

--------------------------------------------------
SECTION 8Q — OPEN IMPLEMENTATION DETAILS REQUIRING EXPLICIT FILL BEFORE FINAL ONE-SHOT
--------------------------------------------------

- Existing pivot/BOS logic exact definition:
  - [ FILL THIS PART IN ]
- Exact Order Block definition:
  - [ FILL THIS PART IN ]
- Exact FVG definition:
  - [ FILL THIS PART IN ]
- Exact IFVG definition:
  - [ FILL THIS PART IN ]
- Whether debug historical boxes are desired during testing:
  - [ FILL THIS PART IN ]
- Whether witness/status tables are allowed during testing:
  - [ FILL THIS PART IN ]
- Final production defaults for debug toggles:
  - [ FILL THIS PART IN ]
- Exact debug table contents:
  - [ FILL THIS PART IN ]
- Exact production build name:
  - [ FILL THIS PART IN ]

==================================================
SECTION 9 — PRE-GENERATION COVERAGE CHECKLIST
==================================================

- Session windows explicitly defined: yes
- Reset boundary explicitly defined: yes
- External liquidity freeze explicitly defined: yes
- Sweep rules explicitly defined: yes
- MSS dependency explicitly defined: yes
- Premium/discount rule explicitly defined: yes
- POI inclusion/exclusion explicitly defined: yes
- Production visuals explicitly defined: yes
- Forbidden visuals explicitly defined: yes
- Current-day-only restriction explicitly defined: yes
- Core law explicitly defined: yes
- Missing precise sub-definitions:
  - pivot/BOS logic
  - Order Block
  - FVG
  - IFVG
  - debug permissions/details
  - midpoint rule wording if exact formula required

==================================================
SECTION 10 — POST-GENERATION VERIFICATION CHECKLIST
==================================================

- Script compiles with zero errors
- ASIA_KZ detected only from 20:00–00:00 NY
- LONDON detected only from 00:00–05:00 NY
- NEW_YORK_KZ detected only from 07:00–11:00 NY
- ASIA_KZ box appears in production
- LONDON box does not appear in production
- External high/low freeze at 07:00 NY
- External lines extend forward and stop on sweep or new day
- Sweep valid only inside NEW_YORK_KZ
- MSS valid only after sweep and inside NEW_YORK_KZ
- Premium/discount filter enforced
- Only OB/FVG/IFVG POIs marked
- Breaker blocks never marked
- No previous-day carryover visible
- One sweep -> One MSS -> one clean setup enforced
- Debug layer hidden by default in production:
  - [ FILL THIS PART IN ]

==================================================
SECTION 11 — ONE-SHOT GENERATION DIRECTIVE
==================================================

You are generating a Pine Script v6 indicator from this locked build packet.

You must process it in this exact order:

PHASE 1 — BLUEPRINT AUDIT
- Read the full build packet.
- Extract all requirements.
- Identify all [ FILL THIS PART IN ] fields.
- Classify each unresolved field as:
  - cosmetic
  - debug-only
  - logic-critical

PHASE 2 — REQUIREMENT COVERAGE MATRIX
- Build a requirement matrix.
- Mark each requirement:
  - COVERED
  - PARTIAL
  - MISSING

PHASE 3 — ZERO-ERROR RISK AUDIT
Audit:
- compiler risks
- timezone risks
- reset risks
- state persistence risks
- geometry lifecycle risks
- production/debug contamination risks
- unresolved-definition risks

PHASE 4 — EMISSION GATE
If any logic-critical [ FILL THIS PART IN ] field remains unresolved:
- do not emit code
- output:
  1. BLUEPRINT AUDIT SUMMARY
  2. REQUIREMENT COVERAGE MATRIX
  3. BLOCKED ITEMS
  4. MINIMUM REQUIRED FILLS
  5. DO NOT EMIT CODE

Only if all logic-critical fields are resolved may you emit:
1. BLUEPRINT AUDIT SUMMARY
2. REQUIREMENT COVERAGE MATRIX
3. ZERO-ERROR RISK AUDIT
4. FINAL IMPLEMENTATION NOTES
5. FINAL PINE SCRIPT V6 CODE

HARD RULES:
- Do not invent missing OB/FVG/IFVG definitions.
- Do not invent pivot/BOS logic.
- Do not reinterpret session windows.
- Do not use chart timezone as logic source.
- Do not emit partial code.
- Do not add unrequested features.
- Do not merge debug and production semantics.
- Keep blueprint names exact.
