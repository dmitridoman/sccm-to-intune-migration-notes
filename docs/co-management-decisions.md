# Co-management decisions

## What co-management is good at

- Letting you **move workloads gradually** without ripping SCCM out overnight.
- Giving Intune a foothold while you still rely on OS deployment or legacy packages.
- Buying time while you rebuild app portfolio hygiene that should have happened years ago.

## What co-management is not

- A permanent architecture for organisations that hate making decisions.
- A magic fix for **policy duplication** — you still need ownership.
- A substitute for cleaning up SCCM — garbage collections still burn CPU and confuse audits.

## Workload sliders (the bit people argue about)

Typical split:

- **Compliance policies**: often Intune-first once you trust baselines — but verify overlap with SCCM configuration baselines.
- **Device configuration**: painful if GPO, SCCM baselines, and Intune policies all touch the same registry keys.
- **Apps**: frequently the longest tail — start with low-risk Win32, not the monolith with fifteen dependencies.
- **Windows Update**: pick **one** authority per ring unless you enjoy reboot roulette.

## Client settings and boundaries

Co-management still needs healthy SCCM clients for the workloads you leave there. If your SCCM estate is already flaky, co-management will not stabilise it — it will surface the pain during hybrid enrolment.

## Telemetry and troubleshooting

You will split signals across SCCM logs, Intune diagnostics, and Entra sign-in trails. Decide where tickets get triaged first or teams will bounce issues for days.

## Exit criteria

Write down what “done” means: which SCCM roles can be retired, which DPs go dark, what reporting replaces the old compliance views.

If exit criteria are vague, you will run two systems forever “just in case”.
