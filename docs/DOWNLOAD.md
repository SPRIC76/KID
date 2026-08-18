# Download

Both launches live on the [latest release](https://github.com/SPRIC76/KIT/releases/latest). One program. Pick the path that fits.

| | | |
|---|---|---|
| **Installer** | Start menu, repair, uninstall | [`KIT-Setup.exe`](https://github.com/SPRIC76/KIT/releases/latest) |
| **Portable** | No install — run from any folder | [`KIT.exe`](https://github.com/SPRIC76/KIT/releases/latest) |

**Installer:** download [`KIT-Setup.exe`](https://github.com/SPRIC76/KIT/releases/latest), run it, open **KIT** from Start. Run Setup again to repair. Remove it from **Settings → Apps**. No administrator required for ordinary use.

**Portable:** download [`KIT.exe`](https://github.com/SPRIC76/KIT/releases/latest) and run it from any folder you like. Delete the file to remove it. Preferences live quietly with your other app data — not beside the portable.

**Updates:** tray **Check for updates…** refreshes the copy you are already running. Setup remains the path for first install, repair, and uninstall.

## Scoop

```bat
scoop bucket add kid https://github.com/SPRIC76/KIT
scoop install kid
scoop update kid
```

## Winget

```bat
winget install --id SPRIC76.KIT -e
```

Or take either launch from the [latest release](https://github.com/SPRIC76/KIT/releases/latest). Digests (SHA-256) sit beside the files.

How it earns trust: [Trust](../TRUST.md).
