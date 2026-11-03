# Ghost Note installer verification

Ghost Note by TwonOnDaBeat v0.2.0-dev, Windows x64. Verification completed on 3 November 2026.

- EXE: `Ghost-Note-VST3-Setup-0.2.0-dev-Windows.exe`
- Size: 5,794,805 bytes.
- SHA-256: `fa5ac611057c157b80f30c21559a41b97c419f621514381af22260b71a9647e6`.
- VST3 binary SHA-256: `d1861a10b020147da90e215918461428a27a4cd5c1e6096a4148c8bc9a631b9c`.
- Product metadata: Ghost Note by TwonOnDaBeat. Publisher metadata: TwonOnDaBeat.
- Authenticode: NotSigned. No certificate was used.

NSIS 3.12 compiled the Unicode installer. Independent 7-Zip 26.05 archive testing and extraction passed. All 21 manifest-listed payload files matched their source lengths and SHA-256 hashes. The embedded payload manifest matched the separately published manifest. The generated uninstaller is present; no standalone music app is included.

The payload is the exact VST3 that passed 3,932,337 engine/MIDI, 3,354 processor and 1,406 UI assertions, plus independent pluginval strictness 5 with editor lifecycle checks. Packaging does not alter those plugin bytes. The EXE checksum is recorded here after compilation and is not embedded in its own payload.

Setup uses the standard Common Files VST3 folder and a dedicated Ghost Note documentation/uninstaller folder. The installer does not change FL Studio search paths, start FL Studio, download software or contact a server. Uninstall removes only manifest-listed product files and empty product directories, with no recursive shared-parent deletion.

This packaging record covers extraction, integrity and metadata. Installation on the owner's computer is a separate follow-up check; successful install/uninstall transactions and FL Studio host loading, drag/import and live routing are not established by this report. No signing, external security audit or malware-free guarantee is claimed.

The versioned payload manifest and installer validation JSON accompany the release. Reproducible commands are in the private source's installer/BUILD.md and scripts.
