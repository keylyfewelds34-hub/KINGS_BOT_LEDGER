# KINGS BOT — MASTER DEVELOPMENT LEDGER

> Authoritative checkpoint record for KINGS BOT development.
>
> This ledger allows the Product Owner, ChatGPT QA/QC, Codex, and developers to identify known-good states, protected behavior, regressions, and current development work.
>
> **The repository is the technical source of truth.**

---

# DEVELOPMENT OPERATING SYSTEM

## Roles

### Product Owner
Responsible for:
- Deciding what KINGS BOT should do
- Defining desired features and behavior
- Setting development priorities
- Approving product direction

### ChatGPT — Systems Architect + QA/QC Engineer
Responsible for:
- Converting ideas into technical specifications
- Performing impact analysis
- Protecting existing functionality
- Preparing coding instructions for Codex
- Reviewing Codex changes
- Detecting regressions
- Approving or rejecting builds
- Maintaining development checkpoints

### Codex — Development Engineer
Responsible for:
- Reading this ledger before modifying code
- Inspecting the existing repository
- Implementing approved specifications
- Running syntax and available tests
- Checking affected call sites and dependencies
- Reporting every file changed and why
- Avoiding unrelated modifications
- Correcting builds rejected by QA/QC

---

# DEVELOPMENT PIPELINE

IDEA

↓

SPECIFICATION

↓

IMPACT ANALYSIS

↓

CODEX BUILD

↓

TEST

↓

CHATGPT QA/QC

↓

DEPLOY

↓

VERIFIED BASELINE

---

# CHECKPOINT RULES

Checkpoints represent meaningful, recoverable engineering states.

Do NOT create a checkpoint for every small code edit.

Create checkpoints when:
- A major subsystem becomes operational
- A significant feature is completed
- A major regression is repaired
- A version milestone is reached
- Architecture materially changes
- A stable deployment is verified

Primary numbering:

KB-000  
KB-010  
KB-020  
KB-030  
...

Ten-point increments leave room for intermediate checkpoints if repository history later reveals additional milestones.

---

# CHECKPOINT CONFIDENCE

**KB-000 through KB-090** are reconstructed historical checkpoints based on available development evidence.

They may not correspond to exact historical Git commits.

Do NOT invent commit hashes or exact dates for reconstructed checkpoints.

**KB-100 onward** has stronger direct development evidence.

Future verified checkpoints should include real Git commit information whenever available.

---

# PROTECTED CORE BEHAVIOR

Unless a specification explicitly authorizes a change, development must protect:

- Kalshi settlement-oriented architecture
- BRTI / settlement-index awareness
- 15-minute cycle tracking
- Signal calculations
- Entry logic
- Confirmation logic
- Flip logic
- Exit logic
- Whale detection
- Discord connectivity
- Discord alerts
- Cycle state
- Chart generation
- Record tracking
- Existing commands
- Backup behavior
- Dashboard behavior
- Asynchronous service supervision

## Critical Rule

**Display and presentation improvements must not silently modify trading/signal logic.**

Where practical, failure of one subsystem should not take unrelated subsystems down.

## Product Principle

**The call is the product. The picture is decoration.**

Charts and presentation systems support the callout system rather than control it.

---

# HISTORICAL CHECKPOINTS

## KB-000 — CONCEPT / BOT DIRECTION

**Status:** RECONSTRUCTED

KINGS BOT begins as Bitcoin/Kalshi analysis and signal tooling and develops toward a Discord-based prediction and callout system.

Core direction:
- Monitor Bitcoin
- Interpret Kalshi BTC markets
- Produce directional information
- Generate usable callouts
- Deliver information through Discord
- Build a repeatable real-time system

---

## KB-010 — SETTLEMENT-AWARE ARCHITECTURE

**Status:** RECONSTRUCTED

KINGS BOT becomes centered around how Kalshi's Bitcoin contracts actually settle rather than treating a generic BTC chart price as the deciding number.

Established principles:
- Settlement-aware analysis
- BRTI/index awareness
- Generic exchange price is not automatically the settlement authority
- Settlement behavior becomes protected architecture

