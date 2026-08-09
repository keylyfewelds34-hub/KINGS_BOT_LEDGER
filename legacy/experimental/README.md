# KINGS BOT — LEGACY EXPERIMENTAL AREA

## STATUS

QUARANTINED DEVELOPMENT AREA

Nothing in this directory is production KINGS BOT logic.

---

# PURPOSE

This directory is reserved for experimental work derived from concepts studied in the protected BetsAndThreats V6 reference.

All Legacy research implementations must begin here or in another explicitly approved experimental location.

---

# PROTECTED SOURCE

The protected original is located at:

`../ORIGINAL_V6_READ_ONLY.pine`

## NEVER MODIFY THE PROTECTED ORIGINAL.

Experimental work must use separate files.

---

# DEVELOPMENT RULES

1. Never modify `../ORIGINAL_V6_READ_ONLY.pine`.

2. Never use the protected original as a working file.

3. Python ports must be created as new experimental files.

4. Experimental Legacy logic must remain isolated from KINGS BOT production logic.

5. Experimental logic initially has ZERO authority over:
   - Calls
   - Entries
   - Confirmations
   - Flips
   - Exits
   - Settlement decisions

6. Do not modify `signal_engine.py` merely to test Legacy concepts.

7. Do not replace existing KINGS BOT data sources during initial testing.

8. Shadow-mode observations must be logged separately from production decisions.

9. Experimental findings must be documented in:

`../LEGACY_AUDIT.md`

10. Any proposed production integration requires:
    - Measured evidence
    - Regression testing
    - ChatGPT QA/QC review
    - Product Owner approval
    - New documented KINGS BOT checkpoint

---

# INITIAL EXPERIMENTAL PRINCIPLE

Observe first.

Measure second.

Compare third.

Integrate only if evidence supports it.

---

# CURRENT AUTHORIZATION

Allowed:

- Research
- Architecture analysis
- Logic comparison
- Shadow-engine development after approval
- Data logging
- Offline testing

Not authorized:

- Production signal changes
- Production flip changes
- Production entry changes
- Production settlement changes
- Replacement of protected KINGS BOT behavior

---

# CURRENT IMPLEMENTATION STATUS

No Legacy Shadow Engine implemented.

No hybrid engine implemented.

No V6-derived production logic implemented.

---

# END
