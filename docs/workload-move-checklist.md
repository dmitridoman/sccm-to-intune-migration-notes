# Workload move checklist

Use as a literal tick list. If you cannot tick an item honestly, you are not ready to move that workload.

## Before you touch sliders

- [ ] Inventory of devices in scope (counts, join types, ownership).
- [ ] Pilot cohort nominated with rollback contacts.
- [ ] Helpdesk briefed on new failure modes (ESP, app timeouts, sync delays).
- [ ] Known high-risk apps flagged (CAD, lab, legacy auth, USB dongle nightmares).

## Apps (Win32 / LOB / Microsoft Store)

- [ ] Install context decided (system vs user) with detection rules that match reality.
- [ ] Dependencies ordered and tested on a slow link.
- [ ] Uninstall path known (or explicitly “reimage-only” documented).
- [ ] Content sources sized — Intune CDN assumptions validated for your sites.

## Updates

- [ ] Single authority chosen per ring (SCCM vs Intune).
- [ ] Deadlines aligned with business hours / exam periods / trading windows.
- [ ] Rollback plan for a bad update (pause rings, WSUS fallback if still in play).

## Configuration / baselines

- [ ] Overlap analysis done against GPO + SCCM baselines + Intune profiles.
- [ ] Conflicts resolved with one named owner per setting area.
- [ ] BitLocker / encryption posture checked against helpdesk recovery practice.

## Compliance

- [ ] Compliance policy matches what you can remediate.
- [ ] Non-compliance actions tested (conditional access impact, helpdesk load).
- [ ] Reporting consumers identified — old SCCM report mapped to new output.

## Identity

- [ ] Join path documented per device type.
- [ ] Admin elevation story documented (LAPS, cloud roles, break-glass).
- [ ] VPN / Wi-Fi profiles validated under new join state if applicable.

## Decommission planning

- [ ] SCCM roles retired in an order that does not orphan clients.
- [ ] DP content lifecycle handled (do not leave big empty shares “for now”).
- [ ] Final compliance evidence captured for audits that ask awkward questions.