---

## KB-020 — CORE CYCLE TRACKER

**Status:** RECONSTRUCTED

15-minute Kalshi cycle tracking becomes core infrastructure.

Established components include:
- Current ticker
- Strike
- Cycle timing
- Current cycle state
- Recurring 15-minute operation

Cycle state becomes shared infrastructure used by signals, charts, timers, Discord alerts, and settlement monitoring.

---

## KB-030 — SIGNAL ENGINE

**Status:** RECONSTRUCTED

Directional callout logic becomes a distinct operational subsystem.

Known behavior includes:
- UP/DOWN directional calls
- Entry guidance
- Confirmation behavior
- Flip behavior
- Exit guidance
- Overpriced-type guidance

### Protection

UI, chart, Discord, timer, logging, and dashboard work must not unintentionally alter signal calculations.

Changes to signal logic require their own specification and QA/QC.

---

## KB-040 — WHALE DETECTION

**Status:** RECONSTRUCTED

Whale/exchange-activity monitoring becomes a separate subsystem.

Historical development evidence includes exchange information from sources such as:
- Coinbase
- Kraken
- Bitstamp

Whale detection remains separable from the primary signal engine unless explicitly integrated by specification.

---

## KB-050 — DISCORD PRODUCT LAYER

**Status:** RECONSTRUCTED

Discord becomes the primary member-facing delivery system.

Known presentation includes:
- Cycle information
- Callouts
- Signal alerts
- Whale alerts
- Charts
- Commands
- Record information

Presentation systems should enhance KINGS BOT without destabilizing analytical systems.

---

## KB-060 — LIVE CHART

**Status:** RECONSTRUCTED

Live chart generation and Discord chart posting become operational.

Known components:
- PNG rendering
- Chart refresh loop
- Discord chart delivery
- Strike/cycle visualization

### Design Principle

**The call is the product; the picture is decoration.**

Chart failures should not intentionally prevent core callout delivery.

---

## KB-070 — MULTI-SERVICE RUNTIME

**Status:** RECONSTRUCTED

KINGS BOT operates through multiple asynchronous services.

Known services include:
- BRTI feed
- Cycle tracker
- Whale detector
- Signal loop
- Daily backup
- Live chart
- Dashboard

Independent services should remain independently supervised where practical.

---

## KB-080 — DASHBOARD + BACKUP

**Status:** RECONSTRUCTED

Dashboard/web functionality and daily backup become part of the primary runtime architecture.

Known components:
- Web/dashboard task
- Daily backup
- Runtime task orchestration

Later errors involving these systems should be treated as regressions unless repository evidence proves otherwise.

---

## KB-090 — KINGS BOT v2.6 MILESTONE

**Status:** MAJOR HISTORICAL PRODUCT MILESTONE

**Version:** 2.6

KINGS BOT v2.6 represents the major named product milestone preceding the current stabilization work.

Product characteristics include:
- Kalshi 15-minute BTC operation
- Settlement/index awareness
- Real-time calls
- Entry/exit guidance
- Signal explanation
- Whale information
- Chart support
- Discord delivery

Primary differentiator:

KINGS BOT is designed around the settlement process that determines the Kalshi outcome rather than treating a generic Bitcoin chart as final settlement authority.

---

# CURRENT-GENERATION DEVELOPMENT

## KB-100 — CYCLE TIMER / NEW-CYCLE PRESENTATION

**Status:** IMPLEMENTATION / INTEGRATION

Development begins on a live countdown and progress system for the NEW CYCLE Discord message.

### Intended behavior

The bot edits the **same NEW CYCLE message** instead of repeatedly posting new messages.

Target refresh:

**Approximately every 3 seconds.**

Display includes:
- Time remaining
- Cycle progress bar

### Critical Constraint

This feature is presentation-only.

It must not modify:
- Signal calculations
- Entry logic
- Confirmation logic
- Flip logic
- Exit logic
- Settlement logic
- Whale detection

---

## KB-110 — SCOPE / INDENTATION REGRESSION DEBUGGING

