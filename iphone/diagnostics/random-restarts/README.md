# DP-001: iPhone Unexpected Restarts and Panic Logs

**AtoZ CyberLabs | Diagnostic Protocol 001**

| Document ID | Version | Applies to | Owner | Last reviewed |
|---|---|---|---|---|
| DP-001 | 1.0 | iPhone (see [model notes](../../models/)) | AJ | 2026-11-23 |

**Objective:** Identify the likely failure category through documented evidence before recommending any component replacement.

**Use this when:** the phone restarts on its own, boot loops, or restarts on a pattern (for example, every 3 minutes).

> **Safety stop:** a swollen, punctured, smoking, or very hot battery means stop and contact AJ before going any further.

Related pages: [Tools](tools.md) · [Videos](videos.md) · [Panic codes and references](panic-codes.md)

---

## Decision path

Answer each question in order. Write every answer in the [findings record](#findings-record) as you go.

### Q1. Has the device sustained physical damage or liquid exposure?

| Answer | Next step |
|---|---|
| **Yes, liquid** | Stop here and run [Liquid Damage](../liquid-damage.md) first. Liquid can cause restarts and will waste a part test. |
| **Yes, physical** (drop, bent frame, cracked back glass) | Note the damage in the ticket. A damaged back glass or bent frame can tear a flex cable, so keep it in mind at Q4. Go to Q2. |
| **No** | Go to Q2. |
| **Unknown** | Check the liquid contact indicator where accessible and inspect the charging port. Corrosion or a triggered indicator counts as **Yes, liquid**. Otherwise go to Q2. |

### Q2. Does the device reach the Home Screen before restarting?

| Answer | Next step |
|---|---|
| **Yes** | Go to Q3. |
| **No** (boot loops at the Apple logo) | You can't pull a log from Settings. Test with a known-good battery and a known-good charging port flex first, since both are common boot-loop causes. If it still loops, a software restore is next, but only after the customer agrees to possible data loss in the ticket. Still looping after restore: Stop and contact AJ. |

### Q3. Is a recent panic-full log available?

Customer unlocks the phone, then go to **Settings > Privacy & Security > Analytics & Improvements > Analytics Data** and look for files starting with `panic-full`.

| Answer | Next step |
|---|---|
| **Yes** | Pull it with the approved extractor ([tools.md](tools.md)) and go to Q4. |
| **No** | Restarts without panic logs often point to battery, power, or software. Check Battery Health, update iOS if the customer agrees, then watch the phone for 30 minutes, on and off the charger. If it restarts, test a known-good battery. |

### Q4. What does the panic string point to?

Read the panic string near the top of the log. Use the analyzer in [tools.md](tools.md), then confirm with the references in [panic-codes.md](panic-codes.md).

| Panic string contains | Likely category | Next step |
|---|---|---|
| `Missing sensor(s):` followed by a sensor name | A sensor that isn't reporting, usually on a flex cable | Look up the sensor name in the iFixit Kernel Panics reference. Go to Q5 and test the matching flex. |
| `thermalmonitord` | Often appears with a missing sensor | Look for a missing sensor in the same log and treat it the same way. Go to Q5. |
| `SMC PANIC - ASSERTION FAILED` with a 0x... value | A sensor array code that maps to a part, by model | Match the code to the exact model with the iFixit SMC Panic reference before choosing a part. Go to Q5. |
| Anything else, or nothing clear | Possible software or logic board fault | Update or restore software (with customer agreement). Still restarting: Stop and contact AJ. |

**Check the shop's own fixes first:** if the panic string is already in the shop-fix table in [panic-codes.md](panic-codes.md), start with what fixed it last time.

### Q5. Confirm with a known-good part (test before you replace)

| Result | Next step |
|---|---|
| **Restarts stop** with the test part | Replace the part. Run the phone 30 minutes including a charge cycle, confirm no new panic logs, then complete the [post-repair checklist](../../quality-checks/post-repair-checklist.md). |
| **Restarts continue** | Put the original part back. Go back to Q4 and check for a second sensor, or Stop and contact AJ. |

---

## Stop and contact AJ

Stop and message AJ on Discord if:

- The battery is swollen, punctured, smoking, or very hot
- The phone still loops or restarts after a software restore
- The panic points to the logic board, or no part test fixes it
- There's corrosion on the logic board

Include the device model, your findings record, and the steps you already tried. No customer details in Discord.

---

## Findings record

Copy this into the repair ticket and fill it in as you go.

```
DP-001 Findings
Device model:
Liquid / physical damage:  Yes (liquid) / Yes (physical) / No / Unknown
Reaches Home Screen:       Yes / No
Panic-full log available:  Yes / No
Panic string (short):
Likely category:
Known-good part tested:
Result:
Recommendation:
Technician / Date:
```

When the repair is confirmed, send the short panic string, model, and fix in team chat so it can be added to the shop-fix table as a verified case.

---

## Model-specific references

| Model | Reference |
|---|---|
| iPhone 14 | [Repair Wiki: How to Fix an iPhone 14 That Randomly Restarts](https://repair.wiki/w/How_To_Fix_an_iPhone_14_That_Randomly_Restarts) |
| All models | Apple repair manual for the exact model, linked from each [model page](../../models/) |

## Revision history

| Version | Date | Change | By |
|---|---|---|---|
| 1.0 | 2026-11-23 | First release as a diagnostic protocol | AJ |
