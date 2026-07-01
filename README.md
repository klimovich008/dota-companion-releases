# Dota Lobby Companion — Releases

Windows app for Dota 2: patches the Minify probe mod, watches your `console.log`, and keeps a local player-notes / match-history dashboard.

## Install

1. Download `DotaCompanion-win-x64.zip` from the [latest release](https://github.com/klimovich008/dota-companion-releases/releases/latest).
2. Unpack anywhere.
3. Run `DotaCompanion.exe`.

A control window opens and lives in the system tray (like Discord):

- **ON/OFF** — start/stop watching the Dota console.log
- **Patch / Remove** — install or remove the Minify mod (pick your dota2-minify folder once)
- **Open Dashboard** — optional browser view with player notes, lobby and match history
- Closing the window hides it to the tray; tray menu → **Exit** stops everything

The app auto-updates from this repo's releases. Your data stays in `app\data` next to the exe and survives updates.

Windows SmartScreen may warn on first run (unsigned exe) — choose "More info" → "Run anyway".
