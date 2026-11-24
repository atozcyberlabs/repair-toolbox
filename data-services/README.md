# Data Services

**AtoZ CyberLabs | Walk-in iPhone Data Retrieval**

| Section owner | Version | Applies to | Policy | Last reviewed |
|---|---|---|---|---|
| AJ | 0.4 (draft) | iPhone first, Android to follow | [POL-001](../policies/POL-001-data-services.md) | 2026-11-24 |

**Our rule:** we protect the customer's data before we erase, replace, or give up on any device.

These services help customers get back what matters to them: find it, copy it, protect it, or get the phone working long enough to save it. Every service follows the [Data Services Policy (POL-001)](../policies/POL-001-data-services.md).

---

## Service scope

**In scope:** the customer can unlock the phone, or can sign in to their own account or backup. Our team then finds the missing item, makes a copy they can open, or gets the phone working long enough for them to unlock it and save their data.

**Out of scope:**
- The customer can't unlock the phone and has no backup
- Getting past a passcode, Apple ID, Google account, or any other lock
- Digital forensics, legal evidence, or work for anyone other than the device owner

If a job falls outside this scope, stop and contact AJ.

---

## Intake question (same at both stores)

> **"What exactly do you need back, and can you unlock the phone for us?"**

Then ask:
1. Do you have a recent backup? (iCloud, Google, computer)
2. Do you know your Apple ID or Google password?

The customer enters their own passcode and passwords. Write the answers in the ticket.

---

## Services by level

Start at the lowest level that solves the customer's problem. Each level up takes more time, more tools, and more risk.

### Level 1: Find it (at the counter, no tools)

| # | Service | What the team does | Protocol |
|---|---|---|---|
| 1 | **Find My Missing Photos** | Search Photos with the customer. Check Recently Deleted (items stay about 30 days), Hidden, Shared Library, and iCloud Photos. If they received the photo, check the original message or app. | [DS-005](DS-005-photo-backup-transfer-help.md) |
| 2 | **Find Missing Files or Attachments** | Check Files, iCloud Drive, the original message thread, or the app they used. Export only the items they ask for. | Planned |

### Level 2: Copy it (store computer)

| # | Service | What the team does | Protocol |
|---|---|---|---|
| 3 | **Save My Photos & Videos** | Connect the unlocked phone, the customer taps **Trust**, import the requested photos and videos, and copy them to **the customer's drive**. Open a few files from the drive before handing it back. | [DS-005](DS-005-photo-backup-transfer-help.md) |
| 4 | **Encrypted Computer Backup** | Back up with Finder (Mac) or the Apple Devices app (Windows), on the customer's computer when possible. The customer sets and keeps the backup password. | [DS-003](DS-003-backup-before-repair.md) Route B |
| 5 | **Pull Specific Data From an Existing Backup** | Browse a compatible backup and export only what the customer needs, without restoring the whole thing. The customer needs the password for an encrypted backup. | **Pilot only.** Needs an approved tool. See [Launch plan](#launch-plan). |

### Level 3: Protect and move it

| # | Service | What the team does | Protocol |
|---|---|---|---|
| 6 | **Set Up & Verify My Backup** | Start an iCloud backup, check the last successful backup date, and check iCloud Photos separately if photos are what they care about. Show them where to check both next time. | [DS-005](DS-005-photo-backup-transfer-help.md), [DS-003](DS-003-backup-before-repair.md) |
| 7 | **Move My Data to a New iPhone** | Quick Start or an existing backup. The customer checks photos, contacts, and key apps on the new phone **before** the old one is erased or traded in. | [DS-004](DS-004-new-phone-migration.md) |
| 8 | **Restore a Backup to a Spare or Replacement Phone** | With the customer's approval, restore a known backup to a separate phone and check the items they need. Useful when the original phone is failing but a good backup exists. | Planned |

### Level 4: Get the phone working long enough

| # | Service | What the team does | Protocol |
|---|---|---|---|
| 9 | **Restore Usable Access** | When a stuck update, screen, or charging fault is the barrier, fix it without wiping: Update instead of Restore, or a known-good part. The customer unlocks it, then the team copies the priority data. | [DS-001](DS-001-software-rescue.md), [iPhone diagnostics](../iphone/) |
| 10 | **Board-Level Recovery to Backup** | When the board needs repair to boot, use our microsoldering. Once it's stable and the customer unlocks it, save the priority files first, then run a full backup if it stays stable. | [DS-002](DS-002-data-rescue-after-board-repair.md) |

> **Photos and backups are separate.** If iCloud Photos is on, the photos live in iCloud Photos, not in the iCloud device backup. Always check the specific photos the customer wants, not just that "a backup exists."

> **Restore erases.** Clicking Restore in recovery mode erases the phone. If the only copy of the data might be on the phone, stop before Restore. See [DS-001](DS-001-software-rescue.md).

---

## Launch plan

**Lead service: Photo, Backup & Transfer Help.** Three counter services for three different needs (find it, copy it, protect it), all in [DS-005](DS-005-photo-backup-transfer-help.md):

1. Find My Photos
2. Photo & Video Copy
3. Backup Setup & Check

Quote up front, give a pickup time, and agree on what happens if nothing is found, before any paid work.

**Two-week trial at both stores:** same three workflows, and every counter request logged in the [counter trial log](../templates/counter-trial-log.md): what they asked for, whether they accepted the quote, hands-on minutes, and what we handed back.

**Before the trial starts:** every tech practices on a **shop phone**, never a customer phone:
- A photo search (Recently Deleted, Hidden, Shared Library)
- A USB photo export to a drive, then opening the files to check them
- An iCloud backup check, including the last backup date and iCloud Photos

**Pilot before selling service #5:** test a backup-browsing tool with a known shop backup, and write down which file types the team can actually export. The tool must be approved and added to the toolbox before any customer job, as [POL-001](../policies/POL-001-data-services.md) requires.

**What the customer gets back:** for most people, a folder of actual photos and videos they can open is better than a backup file. Use a browsable backup only when you need to look through an older copy for something that's missing today.

---

## RepairDesk tags

| Level | Tag |
|---|---|
| Level 1: Find it | `DS-FIND` |
| Level 2: Copy it | `DS-COPY` |
| Level 3: Protect and move it | `DS-BACKUP` or `DS-MIGRATION` |
| Level 4: Software rescue | `DS-SOFTWARE-RESCUE` |
| Level 4: Board-level recovery | `DS-DATA-RESCUE` |

## Pricing

AJ sets prices. They're kept in RepairDesk, not in this public toolbox.

## Revision history

| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | 2026-11-24 | First draft: top 10 list, rules, DS-001 | AJ |
| 0.2 | 2026-11-24 | DS-002, DS-003, DS-004 drafted | AJ |
| 0.4 | 2026-11-24 | DS-005 Photo, Backup & Transfer Help and two-week trial log added | AJ |
| 0.3 | 2026-11-24 | Services regrouped into four levels; scope, intake question, launch plan, and POL-001 added | AJ |
