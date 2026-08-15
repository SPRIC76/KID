# KID

**Keep it Daylight** · *Daylight for dark mode*

A quiet Windows tray utility: keep the machine awake, darken on demand, return to normal when you are done. One program. Local only. No accounts, no telemetry, no fake input.

## Modes

| Mode | What it does |
|---|---|
| **Daylight** | Keeps the PC and display awake. Suppresses lock fog while active. |
| **Night** | Wakeable dark — the screen goes dark, open windows step aside, the machine stays awake. Activity returns you. |
| **Off** | Restores ordinary Windows sleep and lock behavior. |

Three states. One click each. No schedules, no idle games.

## Download

| Installer | Portable |
|---|---|
| [**KID-Setup.exe**](https://github.com/SPRIC76/KID/releases/latest) | [**KID.exe**](https://github.com/SPRIC76/KID/releases/latest) |

Silent install, repair, uninstall, and package-manager notes: [Download](docs/DOWNLOAD.md).

## Use

- Compact control bar and system tray
- Hotkeys (defaults): **Ctrl+Shift+D** Daylight ↔ Off · **Ctrl+Shift+K** Night ↔ Off
- Single instance — a second launch focuses the running copy

Optional settings: `kid.json` beside the executable, or `%LOCALAPPDATA%\KiD\kid.json` ([example](config.example.json)).

## Trust

Runs entirely on your machine. KID does not log keystrokes, spoof mouse or keyboard input, store credentials, or contact the network.

Details and verification: [TRUST.md](TRUST.md).

## Requirements

Windows 10 or 11. The release build needs nothing else installed.

## License

[MIT](LICENSE)
