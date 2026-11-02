# VST3 installer validation

Validation performed for the requested Windows VST3-only installer on 1 November 2026. The EXE installs the VST3 and an uninstaller; it is not a standalone music application.

## Final artifact

- File: `MIDIComposer-VST3-Setup-0.1.0-dev-Windows.exe`
- Size: **4,337,572 bytes**
- SHA-256: `2cf09a0b653e485f1ab4b15bf04cf1c5da296e58f5b3d88c024b75d52b0f50f1`
- Authenticode: **NotSigned**. No certificate was available or used.
- Compiler: **NSIS 3.12**, portable, using zlib compression; compilation completed without warnings.
- Format: Unicode Windows installer, standard administrator manifest. The installer engine is x86 and installs the validated Windows x64 VST3 on 64-bit Windows 10 or later.

## Checks actually performed

The generated EXE was treated as an archive by the independent **7-Zip 26.05** console utility. The installer itself was **not executed**.

1. Compressed-archive integrity test completed with **Everything is Ok**.
2. Extracted its payload into a fresh isolated project folder.
3. Verified **all 19 manifest-listed payload files** against their original byte lengths and SHA-256 values. This includes the full VST3 bundle, original icon, documentation and third-party notices.
4. Verified that the embedded payload manifest is byte-identical to the separate manifest.
5. Verified that the generated `Uninstall.exe` is present and that no other EXE, including a standalone instrument, is in the payload. Temporary NSIS runtime helper DLLs are ordinary installer components, not music apps.
6. Inspected the script and generated uninstall include. Install targets are the fixed product documentation directory and the fixed Common Files VST3 bundle directory. Uninstall deletes only named product files and then empty product directories; no recursive parent-folder deletion is present. It checks the original uninstaller directory and blocks replacement/removal when the plugin cannot be exclusively opened.

The source VST3 bytes in the installer have SHA-256 `08f1d201ad024df77629a06e32b06318dae87cb7db0f2f579f89b75092e967ef`. This is the musical-variety/recent-pattern build that passed 97,770 engine/MIDI, 2,554 processor and 857 UI assertions, plus independent pluginval level 5 with editor lifecycle checks. Packaging did not change those plugin bytes. This separate report is updated after installer compilation; the EXE's own checksum is not embedded in its payload.

## Expected installation behavior

Setup requests the normal Windows administrator approval, then its short wizard installs the complete bundle to `C:\Program Files\Common Files\VST3\MIDI Composer Dev.vst3`. Product documentation and the uninstaller go to `C:\Program Files\MIDI Composer Dev`. It creates an Installed apps uninstall entry for **MIDI Composer Dev VST3**. It does not change FL Studio settings, run FL Studio, use a downloader or contact a server.

A direct GitHub release-asset link can download this single EXE. Running it is a separate action and may show Windows unsigned-publisher/reputation prompts. The release publisher must retain checksums and notices and satisfy the framework licensing requirements described in THIRD_PARTY.md.

## Not performed

- No actual Windows install/uninstall transaction, administrative prompt interaction or Installed apps registration was run.
- No FL Studio scan, host loading, MIDI file drag/import or live-routing test was performed during installer verification.
- No code signing, external security audit or malware-free guarantee is claimed.
- GitHub publication and online-backup verification are performed separately by the primary task; this document does not assert that a public release already exists.

Reproducible compiler instructions, tool download hashes and verification commands are in `installer/BUILD.md`, `scripts/build-installer.ps1` and `scripts/verify-installer.ps1` in the private source. The separate machine-readable results are `Installer-Validation.json` and `Installer-Payload-Manifest.json`.
