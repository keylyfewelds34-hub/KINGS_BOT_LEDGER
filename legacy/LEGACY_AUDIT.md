# KINGS BOT — LEGACY V6 AUDIT

## STATUS

Research Only

No production integration authorized.

Original protected source:

`ORIGINAL_V6_READ_ONLY.pine`

---

# PURPOSE

Evaluate BetsAndThreats V6 against the existing KINGS BOT architecture.

The objective is to identify:

1. Logic KINGS BOT already contains.
2. Logic that is substantially similar.
3. Logic unique to BetsAndThreats V6.
4. Logic worth testing.
5. Logic that should NOT be ported.
6. Features that may improve early-entry awareness.
7. Features that may improve risk/reversion detection.

---

# AUDIT CLASSIFICATIONS

### ALREADY EXISTS
KINGS BOT already performs materially equivalent analysis.

### SIMILAR
KINGS BOT performs related analysis but implementation differs.

### UNIQUE
V6 provides analysis not currently represented in KINGS BOT.

### WORTH TESTING
Potential incremental value exists.

### DO NOT PORT
Potential duplication, conflict, excessive noise, or regression risk.

### PENDING
Insufficient evidence.

---

# PRELIMINARY V6 COMPONENT INVENTORY

## Weighted Multi-Exchange OHLC

Sources:
- Coinbase
- Kraken
- Gemini
- Crypto.com

Classification:

**WORTH TESTING**

Research question:

Does a weighted synthetic BTC candle provide useful information beyond KINGS BOT's existing BRTI and exchange data?

---

## WATCH UP / WATCH DOWN

Classification:

**HIGH-PRIORITY — WORTH TESTING**

Research question:

Can WATCH provide a reliable directional warning before the existing KINGS BOT confirmed call?

Primary metric:

Seconds of useful lead time.

---

## CONFIRM UP / CONFIRM DOWN

Classification:

**WORTH TESTING**

Research question:

Does V6 confirmation agree with KINGS BOT confirmation, and does agreement improve observed outcome quality?

---

## Candle Body Strength

Classification:

**WORTH TESTING**

Research question:

Does body strength help distinguish meaningful momentum from weak target crossings?

---

## EMA Slope

Classification:

**SIMILAR / WORTH COMPARING**

Research question:

Does the V6 EMA-state implementation add information not already captured by KINGS BOT?

---

## Jewel RSI / Stochastic Momentum

Classification:

**PENDING / WORTH TESTING**

Research question:

Does Jewel momentum provide incremental signal value after existing KINGS BOT variables are considered?

---

## Overextension Bands

Classification:

**WORTH TESTING**

Research question:

Can V6 overextension detection reduce late entries or momentum chasing?

---

## Early Reversion Engine

Inputs include:
- Deviation bands
- Wick rejection
- Early-cycle restriction

Classification:

**HIGH-PRIORITY — WORTH TESTING**

Research question:

Can this identify dangerous early-cycle reversions before KINGS BOT commits or flips?

---

## Standard Buy YES / NO

Classification:

**LIKELY OVERLAP**

Do not port before detailed KINGS BOT comparison.

---

## Aggressive Flip Logic

Classification:

**DO NOT PORT YET**

Reason:

KINGS BOT already contains protected flip behavior.

Introducing another flip authority could create contradictory calls and regressions.

---

## Strategy Execution / Pyramiding

Classification:

**DO NOT PORT**

Reason:

TradingView strategy execution is not the research objective.

KINGS BOT uses its own call lifecycle.

---

# SHADOW-STUDY CONCEPT

If approved after audit, an isolated Legacy Shadow Engine may observe live cycles.

It initially receives ZERO authority over production calls.

Potential observations:

- WATCH UP
- WATCH DOWN
- CONFIRM UP
- CONFIRM DOWN
- Body Strength
- EMA Direction
- Jewel State
- Overextension State
- Reversion Warning

---

# PROPOSED MEASUREMENTS

For every cycle:

- KINGS BOT first directional read
- KINGS BOT confirmed call
- KINGS BOT entry time
- Legacy WATCH direction
- Legacy WATCH time
- Legacy CONFIRM direction
- Legacy CONFIRM time
- Final Kalshi outcome
- Agreement/disagreement
- Seconds Legacy led or lagged KINGS BOT
- Reversion warning occurrence
- Whether reversion warning was useful
- Whether WATCH disappeared before confirmation

---

# CORE QUESTIONS

1. Does Legacy WATCH predict KINGS BOT's eventual call early?
2. How much earlier?
3. How often is early WATCH wrong?
4. Does Legacy CONFIRM improve confidence when both systems agree?
5. Are disagreements predictive of bad KINGS BOT calls?
6. Does the reversion engine identify avoidable losses?
7. Does overextension detection prevent poor late entries?
8. Does weighted exchange pricing add information beyond BRTI?
9. Does any V6 component measurably improve KINGS BOT?
10. If nothing adds measurable value, should integration be abandoned?

---

# PROMOTION RULE

No component is promoted because it sounds useful.

Promotion requires measured evidence.

Possible final roles include:

- Display-only context
- Early-warning indicator
- Confluence indicator
- Risk warning
- Entry timing aid
- No integration

Production signal authority requires a separate specification, QA/QC verification, and Product Owner approval.

---

# CURRENT AUDIT STATUS

PRESERVATION / PRE-TEST

No Codex port authorized yet.

No KINGS BOT production modification authorized.

---

# END AUDIT
