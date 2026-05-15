# MEVU.md
> MEV Lite SDK — Declaration File 04 of 11
> MEV Standard v1 · officialMEV.org

---

## MEV Unit (MEVU) Declaration

This file formally declares how MEV Units (MEVU) are defined, generated,
and structured in this implementation.

---

## Core Formula

```
MEVU  =  A  ×  V
```

| Variable | Name         | Definition in this system                    |
|----------|--------------|-----------------------------------------------|
| A        | Activity     | [Define what A is — see MEVActivity.md]       |
| V        | Verification | [Define how V is calculated — range: 0 to 1]  |
| MEVU     | MEV Unit     | [Define what one MEVU represents in your system] |

---

## MEVU Form

**What physical or digital form does MEVU take in this system?**

- [ ] Native blockchain token
- [ ] Learning credit / educational credential
- [ ] Productivity index unit
- [ ] Civic contribution score
- [ ] Yield / reward primitive
- [ ] Off-chain ledger entry
- [ ] Other: [describe]

**MEVU name in this system:** [e.g. MEZE, YTC Credit, CivicPoint, or N/A if off-chain]
**Symbol (if applicable):** [e.g. MEZE, YTC]
**Decimals (if applicable):** [e.g. 18]

---

## Supply Model

**Supply type:**
- [ ] Adaptive / activity-driven (no fixed cap — supply grows with real activity)
- [ ] Fixed cap (maximum supply defined at genesis)
- [ ] Inflationary (scheduled issuance, not activity-driven)
- [ ] Hybrid: [describe]

**Supply cap (if applicable):** [Number or "None — adaptive"]
**Initial supply:** [Number or "0 — genesis from first verified activity"]

---

## Issuance Mechanism

**How are MEVU issued?**

[Describe the technical mechanism by which MEVU enter existence.
Examples:
- On-chain: smart contract mints tokens when a verified activity event is submitted
- Off-chain: ledger entry created when activity passes verification
- Hybrid: off-chain accumulation, periodic on-chain settlement]

**Issuance trigger:** [What event causes MEVU to be issued?]
**Issuance frequency:** [Per event / batched / periodic]
**Who can trigger issuance:** [Validator role / oracle / governance / automated]

---

## Verification Coefficient (V)

**How is V calculated in this system?**

[Describe how the verification score is determined.
V must be in the range [0, 1].
Examples:
- Binary: V = 1 if activity passes all verification checks; V = 0 if it fails
- Weighted: V = average of multiple sub-checks
- Cryptographic: V = 1 if EIP-712 signature valid, freshness check passes, no duplication]

**V range:** [ ] Binary (0 or 1)  [ ] Continuous [0, 1]  [ ] Other: [describe]
**V = 0 outcome:** [MEVU not issued — activity rejected]
**V = 1 outcome:** [Full MEVU issued — activity fully verified]

---

## MEVU Accumulation

```
MEV_total  =  Σ( A_i  ×  V_i )
```

**MEV_total tracking:** [On-chain contract / Off-chain database / Hybrid]
**Resets:** Never. MEV_total is monotonically non-decreasing.
**Reference:** See MEVMRSS.md for full accumulation rules.

---

## Notes

[Any additional notes about MEVU design choices, edge cases, or future plans.]
