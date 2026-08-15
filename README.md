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

## Install

Everything below places the same program: **`KID.exe`**.

| Path | Best for | Get it |
|---|---|---|
| **Installer** | Most people — Start menu, repair, uninstall | [KID-Setup.exe](https://github.com/SPRIC76/KID/releases/latest) |
| **Portable** | No install — run the file | [KID.exe](https://github.com/SPRIC76/KID/releases/latest) |
| **Silent Setup** | Scripts and fleets | Flags below |
| **Scoop** | Scoop users | Commands below |
| **Winget** | After community acceptance | `winget install --id SPRIC76.KID -e` |

### Installer

1. Download **KID-Setup.exe** from the [latest release](https://github.com/SPRIC76/KID/releases/latest).  
2. Run it → Next → Finish.  
3. Open **KID** from the Start menu.

Repair: run Setup again (same install folder).  
Remove: **Settings → Apps → KID → Uninstall**.

### Portable

Download **KID.exe** from the same release. Double-click. No Setup, no Start-menu entry unless you add one.

### Silent install

```bat
KID-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

Desktop shortcut as well:

```bat
KID-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES /TASKS="desktopicon"
```

Silent uninstall:

```bat
"%LOCALAPPDATA%\Programs\KID\unins000.exe" /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

### Scoop

```bat
scoop bucket add kid https://github.com/SPRIC76/KID
scoop install kid
```

### Winget

When the package is listed in the community source:

```bat
winget install --id SPRIC76.KID -e
winget upgrade SPRIC76.KID
winget uninstall SPRIC76.KID
```

Until then, use the installer or portable build from the release page.

Full install reference: [docs/DOWNLOAD.md](docs/DOWNLOAD.md).

## Use

- Compact control bar and system tray  
- Hotkeys (defaults): **Ctrl+Shift+D** Daylight ↔ Off · **Ctrl+Shift+K** Night ↔ Off  
- Single instance — a second launch focuses the running copy  
- Tray option **Ghost bar** — 59% transparent, click-through (hotkeys / tray only)  

Optional settings: `kid.json` beside the executable, or `%LOCALAPPDATA%\KiD\kid.json` ([example](config.example.json)).

## Trust

Runs entirely on your machine. KID does not log keystrokes, spoof mouse or keyboard input, store credentials, or contact the network.

Release assets include SHA-256 digests. Details: [TRUST.md](TRUST.md).

## Requirements

Windows 10 or 11. The release build needs nothing else installed.

## License

[MIT](LICENSE)
