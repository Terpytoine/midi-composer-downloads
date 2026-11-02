# Download and install the VST3

Download **MIDIComposer-VST3-Setup-0.1.0-dev-Windows.exe** from the official GitHub release, then run it. This EXE is an installer for the VST3 instrument; it is not a standalone music application.

1. Close FL Studio before installing or updating the plugin.
2. Open the installer and approve the normal Windows administrator prompt. It writes the full plugin bundle into `C:\Program Files\Common Files\VST3\MIDI Composer Dev.vst3`.
3. Follow the short setup wizard. Open FL Studio, choose **Options → Manage plugins**, and use **Find installed plugins**.
4. Load **MIDI Composer Dev** as an instrument. Its preview audio uses FL Studio's audio device; Host sync follows the project tempo and transport.

The installer does not change FL Studio's saved search paths or other settings, start FL Studio, create a standalone music app, download code, or contact a server. The common VST3 folder is a conventional plugin location; actual scanning/loading in this copy of FL Studio remains untested. If that folder is absent from the host's search list, add it yourself or use the manual ZIP instructions.

At 180 BPM, **½×** gives a 90 BPM musical feel while the MIDI still spans eight host bars / 32 beats / approximately 10.67 seconds. **1×** gives the faster phrasing at the same loop length. Auto suggests a rate from the current tempo, and you can override it. The separate Grid control defaults to **½ beat**.

The installed documentation and uninstaller live in `C:\Program Files\MIDI Composer Dev`. To remove the plugin, close FL Studio and use Windows **Settings → Apps → Installed apps → MIDI Composer Dev VST3 → Uninstall**. The uninstaller removes only this product's manifest-listed files and empty product folders. Your FL Studio projects, custom MIDI files and other plugins are outside its deletion list.

This development installer and plugin are **unsigned**. No code-signing certificate was available. Verify the final release's SHA-256 against its published checksum. An unsigned build can trigger a Windows reputation prompt; signing and reputation are separate from the functional checks reported in the release.

The source remains private. Public release assets should contain the installer, checksum, user documentation and relevant notices, not source/build tools or credentials.
