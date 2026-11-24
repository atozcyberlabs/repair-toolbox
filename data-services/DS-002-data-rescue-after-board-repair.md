# DS-002: Data Rescue After Board Repair

**AtoZ CyberLabs | Data Service 002**

| Document ID | Version | Applies to | Owner | Last reviewed |
|---|---|---|---|---|
| DS-002 | 0.1 (draft) | iPhone 8 and newer | AJ | 2026-11-24 |

**Policy:** [POL-001](../policies/POL-001-data-services.md)

**Objective:** As soon as a repaired board boots, move the customer's data somewhere safe before anything else is tested or replaced.

**Use this when:** a phone that was dead or boot looping now boots after board work, and the customer wants their data.

> **Golden rule:** a board that just came back may not stay up. **Data comes off first. Testing comes after.**

> **Why the customer must be there:** the data on an iPhone is locked to that phone and its passcode. Only the customer can unlock it. If the customer doesn't know the passcode, the data can't be recovered, and we never try to get around a passcode.

---

## Before you start

**Ask the customer:**
- Which data matters most? (photos, messages, contacts, work files)
- Do they have iCloud, and how much space is free?
- Do they have a new phone the data should go to?

**Have ready:**
- The phone on a charger the whole time
- Store computer with the Apple Devices app (Windows) or Finder (Mac)
- A known-good cable plugged directly into the computer

---

## Decision path

Write every answer in the [findings record](#findings-record) as you go.

### Q1. Is the phone stable enough to start?

Let it sit on the charger at the Home Screen or lock screen for 2 minutes.

| Result | Next step |
|---|---|
| **Stays on** | Go to Q2. |
| **Restarts or shuts off** | Don't keep power cycling it. Each restart is a risk. Stop and contact AJ. |

### Q2. The customer unlocks the phone

The customer enters the passcode themselves. Don't ask for it and don't write it down.

| Result | Next step |
|---|---|
| **Unlocked** | Go to Q3. |
| **Customer doesn't know the passcode** | Stop. Explain that the data is locked to the passcode and can't be recovered without it. Note it in the ticket. |

### Q3. Pick the safest route for the data

Use the first route that works for this customer.

| Route | When to use it | How |
|---|---|---|
| **A. Customer's iCloud** | They have iCloud with enough free space, and the store Wi-Fi works | Settings > [their name] > iCloud > iCloud Backup > **Back Up Now**. Wait until it shows today's time under the last backup. |
| **B. Straight to a new phone** | They have a new iPhone with them | Run [DS-004](DS-004-new-phone-migration.md), Quick Start route. |
| **C. Encrypted backup on the store computer** | No iCloud space and no new phone yet | Connect to the store computer. The customer taps **Trust** and enters the passcode. In the Apple Devices app or Finder, tick **Encrypt local backup**. **The customer types the backup password.** Then click **Back Up Now**. |
| **D. Photos only, to the customer's own drive** | Only photos matter, and they brought a drive | Import the photos with an approved tool onto **their** drive. Never keep a copy on the store computer. |

### Q4. Did the copy finish?

| Result | Next step |
|---|---|
| **Finished** | Go to [Customer check](#customer-check). |
| **Phone shut off during the copy** | Don't start over right away. Let it cool, put it back on the charger, and try once more. Shut off again: Stop and contact AJ. |

---

## Customer check

Before testing anything else or closing the job:

1. The customer opens their photos and messages on the destination (iCloud, new phone, or restored backup) and confirms the important items are there.
2. Write "Customer confirmed data" in the ticket.
3. Now finish the board repair testing and run the [post-repair checklist](../iphone/quality-checks/post-repair-checklist.md).
4. Offer [DS-003 backup setup](DS-003-backup-before-repair.md) so this doesn't happen again.
5. Tag the ticket `DS-DATA-RESCUE`.

## Data handling and deletion

- If you used **Route C**, the backup on the store computer is temporary. Once the customer confirms their data is on their own device or account, delete it: Apple Devices app or Finder > Manage Backups > select the backup > Delete.
- Delete it no later than [AJ: set number] days after pickup, even if the customer doesn't come back.
- Write "Store copy deleted" and the date in the ticket.

---

## Stop and contact AJ

Stop and message AJ on Discord if:

- The phone restarts or shuts off more than once during the rescue
- The phone gets hot while copying
- The customer can't prove the phone is theirs
- Anyone asks you to get past a passcode or account lock

Include the model, your findings record, and the steps you already tried. No customer details in Discord.

---

## Findings record

Copy this into the repair ticket and fill it in as you go.

```
DS-002 Findings
Device model:
Board repair done:                 (short description)
Stable on charger 2 minutes:       Yes / No
Customer unlocked phone:           Yes / No
Route used:                        A iCloud / B New phone / C Store backup / D Photos to drive
Copy finished:                     Yes / No
Customer confirmed data:           Yes / No
Store copy deleted (Route C):      Yes, date: ____ / Not needed
Backup setup offered (DS-003):     Yes / No
Technician / Date:
```

## Revision history

| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | 2026-11-24 | First draft | AJ |
