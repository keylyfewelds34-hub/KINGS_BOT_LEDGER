# KINGS BOT — KNOWN PRE-LEGACY REGRESSIONS

## STATUS

PRESERVED UNFINISHED / BROKEN AREAS

Before Legacy/V6 experimentation, KINGS BOT was still under active development and had documented runtime/structural regressions.

Known examples included:

- `IndentationError` after function definitions
- `IndentationError` after `while` blocks
- `NameError: chart_loop is not defined`
- `NameError: cycle_timer_loop is not defined`
- `NameError: web is not defined`
- Parser/indentation problems around `build_chart_file()`
- Accidental text corruption inside a chart-building docstring
- Runtime verification still pending after structural repair

---

## INTERPRETATION

These regressions do not erase earlier evidence that charting, cycle tracking, whale monitoring, BRTI connectivity, and Discord delivery had operated.

They do establish that the bot was not a completed, fully verified production release at the point this baseline was frozen.

---

## PROTECTION RULE

Legacy/V6 experiments must not be used as an excuse to silently repair, replace, or reinterpret these pre-existing regressions inside protected historical areas.

Repairs belong in a separately scoped development effort with their own QA/QC and checkpoint.

---

# END
