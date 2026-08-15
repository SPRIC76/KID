# Download

KID is a single program: **`KID.exe`**. The installer and package managers only place that file.

## Recommended

1. Open the [latest release](https://github.com/SPRIC76/KID/releases/latest).  
2. Download **KID-Setup.exe**.  
3. Run it, then launch **KID** from the Start menu.

Repair: run Setup again.  
Remove: **Settings → Apps → KID → Uninstall**.

## Portable

Download **KID.exe** from the same release. Run it directly — no install required.

## Silent install

```bat
KID-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

With desktop shortcut:

```bat
KID-Setup.exe /VERYSILENT /NORESTART /SUPPRESSMSGBOXES /TASKS="desktopicon"
```

Silent uninstall:

```bat
"%LOCALAPPDATA%\Programs\KID\unins000.exe" /VERYSILENT /NORESTART /SUPPRESSMSGBOXES
```

## Package managers

**Winget** (after community acceptance):

```bat
winget install --id SPRIC76.KID -e
```

**Scoop** (this repository is the bucket):

```bat
scoop bucket add kid https://github.com/SPRIC76/KID
scoop install kid
```
