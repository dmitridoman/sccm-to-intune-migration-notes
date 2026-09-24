# sccm-to-intune-migration-notes

Markdown notes from the uncomfortable part of IT: moving workloads from **Configuration Manager** toward **Intune** without pretending it is a button-click upgrade.

**Status:** reference notes, no code.
**Runs on:** nothing: Markdown only.
**Used by:** infrastructure engineers planning a Configuration Manager to Intune move.

No code on purpose. This is the sort of thing you keep next to the project plan so you remember what hurt last time.

## Contents

- `docs/migration-overview.md`: scope, discovery, sequencing.
- `docs/co-management-decisions.md`: what co-management is for (and what it is not).
- `docs/workload-move-checklist.md`: blunt checklist for moving workloads.
- `docs/common-gotchas.md`: overlap, drift, reporting holes.
- `docs/rollback-considerations.md`: how to back out without heroics.

## Who this is for

Infrastructure engineers who already know what SCCM and Intune are, and who need **judgement prompts**, not another “digital transformation” slide deck.

## Illustrative org naming

Examples use **Harven Group**: `harven.co.uk`, `harvengroup.onmicrosoft.com`, tenant ID `a1b2c3d4-e5f6-7890-abcd-ef1234567890`. Treat as fiction for the portfolio unless that is genuinely your tenant.

## How to use

Read once before you promise dates. Re-read when someone suggests “just flip the slider” on a workload you have never piloted.
