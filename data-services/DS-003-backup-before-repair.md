# DS-003: Backup Before Repair + Backup Setup

**AtoZ CyberLabs | Data Service 003**

| Document ID | Version | Applies to | Owner | Last reviewed |
|---|---|---|---|---|
| DS-003 | 0.1 (draft) | iPhone and Android | AJ | 2026-11-24 |

**Policy:** [POL-001](../policies/POL-001-data-services.md)

**Objective:** Back up the customer's data before any risky repair, and make sure every customer leaves with a working backup.

**Use this when:** the repair is on the risky list below, or at checkout for any customer who has no recent backup.

> **Our rule:** backups go to the customer's own account or their own drive. We don't keep backups for customers.

---

## When to offer it

Offer a backup **before** the repair if the job is any of these:

- Board work
- A battery swap on a swollen or damaged battery
- Liquid damage
- Anything that might need a restore later
- The phone is acting strangely and the customer has no backup

Offer **backup setup** at checkout to every customer who said "no backup" at intake.

---

## Part 1: Backup before repair

### Q1. Does the phone turn on and unlock?

| Answer | Next step |
|---|---|
| **Yes** | The customer unlocks it. Go to Q2. |
| **No** | You can't back it up yet. Note it in the ticket and follow [DS-001](DS-001-software-rescue.md) or [DS-002](DS-002-data-rescue-after-board-repair.md). |

### Q2. Pick a route

| Route | When to use it | How |
|---|---|---|
| **A. Customer's cloud** | iCloud or Google account with enough free space | **iPhone:** Settings > [their name] > iCloud > iCloud Backup > Back Up Now. **Android:** Settings > Google > Backup > Back up now (the exact menu names vary by brand). Wait until it shows today's time. |
| **B. Encrypted backup on the store computer** | Not enough cloud space | iPhone: Apple Devices app or Finder, tick **Encrypt local backup**, **the customer types the backup password**, then Back Up Now. This copy is temporary. |

### Q3. Confirm it worked

Check that the last backup shows today's date and time. Write it in the ticket. Then start the repair.

If you used **Route B**, delete the store copy after the customer confirms their phone and data are fine, and no later than [AJ: set number] days after pickup. Write "Store copy deleted" and the date in the ticket.

---

## Part 2: Backup setup at checkout

Walk the customer through this on their own phone. They tap, you guide.

1. **Turn on automatic backup.**
   iPhone: Settings > [their name] > iCloud > iCloud Backup > on.
   Android: Settings > Google > Backup > on.
2. **Check storage.** If their cloud storage is full, show them where it says so. Buying more storage is their choice. Don't push it.
3. **Run one backup now** and confirm it finished today.
4. **Tell them in one line:** "Your phone now backs itself up when it's charging, locked, and on Wi-Fi."

---

## Stop and contact AJ

Stop and message AJ on Discord if:

- The customer asks us to keep their backup for them
- A backup keeps failing and the repair is risky
- The phone shuts off or gets hot during the backup

Include the model and what you tried. No customer details in Discord.

---

## Findings record

```
DS-003 Findings
Device model:
Reason:                            Before risky repair / Checkout setup
Route used:                        A Cloud / B Store backup
Backup finished (date/time shown): Yes / No
Automatic backup turned on:        Yes / No / Already on
Store copy deleted (Route B):      Yes, date: ____ / Not needed
Technician / Date:
```

Tag the ticket `DS-BACKUP`.

## Revision history

| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | 2026-11-24 | First draft | AJ |
