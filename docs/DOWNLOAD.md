# Download & install

KIT is one program: **`KIT.exe`**. The installer and package managers only place that file. They are not separate apps. (Earlier builds were named KID; Setup uses the same AppId and upgrades in place.)

Prefer downloads from the official [releases](https://github.com/SPRIC76/KIT/releases/latest) page. Each release ships matching **SHA-256** digests beside the binaries.

---

## Installer (recommended)

1. Open the [latest release](https://github.com/SPRIC76/KIT/releases/latest).  
2. Download **KIT-Setup.exe**.  
3. Run it, then launch **KIT** from the Start menu.

| Need | Action |
|---|---|
| Repair / reinstall | Run **KIT-Setup.exe** again |
| Upgrade | Tray **Check for updates…** (replaces the running `KIT.exe` in place, Desktop shortcut, relaunch), or run a newer **KIT-Setup.exe** (closes KIT, replaces files, relaunches) |
| Uninstall | **Settings → Apps → KIT → Uninstall**, or the uninstaller under the install folder |
| Default location | `%LOCALAPPDATA%\Programs\KIT\` (no Admin; prior KiD installs may remain under `Programs\KID`) |

**Note:** Install *folder* does not defeat Smart App Control. Unsigned `KIT.exe` can be blocked in any path. On a blocked PC with Python, use the repo’s `install_local.ps1` / `run_kid.cmd` (runs under signed `pythonw`). On PCs where an older KID.exe already runs, keep using Setup / Start Menu as usual.

---

## Portable

1. Download **KIT.exe** from the same release.  
2. Run it from any folder you choose.

No installer, no automatic Start-menu entry, no uninstaller — delete the file to remove it. Settings and other generated files live in `%LOCALAPPDATA%\KiT\` (legacy `%LOCALAPPDATA%\KiD\`), not beside the portable.

---

## Tray update (after first install)

Tray **Check for updates…** downloads **`KIT.exe`** (+ SHA-256; falls back to `KID.exe` on older releases), **replaces the copy you are running** (a Desktop portable stays there; a Setup install stays under Programs), refreshes Desktop **KIT.lnk** to that same file, rewrites **Run at Windows sign-in** to that file when it is on, and relaunches. Staging files go in `%LOCALAPPDATA%\KiT\update\`. It does **not** run Setup. Use Setup / package managers for first install, repair, and uninstall. Setup itself closes a running KIT, replaces files, heals the Run key if autostart is on, and relaunches the new version.

---

## Silent / scripted Setup

Quiet install:

```bat
KIT-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

Quiet install with desktop shortcut:

```bat
KIT-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES /TASKS="desktopicon"
```

Progress UI, still unattended:

```bat
KIT-Setup.exe /SILENT /NORESTART /SUPPRESSMSGBOXES
```

Quiet uninstall:

```bat
"%LOCALAPPDATA%\Programs\KIT\unins000.exe" /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

---

## Scoop

This repository is the Scoop bucket (`bucket/kid.json`). It installs from the GitHub release assets.

```bat
scoop bucket add kid https://github.com/SPRIC76/KIT
scoop install kid
scoop update kid
scoop uninstall kid
```

---

## Windows Package Manager (winget)

Once accepted into the [winget community repository](https://github.com/microsoft/winget-pkgs):

```bat
winget install --id SPRIC76.KID -e
winget upgrade SPRIC76.KID
winget uninstall SPRIC76.KID
```

Until that listing is live, install with **KIT-Setup.exe** (interactive or silent flags above).

---

## Verify

1. Download the `.sha256` file next to the asset you chose.  
2. Compare with a local hash, for example:

```bat
certutil -hashfile KIT-Setup.exe SHA256
certutil -hashfile KIT.exe SHA256
```

Trust and behavior notes: [TRUST.md](../TRUST.md).

---

## Windows blocks KIT.exe (Smart App Control / error 4551)

Unsigned builds can be blocked with:

> Unable to execute file … CreateProcess failed; code 4551.  
> An Application Control policy has blocked this file.

Or: “Part of this app has been blocked … we can't confirm who published **KIT.exe**.”

**This is Windows Application Control / Smart App Control**, not a bad install.

| Path | What to do |
|---|---|
| Check the policy | **Windows Security → App & browser control → Smart App Control** |
| Evaluation vs On | Evaluation warns; **On** hard-blocks unsigned apps. Turning **On** off may require resetting the feature (Microsoft’s rules). |
| Develop / use now | From the project folder: `python -m kid` (runs under your signed Python) |
| Verify the file | Compare SHA-256 to the [release](https://github.com/SPRIC76/KIT/releases/latest) digests before trusting any unblock |
| Lasting product fix | Authenticode **code signing** so Smart App Control can verify the publisher |

Do not disable core Windows security casually. Prefer signing when you want Setup/Start Menu launches to just work on locked-down PCs.
