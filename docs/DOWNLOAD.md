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
| Uninstall | **Settings → Apps → KID → Uninstall**, or the uninstaller under the install folder |
| Default location | `%LOCALAPPDATA%\Programs\KID\` |

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
