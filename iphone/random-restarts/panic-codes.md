# Known Panic Codes (AtoZ Shop Fixes)

Fixes confirmed at our bench. Add a row only after the fix was tested and the restarts stopped.
Use synthetic examples only. Never paste a full real log here.

| Model | Panic string (short) | Likely area | What fixed it | Confirmed |
|---|---|---|---|---|
| | | | | |

## Panic Log References

Use these links to narrow down what to test. Once the bench confirms the repair, add a row to the shop-fix table above.

| What you see | Link | What it helps you check |
|---|---|---|
| `panic-full`, `thermalmonitord`, or `Missing sensor(s)` | [iFixit: iPhone Kernel Panics](https://www.ifixit.com/Wiki/iPhone_Kernel_Panics) | How to read the log and where to start for sensor clues such as PRS0, Mic1, Mic2 and TG0B. |
| `SMC PANIC - ASSERTION FAILED` with a 0x... sensor array | [iFixit: iPhone SMC Panic Assert](https://www.ifixit.com/Wiki/iPhone_SMC_Panic_Assertion_Failed) | Match the sensor value to the exact iPhone model before choosing an assembly or connector to inspect. |
| Unexpected restarts or shutdowns on an iPhone 15 | [Apple: iPhone 15 Repair Manual](https://support.apple.com/en-us/104900) | Apple's troubleshooting flow under "Unexpected freeze, restart, or shutdown issues." |
| You need instructions for a different model or want to run diagnostics | [Apple: Self Service Repair](https://support.apple.com/self-service-repair) · [Apple: Diagnostics mode](https://support.apple.com/en-us/101944) | Find the model-specific repair manual, or check how to enter Diagnostics mode. |
