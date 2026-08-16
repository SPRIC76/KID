# Download & install

KIT is one program: **[`KIT.exe`](https://github.com/SPRIC76/KIT/releases/latest)**. The installer and package managers only place that file.

Both launches live on the same page — open **[latest release](https://github.com/SPRIC76/KIT/releases/latest)** and pick either:

| Launch | File | |
|---|---|---|
| **Installer** | [`KIT-Setup.exe`](https://github.com/SPRIC76/KIT/releases/latest) | Start menu, repair, uninstall |
| **Portable** | [`KIT.exe`](https://github.com/SPRIC76/KIT/releases/latest) | No install — run from any folder |

Matching digests sit beside the binaries on that page.

---

## Installer (recommended)

1. Download [`KIT-Setup.exe`](https://github.com/SPRIC76/KIT/releases/latest)  
2. Run it, then open **KIT** from the Start menu  

| Need | Action |
|---|---|
| Repair | Run Setup again |
| Upgrade | Tray **Check for updates…**, or a newer Setup |
| Uninstall | **Settings → Apps → KIT** |

Installs under your user profile — no administrator required for ordinary use.

---

## Portable

Download [`KIT.exe`](https://github.com/SPRIC76/KIT/releases/latest) and run it from any folder you like. No Start-menu entry unless you add one. Delete the file to remove it. Preferences live quietly in your user app data — not beside the portable.

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

Until then, use [`KIT-Setup.exe`](https://github.com/SPRIC76/KIT/releases/latest) or [`KIT.exe`](https://github.com/SPRIC76/KIT/releases/latest) from the [latest release](https://github.com/SPRIC76/KIT/releases/latest).

---

## Verify

```bat
certutil -hashfile KIT-Setup.exe SHA256
certutil -hashfile KIT.exe SHA256
```

Compare to the `.sha256` files on the [latest release](https://github.com/SPRIC76/KIT/releases/latest). Trust notes: [TRUST.md](../TRUST.md).

---

## If Windows blocks KIT

Unsigned builds can be refused by **Smart App Control** or Application Control — a publisher-trust policy, not a bad download.

1. Confirm the digest from the [official release](https://github.com/SPRIC76/KIT/releases/latest)  
2. Review **Windows Security → App & browser control → Smart App Control**  
3. Prefer a signed release when that lands; avoid casually disabling core protections  

Details and alternatives live with the project maintainer’s notes in the private source tree when you are developing from Python.
