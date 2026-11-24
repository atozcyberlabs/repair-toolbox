# DS-001: iPhone Software Rescue (Fix Without Wiping)

**AtoZ CyberLabs | Data Service 001**

| Document ID | Version | Applies to | Owner | Last reviewed |
|---|---|---|---|---|
| DS-001 | 0.1 (draft) | iPhone 8 and newer | AJ | 2026-11-24 |

**Policy:** [POL-001](../policies/POL-001-data-services.md)

**Objective:** Get a phone that is stuck in startup working again while keeping the customer's data.

**Use this when:** the phone is stuck on the Apple logo, shows the "connect to computer" screen, gets stuck during an update, or boot loops with no sign of liquid or physical damage.

**Not this guide:** a phone with no power at all ([No Power](../iphone/diagnostics/no-power.md)), a phone that restarts after reaching the Home Screen ([DP-001](../iphone/diagnostics/random-restarts/)), or liquid damage ([Liquid Damage](../iphone/diagnostics/liquid-damage.md)).

> **Golden rule:** **Update** keeps the data. **Restore** erases it. Always try Update first. Never Restore without the customer's written agreement in the ticket.

---

## Before you start

**Ask the customer:**
- What happened right before it got stuck? (update, drop, full storage, charging)
- Is the data important? Do they have a backup?
- Do they know their Apple ID and password? (A restored phone will ask for it.)

**Have ready:**
- Store computer with the Apple Devices app (Windows) or Finder (Mac), signed in to nothing
- A known-good cable plugged directly into the computer, not a hub
- The phone charged for at least 15 minutes

---

## Decision path

Write every answer in the [findings record](#findings-record) as you go.

### Q1. Any liquid or physical damage?

| Answer | Next step |
|---|---|
| **Yes** | Stop. Run [Liquid Damage](../iphone/diagnostics/liquid-damage.md) or note the damage, then come back. |
| **No** | Go to Q2. |

### Q2. Does a forced restart fix it?

Press and release **Volume Up**, press and release **Volume Down**, then hold the **Side button** until the Apple logo appears. Let go and wait 5 minutes.

| Result | Next step |
|---|---|
| **Reaches the Home Screen** | Done. Go to [After it boots](#after-it-boots). |
| **Still stuck** | Go to Q3. |

### Q3. Can the computer see the phone in recovery mode?

1. Connect the phone to the store computer.
2. Press and release **Volume Up**, press and release **Volume Down**, then hold the **Side button**. Keep holding past the Apple logo until the "connect to computer" screen appears.
3. The computer should show a message that the phone needs to be updated or restored.

| Result | Next step |
|---|---|
| **Computer shows Update / Restore** | Go to Q4. |
| **Computer does not see the phone** | Try another cable and USB port. Still nothing: this is likely hardware. Go to [Stop and contact AJ](#stop-and-contact-aj). |

### Q4. Choose **Update** (never Restore here)

1. Click **Update**. This reinstalls iOS and keeps the data.
2. Leave the phone and cable alone until it finishes.
3. If the phone leaves recovery mode before the download finishes (this can happen after about 15 minutes), put it back into recovery mode and click **Update** again.

| Result | Next step |
|---|---|
| **Phone boots to the Home Screen** | Go to [After it boots](#after-it-boots). |
| **Update fails or phone loops again** | Go to Q5. |

### Q5. Did the update fail more than twice?

Now the data is at risk. Do not go further on your own.

| Situation | Next step |
|---|---|
| **Customer has a backup and agrees in writing to erase** | You may click **Restore**. Note the agreement in the ticket first. After the restore, the customer signs in with their Apple ID. |
| **No backup, data matters** | Do not Restore. Stop and contact AJ. The phone may need board-level diagnosis before any software step. |

---

## After it boots

Do these before handing the phone back:

1. The customer unlocks the phone.
2. Offer [DS-003 Backup](DS-003-backup-before-repair.md). If the phone just got stuck, it can get stuck again.
3. Check storage. Almost full storage is a common reason updates get stuck. Point the customer to Settings > General > iPhone Storage.
4. Run the [post-repair checklist](../iphone/quality-checks/post-repair-checklist.md).
5. Tag the ticket `DS-SOFTWARE-RESCUE`.

---

## Stop and contact AJ

Stop and message AJ on Discord if:

- The computer cannot see the phone in recovery mode
- Update failed twice and the customer has no backup
- The phone gets hot, shows liquid signs, or loses power during the update
- The customer cannot prove the phone is theirs

Include the model, your findings record, and the steps you already tried. No customer details in Discord.

---

## Findings record

Copy this into the repair ticket and fill it in as you go.

```
DS-001 Findings
Device model:
What happened before it got stuck:
Data important / backup exists:   Yes / No  |  Yes / No
Liquid or physical damage:         Yes / No
Forced restart fixed it:           Yes / No
Seen in recovery mode:             Yes / No
Update result:                     Booted / Failed (times: )
Customer agreed to erase:          Yes / No / Not needed
Final result:
Backup offered (DS-003):           Yes / No
Technician / Date:
```

---

## Approved tools

<!-- AJ: add only tools you have approved for store computers. Name, link, and one line on when to use it. -->

| Tool | When to use it | Link |
|---|---|---|
| Apple Devices app (Windows) / Finder (Mac) | Q3 and Q4: recovery mode and Update | Built in / Microsoft Store |
| [AJ: add approved tool] | | |

## Revision history

| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | 2026-11-24 | First draft | AJ |
