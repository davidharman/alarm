# alarm

macOS zsh script that wraps [`termdown`](https://github.com/trehn/termdown) to count down to a time, announce it with `say`, and offer a snooze dialog.

## Usage

```
./alarm [TIME] [TEXT] [FONT]
./alarm 10 "Tea" starwars
./alarm -h
```

Requires `termdown`, and the macOS tools `say`, `osascript` and BSD `date`.

## Changelog

### 2026-11-11 - v0.4
- **What changed:** The alarm text is now passed to `osascript` as an argument instead of being pasted into the AppleScript source. The snooze minutes are validated (whole number >= 1, otherwise 2 is used). Cancelling the dialog (Esc) now stops the alarm.
- **Why:** A `"` in TEXT broke the dialog. Blank or non-numeric snooze input, or a cancelled dialog, left `termdown` with no target, so it counted up forever.
- **How to use:** Nothing changes for the user. TEXT can now contain quotes, and a bad snooze value prints `Invalid snooze '...'` and snoozes for 2 minutes.

### 2026-11-11 - v0.3
- **What changed:** Snoozing now counts down only the snooze time. The countdown target is held in a `target` variable and the loop has a single `termdown` call.
- **Why:** In v0.2 the snooze ran its own `termdown`, then the loop restarted and ran the original TIME again before showing the dialog, so a 2 minute snooze took much longer.
- **How to use:** Nothing changes for the user. Enter the snooze minutes in the dialog and press Snooze. The alarm sounds and the dialog reappears after those minutes.