**Status:** HISTORICAL REGRESSION PERIOD

**Date:** August 8, 2026

Manual structural editing produced Python indentation and function-scope regressions.

Observed errors included:

- Expected indented block after `cycle_timer_loop()` definition
- Expected indented block after `while`
- `NameError: cycle_timer_loop is not defined`
- `NameError: chart_loop is not defined`
- `build_chart_file()` indentation/parser problems
- Accidental text corruption inside the `build_chart_file()` docstring

### Engineering Conclusion

These were integration/editing regressions.

They are not evidence that previously operational chart or cycle functionality never existed.

### Process Lesson

Structural Python editing through a small mobile editor creates unnecessary indentation and scope risk.

Repository-level development should move toward Codex.

---

## KB-120 — STRUCTURAL REPAIR BASELINE

**Status:** PENDING RUNTIME VERIFICATION

**Date:** August 8, 2026

Latest structural repair before transition to the new development operating system.

Visually restored to apparent module-level scope:

- `chart_loop()`
- `cycle_timer_loop()`
- `build_chart_file()`

Internal function indentation was repaired.

The corrupted `build_chart_file()` documentation text was also cleaned.

### Important

KB-120 is **not yet runtime-certified** solely because the source visually appears correct.

Previous Railway deployment evidence showed:

`NameError: chart_loop is not defined`

A deployment from the corrected source must successfully run before this checkpoint can be promoted to VERIFIED.

---

## KB-130 — DEVELOPMENT OS / CODEX TRANSITION

**Status:** CURRENT OPERATING MODEL

**Date:** August 8, 2026

KINGS BOT transitions from primarily conversational/manual editing to a structured engineering workflow.

### Roles

**Product Owner**  
Defines behavior and priorities.

**ChatGPT**  
Systems Architect + QA/QC Engineer.

**Codex**  
Development Engineer with repository visibility.

### Workflow

IDEA → SPEC → IMPACT ANALYSIS → CODEX BUILD → TEST → CHATGPT QA/QC → DEPLOY → BASELINE

### Repository Rule

The repository becomes the primary technical source of truth.

Screenshots remain useful for diagnosis but should not replace repository inspection when repository access is available.

### QA Rule

Compilation alone does not make a feature complete.

Verification should consider:
- Startup
- Runtime
- Intended feature behavior
- Protected-system behavior
- Signal integrity
- Regression risk

---

## KB-140 — LEGACY V6 PRESERVATION BASELINE

**Status:** VERIFIED

**Date:** August 9, 2026

### Objective
Preserve BetsAndThreats V6 as an immutable research reference before any Legacy Shadow or hybrid experimentation begins.

### Changes
- Created a protected V6 master reference and preservation rules.
- Preserved the original Pine v6 source as `legacy/ORIGINAL_V6_READ_ONLY.pine`.
- Created the Legacy V6 research audit framework.
- Created an isolated experimental quarantine area.
- Corrected malformed repository paths created during manual GitHub navigation.
- Removed the malformed duplicate V6 path after verifying the correct protected copy.
- Corrected the experimental README filename and removed the malformed duplicate.

### Files
- `legacy/MASTER_BETSANDTHREATS_V6.md`
- `legacy/ORIGINAL_V6_READ_ONLY.pine`
- `legacy/LEGACY_AUDIT.md`
- `legacy/experimental/README.md`

### Protected Systems Verified
- Original V6 source content preserved.
- Original V6 source remains separate from KINGS BOT production logic.
- Experimental Legacy work has zero production authority.
- No KINGS BOT signal, entry, confirmation, flip, exit, settlement, BRTI, whale, Discord, chart, backup, or dashboard logic was modified as part of this preservation checkpoint.

### QA Result
PASS.

Repository inspection confirmed the intended preservation structure and the original V6 Pine strategy declaration at the protected path. The malformed `.pinelegacy/` duplicate was removed. The malformed `openREADME.md` duplicate was replaced by the intended `legacy/experimental/README.md`.

