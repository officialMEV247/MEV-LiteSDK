# MEVOracle.md
> MEV Lite SDK — Declaration File 08 of 11
> MEV Standard v1 · officialMEV.org

---

## MEV Oracle Declaration

The MEV Oracle is the bridge between where Activity (A) occurs and where
MEVU is generated and recorded. This file formally declares the Oracle
operating mode and architecture for this implementation.

---

## Operating Mode

**Select the operating mode for this implementation:**

- [ ] **Off-Chain Only**
  No blockchain involved. Activity is verified and MEVU is recorded
  in an off-chain system (database, ledger, etc.). No on-chain settlement.
  *Best for: enterprises, education platforms, traditional institutions.*

- [ ] **On-Chain Only**
  Activity originates on-chain. Verification and MEVU issuance are
  handled natively by smart contracts on the blockchain.
  *Best for: DeFi protocols, native Web3 systems.*

- [ ] **Bridge (Oracle)**
  Activity originates off-chain. The Oracle captures, verifies, and
  commits verified activity to the blockchain for on-chain settlement.
  *Best for: real-world activity settling on-chain.*

**Selected mode:** [Off-Chain Only / On-Chain Only / Bridge]

---

## Bridge Mode Configuration (if applicable)

*Complete this section only if operating mode is Bridge.*

### Oracle Architecture

```
[Off-Chain Activity Source]
        ↓
[Oracle Capture Layer]
        ↓ (signed payload)
[On-Chain Verification]
        ↓
[MEVU Issuance]
```

### Oracle Identity

| Field | Value |
|-------|-------|
| Oracle name | [Your oracle name, e.g. OCEO] |
| Oracle type | [Centralised / Decentralised / Hybrid] |
| On-chain identifier | [e.g. Registered signing address, contract address] |
| Key storage | [e.g. HSM, Cloud KMS, Multi-party] |
| Key rotation mechanism | [e.g. Governance multisig transaction] |

### Signing Mechanism

**Signing standard:** [e.g. EIP-712 typed data, ECDSA, custom]
**What is signed:** [Describe the payload structure]
**Signature verification:** [On-chain / Off-chain / Both]

### Data Freshness Policy

**Maximum payload age:** [e.g. 5 minutes — payloads older than this are rejected]
**Freshness check enforcement:** [On-chain in verifier contract / Off-chain]
**Stale payload outcome:** [Rejected — MEVU not issued]

### Replay Protection

**Method:** [e.g. Processed event IDs permanently marked on-chain]
**Duplicate outcome:** [Rejected — second submission for same event ID fails]
**Replay protection scope:** [Per-event ID / Per-block / Other]

### Oracle Security Model

| Property | Description |
|----------|-------------|
| Cannot mint directly | Oracle only signs data — authorised roles submit to chain |
| Compromise recovery | Key rotation via [mechanism] |
| Single point of failure | [Yes / No — describe mitigation] |
| Operator | [Who operates the oracle?] |

---

## Off-Chain Only Configuration (if applicable)

*Complete this section only if operating mode is Off-Chain Only.*

| Field | Value |
|-------|-------|
| Accumulation system | [Database / Ledger / Other] |
| Verification system | [Describe] |
| Audit trail | [How is the accumulation record audited?] |
| Data export | [Can MEV_total be independently verified?] |

---

## On-Chain Only Configuration (if applicable)

*Complete this section only if operating mode is On-Chain Only.*

| Field | Value |
|-------|-------|
| Network | [Blockchain name] |
| Contract address | [0x...] |
| Verification logic | [On-chain — describe] |
| Activity source | [On-chain events / Transactions / Other] |

---

## Notes

[Any additional notes about Oracle design, security model, or future plans.]
