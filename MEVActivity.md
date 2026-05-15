# MEVActivity.md
> MEV Lite SDK — Declaration File 09 of 11
> MEV Standard v1 · officialMEV.org

---

## MEV Activity Declaration

This file formally defines what constitutes a valid Activity event (A) in
this implementation. Activity is the origin of all economic value in any
MEV-compliant system. No MEVU is generated without a valid, verified Activity.

---

## Activity Definition

**Formal definition of Activity in this system:**

> [Write a precise, unambiguous formal definition of what constitutes a valid
> Activity event in your system. This is your canonical reference document —
> write it as you would a specification, not a description.]

---

## Activity Categories

**How many categories of Activity does this system recognise?**

| Category ID | Category Name | Description | A value method |
|-------------|---------------|-------------|----------------|
| [CAT-001]   | [Name]        | [Description of this type of activity] | [How A is calculated] |
| [CAT-002]   | [Name]        | [Description] | [How A is calculated] |
| [CAT-003]   | [Name]        | [Description] | [How A is calculated] |

---

## Activity Value (A) Calculation

**How is the numeric value of A determined for each activity event?**

[Describe the formula or method used to assign a numeric value to each
Activity event. Examples:
- A = transaction amount in normalised base currency
- A = 1 (binary — all valid activities have equal weight)
- A = percentage of task completion × difficulty rating
- A = infrastructure uptime hours × load factor]

**A unit:** [What unit is A expressed in? e.g. USD equivalent, tokens, points, hours]
**A normalisation:** [Is raw A normalised before use? Describe the process.]
**A range:** [Minimum A value] to [Maximum A value per event, if capped]

---

## Activity Data Sources

**Where does Activity data originate?**

| Source ID | Source Name | Data Type | Integration Method |
|-----------|-------------|-----------|-------------------|
| [SRC-001] | [e.g. Payment processor] | [e.g. Settled transaction] | [e.g. Webhook, API, on-chain event] |
| [SRC-002] | [e.g. Learning system] | [e.g. Course completion event] | [e.g. LMS webhook] |

**Data freshness requirement:** [Maximum acceptable age of activity data]
**Settlement requirement:** [Must activity be fully settled before it counts?]

---

## Activity Exclusions

**The following do NOT constitute valid Activity in this system:**

| Exclusion | Reason |
|-----------|--------|
| [e.g. Test / sandbox transactions] | [Not real economic activity] |
| [e.g. Refunded or reversed events] | [Economic value was not retained] |
| [e.g. Duplicate submissions] | [Same event already processed] |
| [e.g. Self-activity / wash events] | [No genuine external economic activity] |
| [e.g. Events below minimum threshold] | [Below minimum A value] |

---

## Activity Lifecycle

```
Activity occurs
      ↓
Activity data captured by [source/oracle]
      ↓
Activity submitted for verification
      ↓
Verification checks applied (see MEVMRSS.md)
      ↓
V assigned (0 = rejected, >0 = accepted)
      ↓
MEVU = A × V generated (if V > 0)
      ↓
MEV_total updated
```

---

## Activity Record

**How are Activity records stored and audited?**

| Property | Value |
|----------|-------|
| Storage location | [On-chain / Database / Both] |
| Immutability | [Immutable on-chain / Append-only database / Other] |
| Audit access | [Public / Permissioned / Internal only] |
| Retention period | [Permanent / [n] years / Other] |

---

## Notes

[Any additional notes about Activity definitions, edge cases, or future activity types.]
