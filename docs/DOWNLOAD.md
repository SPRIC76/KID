# Download & install

KIT is one program: **`KIT.exe`**. The installer and package managers only place that file.

Prefer the official [releases](https://github.com/SPRIC76/KIT/releases/latest) page. Each release includes matching digests beside the binaries.

---

## Installer (recommended)

1. Open the [latest release](https://github.com/SPRIC76/KIT/releases/latest)  
2. Download **KIT-Setup.exe**  
3. Run it, then open **KIT** from the Start menu  

| Need | Action |
|---|---|
| Repair | Run Setup again |
| Upgrade | Tray **Check for updates…**, or a newer Setup |
| Uninstall | **Settings → Apps → KIT** |

Installs under your user profile — no administrator required for ordinary use.

---

## Portable

Download **KIT.exe** from the same release and run it from any folder you like. No Start-menu entry unless you add one. Delete the file to remove it. Preferences live quietly in your user app data — not beside the portable.

---

## Updates

Tray **Check for updates…** refreshes the copy you are already running, updates your Desktop shortcut when needed, and relaunches. Setup remains the path for first install, repair, and uninstall.

---

## Silent Setup

```bat
KIT-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

With a Desktop shortcut:

```bat
KIT-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES /TASKS="desktopicon"
```

Quiet uninstall:

```bat
"%LOCALAPPDATA%\Programs\KIT\unins000.exe" /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

---

## Scoop

```bat
scoop bucket add kid https://github.com/SPRIC76/KIT
scoop install kid
scoop update kid
```

---

## Winget

When listed in the community source:

```bat
winget install --id SPRIC76.KIT -e
```

Until then, use Setup or portable from the release page.

---

## Verify

```bat
certutil -hashfile KIT-Setup.exe SHA256
certutil -hashfile KIT.exe SHA256
```

Compare to the `.sha256` files on the release. Trust notes: [TRUST.md](../TRUST.md).

---

## If Windows blocks KIT

Unsigned builds can be refused by **Smart App Control** or Application Control — a publisher-trust policy, not a bad download.

1. Confirm the digest from the official release  
2. Review **Windows Security → App & browser control → Smart App Control**  
3. Prefer a signed release when that lands; avoid casually disabling core protections  

Details and alternatives live with the project maintainer’s notes in the private source tree when you are developing from Python.
