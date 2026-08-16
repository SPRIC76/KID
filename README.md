# KID

**Keep it Daylight** · *Daylight for dark mode*

A quiet Windows tray utility: keep the machine awake, darken on demand, return to normal when you are done. One program. Local only. No accounts, no telemetry, no fake input.

## Modes

| Mode | What it does |
|---|---|
| **Light** | Keeps the PC and display awake. Suppresses lock fog while active. (Default on first run.) |
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

- Low-profile control bar pinned just above the taskbar (equal pad to the taskbar edge)  
- Hotkeys (defaults): **Ctrl+Shift+D** Light · **Ctrl+Shift+K** Night (Night again or **Esc** → Light)  
  - Hold either chord **2 seconds** → Off  
  - Triple-tap either chord → flip Light ↔ Night  
- Last mode and settings restore on startup (`remember_last`, default on)  
- Tray menu shows **KiD v… · GitHub** (opens the public repo)  
- Single instance — a second launch focuses the running copy  
- Tray option **Ghost bar** — 63% transparent, click-through (hotkeys / tray only)  
- Tray **Hold Night** — mouse/idle/saver motion do not wake; leave Night only with hotkeys (**Ctrl+Shift+K** / **D** / **Esc**)  
- Tray **Run at Windows sign-in** — optional autostart (HKCU Run)  
- Tray **Screensaver (Night)** — Off / Random / DVD / Snake / Globules / Orbit; runs only in Night (default Globules)  
  - Globules: seed → roster → gravity well · unique letter colors · Light/Night larges fuse into suns/moons · center black hole absorbs (accretion jets) · single-letter pop only · ricochet sparks · burn-safe animated vortex · hard small/medium caps (no frozen merge orphans)  
- Tray **Check for updates…** — confirms, downloads Setup to Downloads, verifies SHA-256, silent install with interactive fallback if Windows blocks it  

Optional settings: `kid.json` beside the executable, or `%LOCALAPPDATA%\KiD\kid.json` ([example](config.example.json)).

## Trust

Runs on your machine. No keystroke logging, no input spoofing, no credentials. **No network** unless you use tray **Check for updates…** (GitHub Releases only).

Release assets include SHA-256 digests. Details: [TRUST.md](TRUST.md).

## Requirements

Windows 10 or 11. The release build needs nothing else installed.

## License

[MIT](LICENSE)
