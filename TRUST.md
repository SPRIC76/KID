# Trust

KID stays on your machine. It keeps Windows awake and can darken the display on demand. This page states what the shipped app does — and what it never does — so you can judge it plainly.

## What it asks of Windows

| Capability | Mechanism (summary) |
|---|---|
| Stay awake | Standard execution-state request (same class of API as classic “caffeine” tools) |
| Daylight / Night without lock fog | Temporary power/lock timeout adjustments, restored on Off |
| Hotkeys | Registered chords only — Windows reports that a shortcut fired, not what you typed |
| Night workspace | Minimizes open windows and hides the taskbar; restores both when you leave Night |
| Night darkness | Monitor brightness when available, plus a full-screen black layer |
| Wake from Night | Idle timestamp check only — not key identity or typed content |
| Control bar / screensaver | Bar hides during Night; optional in-app saver runs only during Night |
| Single instance | Named mutex |

## What it never does

- Record or inspect keystrokes or clipboard contents  
- Synthesize mouse or keyboard input  
- Store, transmit, or type credentials  
- Open network connections, phone home, or collect telemetry  
- Require administrator rights for ordinary use  

## How to verify

- Each [release](https://github.com/SPRIC76/KID/releases) publishes `KID.exe`, `KID-Setup.exe`, and matching SHA-256 digests  
- Prefer downloads from that release page only  
- The executable carries ordinary product metadata (name, version, copyright)  

New publishers and unsigned binaries often trigger a one-time reputation scan from antivirus or SmartScreen. That is expected for a fresh release; it is not evidence of malice. Compare hashes from the official release page.

If a vendor flags a release incorrectly, submit their false-positive form with the release asset and hash, and/or check [VirusTotal](https://www.virustotal.com/) against the published digests.
