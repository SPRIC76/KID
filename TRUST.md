# Trust

KIT is a local Windows utility. It keeps the machine awake when you ask, can darken the room without putting the PC to sleep, and otherwise stays out of the way. This page is the honest account of what it does — and what it refuses to do.

## Design posture

Quiet. Efficient. Under your control. No account. No dashboard in the cloud. No “engagement.” The product earns trust by staying small and saying no to the usual surveillance habits of desktop tools.

## What it does

- Holds the session awake in **Light** and **Night**  
- Softens lock interruptions while those modes are active  
- Offers global hotkeys for Light, Night, Off, and flip — chords only, never a record of what you type  
- In **Night**, clears the desk and darkens the display; activity (or Escape) can return you — unless you choose **Hold Night**  
- Draws its own Night faces and control bar locally  
- Checks for updates **only** when you choose tray **Check for updates…**  
- Runs as a single instance  

## What it never does

- Record keystrokes or clipboard  
- Fake mouse or keyboard input  
- Store, send, or type credentials  
- Call home, collect telemetry, or open the network except that opt-in update path  
- Demand administrator rights for ordinary use  

## How to verify

- Prefer downloads from the official [releases](https://github.com/SPRIC76/KIT/releases) page  
- Each release includes matching digests beside the binaries  
- The executable carries ordinary product identity (name, version, publisher)  

New publishers and unsigned builds often get a one-time reputation look from Windows or antivirus. That is normal for a fresh release — not proof of malice. Compare hashes from the release page before you decide.

On locked-down PCs, **Smart App Control** may refuse unsigned apps outright. That is publisher policy, not a corrupt file. See [Download & install](docs/DOWNLOAD.md). Signing is the lasting product answer when it becomes practical.

If a vendor flags a release incorrectly, use their false-positive path with the official asset and digest, or check [VirusTotal](https://www.virustotal.com/) against the published hashes.
