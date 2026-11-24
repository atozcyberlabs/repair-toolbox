# Repair Case Template

Use this to document a real repair after it's finished and verified. Copy the blank form into a new file in the [cases folder](../cases/), named after the case ID (for example `AZ-CASE-001.md`).

**Rules:**
- Only real repairs from our bench. Never publish an example or a guess as a case.
- No customer names, phone numbers, ticket numbers, serial numbers, IMEIs, or full logs.
- Use the short panic string only, with the actual sensor name.
- Pick a **confirmation level** honestly (see below). A strong clue isn't the same as an isolated failure.
- Tag every case using only the [tag list](#tag-list), so cases stay searchable.
- Status stays **Pending Review** until AJ reviews it. Only then does it become **Verified**.

---

## Blank form

```
# [Device]: [Problem]

Case ID:        AZ-CASE-[###]
Status:         Pending Review
Protocol used:  DP-[###] or DS-[###]
Device:         [Model]
Technician:     [Name]
Date:           [Month Year]
Symptom:        [What the customer and tech observed]

## Diagnostic evidence
1. [What you observed first]
2. [Panic string or error, exact sensor name]
3. [Test 1 and its result]
4. [Test 2 and its result]

## Finding
Evidence supports [part or cause] as the cause of the observed [symptom].

Confirmation level:  [Suspected / Supported / Isolated]
Original part:       [Retested / Inspected / Not retested] - [result]

## Repair performed
[What was replaced or fixed]

## Verification
- [Run time without the problem]
- [Charge test, with the actual result]
- [Panic logs checked after the repair]
- Post-repair checklist: [Passed / Failed items]

## Review
Reviewed by:   [AJ]
Review date:   [YYYY-MM-DD]
Final status:  [Verified / Needs more evidence]

## Tags
Device: [iphone-13]  Problem: [random-restarts]  Evidence: [panic-log, known-good-test]  Component: [charging-port-flex]  Category: [hardware-diagnostics]
```

---

## Example (illustrative only, not a real repair)

> This example shows how a finished case should read. It is not an AtoZ repair and is not counted as a verified case.

```
# iPhone 13: Random Restarts

Case ID:        EXAMPLE
Status:         Example only
Protocol used:  DP-001
Device:         iPhone 13
Technician:     AJ
Date:           November 2026
Symptom:        Restarts about every 3 minutes, including on the lock screen

## Diagnostic evidence
1. Device restarts every three minutes, including while on the lock screen.
2. Panic log reports "Missing sensor(s): [sensor name]".
3. Tested with a known-good battery. Restart issue persisted.
4. Tested with a known-good charging port flex. Restart issue stopped.

## Finding
Evidence supports a faulty charging port flex assembly as the cause
of the observed restarts.

Confirmation level:  Supported
Original part:       Not retested

## Repair performed
Replaced charging port flex assembly.

## Verification
- 30+ minutes of operation with no restarts.
- Charged from 20% to 100% with no restart.
- No new panic logs during verification.
- Post-repair checklist passed.

## Review
Reviewed by:   AJ
Review date:   [YYYY-MM-DD]
Final status:  Example only

## Tags
Device: iphone-13  Problem: random-restarts  Evidence: panic-log, known-good-test  Component: charging-port-flex  Category: hardware-diagnostics
```

To reach **Isolated**, the tech would also reinstall the original flex and see the restarts return, or find visible damage on it, and record that under "Original part."

---

## Confirmation levels

| Level | Meaning | Example |
|---|---|---|
| **Suspected** | Evidence points to a cause, but no part test has been done yet | Panic log names a sensor on the charging port flex |
| **Supported** | A known-good part made the symptom stop | Restarts stopped with a known-good charging port flex |
| **Isolated** | Supported, and the original part was proven faulty | The original flex was reinstalled and the restarts came back, or it shows visible damage |

Only **Supported** and **Isolated** cases can be marked Verified. A **Suspected** case stays Pending Review.

## Tag list

Use only these tags, lowercase with hyphens. To add a new tag, ask AJ so the list stays consistent.

| Group | Tags |
|---|---|
| Device | `iphone-8`, `iphone-13`, `iphone-14`, `iphone-15`, `iphone-16`, `iphone-17` (add model variants like `iphone-14-pro` as needed) |
| Problem | `random-restarts`, `no-power`, `charging`, `display-touch`, `battery-thermal`, `liquid-damage`, `camera-biometrics` |
| Evidence | `panic-log`, `known-good-test`, `visual-inspection`, `diagnostics-mode`, `customer-report` |
| Component | `battery`, `charging-port-flex`, `display`, `back-glass`, `logic-board`, `sensor-flex`, `camera`, `face-id`, `speaker`, `microphone` |
| Category | `hardware-diagnostics`, `software`, `board-level` |
