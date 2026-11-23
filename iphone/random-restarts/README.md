# iPhone Random Restarts

Use this when an iPhone restarts by itself, boot loops, or restarts every few minutes.

**Rule of thumb:** read the panic log before you replace any part. The log usually points to the area that is failing.

Related pages: [Tools](tools.md) · [Videos](videos.md) · [Known panic codes](panic-codes.md)

---

## Step 1. Intake checks

Ask the customer and write the answers in the repair ticket:

- When did it start? After a drop, water exposure, an iOS update, or a part replacement somewhere else?
- How often does it restart? Every few minutes, a few times a day, only when charging?
- Does it restart only when using the camera, Face ID, or when the phone gets warm?
- Has the battery or screen been replaced before?

Check the phone:

- Visible damage: bent frame, swollen battery (screen lifting), cracked back glass.
- Liquid indicators if accessible.

> Do not ask for the passcode. The customer unlocks the phone themselves for the log steps.

## Step 2. Basic software checks

1. Check the iOS version in **Settings > General > About**. Note it in the ticket.
2. Check **Settings > Battery > Battery Health** (on newer iOS: Battery Health & Charging). Note the percentage and any service message.
3. If the phone stays on long enough, ask the customer if they're OK with an iOS update before you go further.

## Step 3. Pull the panic log

1. With the phone unlocked by the customer, go to **Settings > Privacy & Security > Analytics & Improvements > Analytics Data**.
2. Look for files starting with `panic-full`. The newest one matters most.
3. If there are no panic-full files, the restarts may be software related. Skip to Step 6.
4. Use the approved extractor on the store computer to pull the log. See [tools.md](tools.md).

## Step 4. Review the log

1. Open the log in the approved analyzer. See [tools.md](tools.md).
2. Find the **panic string** near the top. It often names a missing sensor or a timeout.
3. Look it up in [panic-codes.md](panic-codes.md). If it's not there, check [videos.md](videos.md) and the outside resources in [tools.md](tools.md).
4. Write the panic string and the likely cause in the repair ticket.

> Treat the analyzer result as a strong clue, not a final answer. Confirm with the test in Step 5.

## Step 5. Isolate the part

1. Test with a known-good part when possible (battery or charge port flex are the most common).
2. If the restarts stop with the test part, replace the part and run the phone for at least 30 minutes, including a charge cycle.
3. If restarts continue with the known-good part, put the original part back and move to Step 6.

## Step 6. Software restore

1. Make sure the customer has a backup or agrees to data loss in writing on the ticket.
2. Update or restore iOS using the store computer.
3. If the phone still restarts after a clean restore, it's likely a board-level issue. Go to Step 7.

## Step 7. Escalation

Escalate when:

- The panic log points to the board (CPU, NAND, or a power issue on the logic board).
- Known-good part tests and a restore did not fix it.
- There are signs of liquid damage on the board.

**How to escalate:** escalate to the lead tech, or message the owner on Discord with the device model, panic string and steps already tried. Do not share customer details in Discord.

## Step 8. Close out

- Write the panic string, the fix, and the parts used in the ticket.
- If this was a new panic string, send it in team chat so it can be added to [panic-codes.md](panic-codes.md).
- Delete any log files from the store computer.
