# Trust

KIT stays on your machine. It keeps Windows awake and can darken the display on demand. This page states what the shipped app does — and what it never does — so you can judge it plainly.

## What it asks of Windows

| Capability | Mechanism (summary) |
|---|---|
| Stay awake | Standard execution-state request (same class of API as classic “caffeine” tools) |
| Daylight / Night without lock fog | Temporary power/lock timeout adjustments, restored on Off |
| Hotkeys | Registered chords only — Windows reports that a shortcut fired, not what you typed. Short tap / 2s hold → Off / triple-flip are timed from those notifications (auto-repeat), never from key content |
| Night workspace | Minimizes open windows and hides the taskbar; restores both when you leave Night |
| Night darkness | Monitor brightness when available, plus a full-screen black layer |
| Wake from Night | Idle timestamp check only — not key identity or typed content (disabled when Hold Night is on). Escape leaves Night via global key presence (`GetAsyncKeyState`) plus Night-surface bind — same class as hotkeys, not a keylogger. Bare Escape is never registered as a system hotkey (that can swallow the key). |
| Hold Night | Optional: leave Night only via hotkeys (incl. Escape); ignores mouse/idle wake and tray/saver mode picks |
| Control bar / screensaver | Bar hides during Night; optional in-app saver runs only during Night |
| Check for updates (tray) | **Only when you choose it** — reads the public GitHub latest release, downloads `KIT.exe` (+ SHA-256 when present; older releases may still ship `KID.exe`), replaces the install under `%LOCALAPPDATA%\Programs\KIT\` (or an existing KiD folder), refreshes Desktop **KIT.lnk**, and relaunches. Tray never runs Setup. |
| Single instance | Named mutex |

## What it never does

- Record or inspect keystrokes or clipboard contents  
- Synthesize mouse or keyboard input  
- Store, transmit, or type credentials  
- Phone home, collect telemetry, or open the network **except** the opt-in tray **Check for updates…** path above  
- Require administrator rights for ordinary use (updates install under your user profile)  

## How to verify

- Each [release](https://github.com/SPRIC76/KIT/releases) publishes `KIT.exe`, `KIT-Setup.exe`, and matching SHA-256 digests  
- Prefer downloads from that release page only  
- The executable carries ordinary product metadata (name, version, copyright)  

New publishers and unsigned binaries often trigger a one-time reputation scan from antivirus or SmartScreen. That is expected for a fresh release; it is not evidence of malice. Compare hashes from the official release page.

**Smart App Control / Application Control (error 4551):** Windows may refuse to launch unsigned `KIT.exe` entirely. That is a publisher-trust policy, not network malware detection. See [docs/DOWNLOAD.md](docs/DOWNLOAD.md) (section on Smart App Control). Interim: run `python -m kid` from the project while developing, or obtain Authenticode signing for release builds.

If a vendor flags a release incorrectly, submit their false-positive form with the release asset and hash, and/or check [VirusTotal](https://www.virustotal.com/) against the published digests.
