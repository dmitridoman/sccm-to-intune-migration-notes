# sccm-to-intune-migration-notes

Markdown notes from the uncomfortable part of IT: moving workloads from **Configuration Manager** toward **Intune** without pretending it is a button-click upgrade.

No code on purpose. This is the sort of thing you keep next to the project plan so you remember what hurt last time.

## Contents

- `docs/migration-overview.md` — scope, discovery, sequencing.
- `docs/co-management-decisions.md` — what co-management is for (and what it is not).
- `docs/workload-move-checklist.md` — blunt checklist for moving workloads.
- `docs/common-gotchas.md` — overlap, drift, reporting holes.
- `docs/rollback-considerations.md` — how to back out without heroics.

## Who this is for

Infrastructure engineers who already know what SCCM and Intune are, and who need **judgement prompts**, not another “digital transformation” slide deck.

## Placeholders

Any names like `contoso.onmicrosoft.com` or `00000000-0000-0000-0000-000000000000` are sanitised examples.

## How to use

Read once before you promise dates. Re-read when someone suggests “just flip the slider” on a workload you have never piloted.
