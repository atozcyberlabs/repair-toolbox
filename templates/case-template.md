# Repair Case Template

Use this to document a real repair after it's finished and verified. Copy the blank form into a new file in the [cases folder](../cases/), named after the case ID (for example `AZ-CASE-001.md`).

**Rules:**
- Only real repairs from our bench. Never publish an example or a guess as a case.
- No customer names, phone numbers, ticket numbers, serial numbers, IMEIs, or full logs.
- Use the short panic string only, with the actual sensor name.
- Status stays **Pending Review** until AJ reviews it. Only then does it become **Verified**.

---

## Blank form

```
# [Device]: [Problem]

Case ID:        AZ-CASE-[###]
Status:         Pending Review
Protocol used:  DP-[###]
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
```
