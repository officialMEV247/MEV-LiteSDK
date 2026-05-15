# MEVEpoch.md
> MEV Lite SDK — Declaration File 05 of 11
> MEV Standard v1 · officialMEV.org

---

## MEV Epoch Declaration

This file formally declares the Logarithmic Milestone Formula, milestone scale,
Epoch types, Epoch Factor (Te) values, and the on-chain or off-chain Epoch
response mechanism for this implementation.

---

## Epoch Trigger Condition

```
MEV_total  >=  M(n)  →  Epoch_n  fires
```

When the accumulated MEV_total crosses milestone threshold M(n), Epoch n triggers.
This is a permanent, irreversible event — MEV_total never decreases.

---

## Logarithmic Milestone Formula

**Which formula type does this system use?**

- [ ] `M = k × bⁿ` — Dense coverage formula (k ∈ {1,5}, b = base, e.g. 10)
- [ ] `M(n) = log_b(n)` — Base-b logarithm
- [ ] `M(n) = a × log_b(n) + c` — Linear-log hybrid
- [ ] Custom monotonic sequence: [describe]

**Formula declaration:**

```
M  =  [your formula here]
```

**Parameters:**
| Parameter | Value | Description |
|-----------|-------|-------------|
| k         | [value or N/A] | Multiplier coefficient (for k×bⁿ formula) |
| b         | [value] | Base (e.g. 10) |
| n         | 0, 1, 2, 3... | Milestone index, starting at 0 |

---

## Milestone Scale

**First 12 milestones in this system:**

| Milestone n | Threshold M(n) |
|-------------|----------------|
| 0           | [value]        |
| 1           | [value]        |
| 2           | [value]        |
| 3           | [value]        |
| 4           | [value]        |
| 5           | [value]        |
| 6           | [value]        |
| 7           | [value]        |
| 8           | [value]        |
| 9           | [value]        |
| 10          | [value]        |
| 11          | [value]        |
| ...         | Infinite       |

**MEVU unit for milestones:** [e.g. MEZE tokens, learning credits, index points]

---

## Epoch Factor (Te)

Te is a phase modifier applied to MEVU generation within an Epoch period.
Te is NOT a per-transaction multiplier — it is a rate adjustment for the phase.

```
MEVU_epoch  =  A  ×  V  ×  Te
```

| Epoch Phase           | Te Range   | Description                              |
|-----------------------|------------|------------------------------------------|
| Genesis / Bootstrap   | 0.8 – 1.0  | Conservative baseline                    |
| Growth Phase          | 1.2 – 1.5  | Accelerated generation                   |
| Expansion Phase       | 1.5 – 2.0  | Network effect multiplier                |
| Critical Milestone    | 2.0+       | Peak incentive — landmark achievement    |

**Te values in this system:**

| Epoch n | Te value | Phase name    | Notes                  |
|---------|----------|---------------|------------------------|
| 0       | [value]  | [phase name]  | [any notes]            |
| 1       | [value]  | [phase name]  | [any notes]            |
| 2       | [value]  | [phase name]  | [any notes]            |
| ...     | ...      | ...           | Adopter-defined        |

---

## Epoch Response

**What happens when an Epoch fires in this system?**

- [ ] NFT minted commemorating the milestone
- [ ] Economic parameter recalibration (Te update)
- [ ] Governance trigger / vote enabled
- [ ] Reward phase change
- [ ] Public announcement / registry update
- [ ] Other: [describe]

**Epoch response mechanism:** [On-chain smart contract / Off-chain process / Both]
**Epoch response timing:** [Immediate on threshold crossing / Curated then executed]
**Who executes the Epoch response:** [Automated / Authorised operator / Governance]

---

## Epoch History Reference

[Link to on-chain explorer or off-chain record showing Epoch history, if available]

---

## Notes

[Any additional notes about Epoch design choices or future plans.]
