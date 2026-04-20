# Migration overview

## What “migration” actually means here

You are not “replacing SCCM” in a weekend. You are **re-homing** client management primitives (apps, updates, baselines, OS deployment habits) onto a cloud control plane that thinks in identities, MDM channels, and different reporting.

If you start without inventory, you will discover the embarrassing stuff in production: that one package that only works when a legacy GPO whispers to it, the collection that secretly included servers, the task sequence nobody owns.

## Discovery (boring, non-negotiable)

- **Clients**: versions, join state (workgroup, domain, hybrid, Entra join), branch office distribution reality.
- **Deployments**: what is required vs available, maintenance windows, nested dependencies.
- **Boundaries and DP layout**: informs whether you are kidding yourself about bandwidth during Intune content pulls.
- **Custom inventory**: if your compliance team lives off SCCM reports, map each one to an Intune / Graph / Log Analytics story early — or prepare for awkward silence in audits.

## Pilot rings

You want **representative misery**: teaching labs, finance laptops, exec assistants, VPN-heavy remote users, and at least one site with bad connectivity.

Pilot is where you learn:

- Win32 app behaviour under real user context.
- ESP timeouts and Autopilot profile mistakes.
- Policy overlap that did not show up in the lab.

## Application packaging concerns

SCCM packages often assume:

- interactive admin,
- long-running installs during maintenance windows,
- random prerequisites silently pre-installed by older GPO.

Intune Win32 is stricter about detection rules, exit codes, and context. “It worked in SCCM” is not a detection method.

## Policy overlap risks

Co-management can mean **double intent**: two engines trying to enforce “similar enough” settings. Sometimes they fight, sometimes you get false confidence because one side is not actually applying what you think.

Write down **one owner per control area** for the migration window. Temporary duplication should be deliberate, not accidental.

## Identity and join state

Modern management wants a clear story: **who owns credentials**, **how devices join**, **how admin elevation works**. Hybrid join vs Entra join changes how you think about PKI, Wi-Fi profiles, and resource access.

If you skip this, you will fix it later under pressure.

## Compliance and reporting gaps

SCCM reporting is not pretty, but it is familiar. Intune compliance is real, yet dashboards answer different questions. Expect a period where leadership asks for the old report and you hand them something that is *better in theory* and *worse for their spreadsheet habits*.

Plan the translation, not just the migration.

## Rollback thinking

See `rollback-considerations.md`. If you cannot answer “what do we do Friday if Intune app installs brick exams”, you are not ready.
