# Rollback considerations

Rollback is not always “put the slider back”. Sometimes it is **stop the bleeding**, then **clean up**, then **admit which data you lost**.

## What you can roll back quickly

- **Intune assignments**: unassign apps or policies from pilot groups — fast if you scoped pilots honestly.
- **Update rings**: pause feature/quality updates if the platform supports pausing in your configuration.
- **Conditional Access dependencies**: if compliance drives access, have a break-glass admin path documented (not in this repo — your org should already have one).

## What is slow and messy

- **OS builds already deployed** with a bad ESP profile — you might be reimaging, not “reverting”.
- **Win32 installs half-applied** — detection + remediation loops; sometimes uninstall is fiction and reimage is truth.
- **Identity join state changes** — unwinding Entra join decisions is not a tidy “undo”.

## SCCM-side rollback

If SCCM still owns workloads, you may re-enable old deployments — but verify:

- clients are still healthy,
- content is still on DPs,
- boundaries still match reality after office moves nobody documented.

## Data and audit trail

Rollback decisions should be logged: who approved, what broke, what was scoped. Future you will not remember why Friday happened.

## Communication

If you roll back, tell helpdesk with **symptoms**, not console jargon. “If login hangs at ‘Setting up device’ for more than X minutes, capture correlation id and call…” beats “ESP failed”.

## The honest bit

Some rollbacks are partial: you keep Intune for compliance but move apps back temporarily. That is fine if documented — the failure mode to avoid is **silent dual authority** with nobody owning outcomes.