### Known Issues
- `KB-120` remains pending runtime verification and is not promoted by this checkpoint.
- Legacy V6 has not yet been ported, shadow-tested, or granted production authority.

### Regression Risk
LOW

### Preservation Commits
- Original V6 preservation: `a6635b0eb59db094e4c694d1417d9932c108cf97`
- Correct protected V6 path created: `a3fbd7b1fa9636f9e21b0427acff4404345d9387`
- Malformed V6 path removed: `1187c26e3f1fbee90f38e682a88e2c10973b5d0f`
- Correct experimental README created: `8d580d6e4778d7cc7183f6a18d6e7eeb2d6d26b4`
- Malformed experimental README removed / final preservation state: `80a84b6edc6f6da42f6737460145fdc8695ce72a`

### Next Action
Design the Legacy Shadow Study specification before authorizing Codex to implement any V6-derived experimental logic.

---

# CURRENT ACTIVE WORK

### Feature
Legacy Shadow Study specification, while preserving the existing KINGS BOT runtime stabilization work.

### Intended Behavior
Evaluate selected V6 concepts in isolated shadow mode without granting them production signal authority.

### Technical State
KB-140 preservation baseline is VERIFIED. KB-120 remains pending runtime/deployment verification.

### Required Next Step
Define the Shadow Study inputs, outputs, comparison metrics, data boundaries, and Codex implementation instructions.

---

# KNOWN PROJECT COMPONENTS

Historical development evidence includes:

- `bot.py`
- `brti_feed.py`
- `kalshi_market.py`
- `signal_engine.py`
- `whale_feed.py`
- `cycle_log.py`
- `chart.py`
- `chart_image.py`
- `record.py`
- `requirements.txt`

Additional files may exist.

Always inspect the repository before assuming this list is complete.

---

# CODEX OPERATING INSTRUCTION

Before modifying KINGS BOT:

1. Read `KINGS_BOT_LEDGER.md`.
2. Identify the current baseline.
3. Inspect the existing implementation.
4. Identify systems affected by the requested change.
5. Preserve protected behavior unless explicitly authorized.
6. Do not refactor unrelated systems merely for style.

Before completing work:

1. Run Python syntax checks.
2. Inspect changed call sites.
3. Check function scope and imports.
4. Run available tests.
5. Perform reasonable startup/runtime checks.
6. Report every file changed.
7. Explain why each file changed.
8. Identify unresolved risks.
9. Do not claim runtime success without evidence.

---

# QA/QC CLASSIFICATIONS

## VERIFIED

Use when:
- Feature works as specified
- Required tests/checks pass
- Relevant protected systems show no regression
- No critical uncertainty remains

## CONDITIONAL PASS

Use when:
- Main implementation works
- A documented non-critical issue remains
- Deployment can reasonably continue

## REJECTED

Use when:
- Specification is not met
- Runtime is broken
- Protected behavior regresses
- Signal logic changes unintentionally
- Critical uncertainty remains

---

# FUTURE CHECKPOINT TEMPLATE

## KB-XXX — CHECKPOINT NAME

**Status:** VERIFIED / CONDITIONAL / PENDING / REJECTED

**Date:** YYYY-MM-DD

**Version:** If applicable

### Objective
Describe the objective.

### Changes
- Change
- Change

### Files Changed
- file
- file

### Protected Systems Verified
- System
- System

### QA Result
Describe verification performed.

### Known Issues
- Issue

### Regression Risk
LOW / MEDIUM / HIGH

### Commit
Add exact Git commit SHA when verified.

### Next Action
Describe next development action.

---

# CURRENT REFERENCE POINTS

**Current verified preservation checkpoint:**  
KB-140 — LEGACY V6 PRESERVATION BASELINE

**Current development operating checkpoint:**  
KB-130 — DEVELOPMENT OS / CODEX TRANSITION

**Current technical stabilization target:**  
KB-120 — STRUCTURAL REPAIR BASELINE

**Major historical product reference:**  
KB-090 — KINGS BOT v2.6 MILESTONE

**Next available major checkpoint:**  
KB-150

---

# END OF MASTER LEDGER
