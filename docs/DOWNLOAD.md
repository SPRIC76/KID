# Download & install

KID is one program: **`KID.exe`**. The installer and package managers only place that file. They are not separate apps.

Prefer downloads from the official [releases](https://github.com/SPRIC76/KID/releases/latest) page. Each release ships matching **SHA-256** digests beside the binaries.

---

## Installer (recommended)

1. Open the [latest release](https://github.com/SPRIC76/KID/releases/latest).  
2. Download **KID-Setup.exe**.  
3. Run it, then launch **KID** from the Start menu.

| Need | Action |
|---|---|
| Repair / reinstall | Run **KID-Setup.exe** again |
| Upgrade | Run a newer **KID-Setup.exe** — same install replaces files in place (no uninstall) |
| Uninstall | **Settings → Apps → KID → Uninstall**, or the uninstaller under the install folder |
| Default location | `%LOCALAPPDATA%\Programs\KID\` (no Admin; correct for Setup) |

**Note:** Install *folder* does not defeat Smart App Control. Unsigned `KID.exe` can be blocked in any path. On a blocked PC with Python, use the repo’s `install_local.ps1` / `run_kid.cmd` (runs under signed `pythonw`). On PCs where 1.0.17 already runs, keep using Setup / Start Menu as usual.

---

## Portable

1. Download **KID.exe** from the same release.  
2. Run it from any folder you choose.

No installer, no automatic Start-menu entry, no uninstaller — delete the file to remove it. Settings, if any, still use `kid.json` beside the exe or under `%LOCALAPPDATA%\KiD\`.

---

## Silent / scripted Setup

Quiet install:

```bat
KID-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

Quiet install with desktop shortcut:

```bat
KID-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES /TASKS="desktopicon"
```

Progress UI, still unattended:

```bat
KID-Setup.exe /SILENT /NORESTART /SUPPRESSMSGBOXES
```

Quiet uninstall:

```bat
"%LOCALAPPDATA%\Programs\KID\unins000.exe" /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

---

## Scoop

This repository is the Scoop bucket (`bucket/kid.json`). It installs from the GitHub release assets.

```bat
scoop bucket add kid https://github.com/SPRIC76/KID
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

Until that listing is live, install with **KID-Setup.exe** (interactive or silent flags above).

---

## Verify

1. Download the `.sha256` file next to the asset you chose.  
2. Compare with a local hash, for example:

```bat
certutil -hashfile KID-Setup.exe SHA256
certutil -hashfile KID.exe SHA256
```

Trust and behavior notes: [TRUST.md](../TRUST.md).

---

## Windows blocks KID.exe (Smart App Control / error 4551)

Unsigned builds can be blocked with:

> Unable to execute file … CreateProcess failed; code 4551.  
> An Application Control policy has blocked this file.

Or: “Part of this app has been blocked … we can't confirm who published **KID.exe**.”

**This is Windows Application Control / Smart App Control**, not a bad install.

| Path | What to do |
|---|---|
| Check the policy | **Windows Security → App & browser control → Smart App Control** |
| Evaluation vs On | Evaluation warns; **On** hard-blocks unsigned apps. Turning **On** off may require resetting the feature (Microsoft’s rules). |
| Develop / use now | From the KiD project folder: `python -m kid` (runs under your signed Python) |
| Verify the file | Compare SHA-256 to the [release](https://github.com/SPRIC76/KID/releases/latest) digests before trusting any unblock |
| Lasting product fix | Authenticode **code signing** so Smart App Control can verify the publisher |

Do not disable core Windows security casually. Prefer signing when you want Setup/Start Menu launches to just work on locked-down PCs.
