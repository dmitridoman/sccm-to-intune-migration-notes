# Common gotchas

Blunt list. If anything here annoys you, good — it means you have met reality before.

## Double policy, double lies

Two management systems can report “success” for different reasons. You see compliant in one console and broken UX on the desk. The fix is not “another baseline” — it is **one owner** and a conflict audit.

## Collections that lied

SCCM collections based on stale inventory will absolutely migrate the wrong devices first. Clean inventory before you trust pilot metrics.

## App installs that only work “after lunch”

Translation: after a reboot, after a second logon, after SCCM cached something, after a GPO refreshed. Intune will not tolerate that vagueness — tighten prerequisites or accept churn.

## Detection rules that check the wrong file version

Teams love checking `C:\Program Files\App\app.exe` version `1.2.3` when the vendor moved to a different path in patch `1.2.3a`. Detection fails, Intune retries, helpdesk hears “looping install”.

## Hybrid join confusion

Users cannot tell you if a device is hybrid join or Entra join — they will say “domain joined” for everything. If your support scripts assume the wrong state, you will burn hours.

## Wi-Fi and OOBE

Autopilot + Intune Wi-Fi profiles are fine until they are not. Have a USB ethernet dongle in the pilot bag. Yes, still, in $CURRENT_YEAR.

## Certificate/PKI apps

Anything that chains trust to on-prem PKI will haunt cloud-first join until you redesign trust. Migration projects pretend this is a footnote; it is often the main plot.

## Reporting gaps during transition

For a while, neither SCCM nor Intune reports answer the old question exactly. Leadership will ask for a number you no longer produce the same way. Prepare a one-page “metric translation” or suffer endless meetings.

## “We will fix culture later”

If helpdesk still defaults to local admin fixes, your modern baseline will be bypassed by “helpful” field tech habits. Process and tooling go together.

## Exam season amnesia

The worst time to roll change is exactly when someone schedules it anyway. Put academic / finance freeze windows in the plan document, not just in someone’s head.

## Co-management left on forever

If you never retire SCCM roles, you pay twice and troubleshoot twice. Co-management should have an exit date, even if it slips.
