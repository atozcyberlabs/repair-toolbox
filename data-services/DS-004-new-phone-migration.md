# DS-004: New Phone Setup + Migration

**AtoZ CyberLabs | Data Service 004**

| Document ID | Version | Applies to | Owner | Last reviewed |
|---|---|---|---|---|
| DS-004 | 0.1 (draft) | iPhone to iPhone, Android to iPhone, Android to Android | AJ | 2026-11-24 |

**Policy:** [POL-001](../policies/POL-001-data-services.md)

**Objective:** The customer walks out with a new phone that has their data, their apps, and their sign-ins working, and the old phone still untouched until they say it's OK.

**Use this when:** a customer buys or brings in a new phone and wants everything moved over.

> **Golden rule:** **never erase the old phone** until the customer has checked the new one and said yes.

---

## Before you start

**Ask the customer:**
- Does the old phone turn on and unlock? (If not, start with [DS-001](DS-001-software-rescue.md) or [DS-002](DS-002-data-rescue-after-board-repair.md).)
- Do they know their Apple ID or Google password?
- Do they use apps that move separately, like WhatsApp, banking apps, or a code app for two-step sign-in?
- Is their phone service on a physical SIM or an eSIM?

**Have ready:**
- Both phones charged above 50 percent
- Store Wi-Fi working
- Enough free storage on the new phone for the old phone's data

---

## Decision path

### Q1. Which kind of move is it?

| Move | Route | How |
|---|---|---|
| **iPhone to iPhone** | **Quick Start** | Turn on the new iPhone and set it next to the old one with Bluetooth on. Follow the prompts. When asked, choose to transfer directly from the old iPhone. |
| **Android to iPhone** | **Move to iOS** | On the new iPhone, during setup, choose to move data from Android. Install Apple's Move to iOS app on the Android phone and enter the code shown on the iPhone. |
| **Android to Android** | **Built-in setup copy** | Turn on the new phone and follow the setup prompts to copy from the old phone, by cable or wirelessly. Samsung phones can use Samsung's own transfer app. |

### Q2. Did the transfer finish?

| Result | Next step |
|---|---|
| **Finished** | Go to Q3. |
| **Failed or stuck** | Restart both phones and try once more. Still failing: try the other method (cable instead of wireless, or a fresh backup and restore). Then Stop and contact AJ. |

### Q3. Move the things that don't move on their own

Go through this list with the customer:

| Item | What to do |
|---|---|
| **WhatsApp chats** | Use WhatsApp's own chat transfer, or its backup and restore, during setup. |
| **Two-step sign-in codes** (code apps) | Check that the code app works on the new phone **before** the old phone is erased. If it doesn't, the customer could get locked out of their accounts. |
| **Banking apps** | The customer signs in again themselves. Some banks need a text or email check. |
| **eSIM / phone service** | Transfer through the phone's setup prompts or the carrier. Make a test call before they leave. |

---

## Customer check before handoff

The customer checks these on the new phone and says yes to each:

1. Photos are there
2. Messages and contacts are there
3. The apps they use most open and sign in
4. Code apps for two-step sign-in work
5. Calls and texts work

Only then ask: "Do you want us to erase the old phone for you?" If yes, sign it out of their account first, then erase it. Write it in the ticket.

---

## Stop and contact AJ

Stop and message AJ on Discord if:

- The transfer fails with both methods
- The customer can't sign in to their Apple ID or Google account
- Two-step sign-in codes won't move and the customer may get locked out
- The old phone has no passcode the customer remembers

Include both models and what you tried. No customer details in Discord.

---

## Findings record

```
DS-004 Findings
Old phone model:
New phone model:
Move type:                     iPhone>iPhone / Android>iPhone / Android>Android
Method used:
Transfer finished:             Yes / No
WhatsApp moved:                Yes / No / Not used
Code apps working:             Yes / No / Not used
Phone service working:         Yes / No
Customer checked and approved: Yes / No
Old phone erased:              Yes (signed out first) / No, customer kept it as is
Technician / Date:
```

Tag the ticket `DS-MIGRATION`.

## Revision history

| Version | Date | Change | By |
|---|---|---|---|
| 0.1 | 2026-11-24 | First draft | AJ |
