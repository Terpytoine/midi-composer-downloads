# MIDI Composer VST3 — v0.1.0-dev

Windows x64 development prerelease. Download and run **MIDIComposer-VST3-Setup-0.1.0-dev-Windows.exe** to install the VST3. No standalone music app is included. The raw VST3 ZIP remains an alternative for manual installation.

## Included workflow

- Connected melody, bass, chords and optional countermelody/chord layer across one harmonic timeline.
- Eight host bars by default, Auto or manual ½×/1×/2× Beat Scale, and a separate half-beat editing grid. At 180 BPM, ½× and 1× both occupy 32 beats / 10.67 seconds.
- Candidate A/B, Keep/Discard, exact part locks, independent regeneration and smaller variations.
- Piano-roll note editing, velocity, scale highlighting, straight/triplet snapping, zoom and scrolling.
- Editable part and multitrack MIDI export, drag files, project/plugin state, undo/redo, history and favorites.
- Compact resizable ink-and-copper interface, original artwork and corrected Unicode dropdown labels.

New Idea now retries up to 32 times against 64 recent pitch/onset fingerprints per role and arrangement. Recent ideas include discarded candidates and survive project save/restore. Default instances use fresh seeds, and explicit seed requests still reproduce an idea. Fingerprints ignore sound, velocity, gain, gate and tiny timing changes. This is best effort; it does not promise that a melody is globally unique or that a musical phrase has never existed elsewhere. Locks and preserved motifs can intentionally retain material.

## Verification and limits

The final plugin passed all three suites: 97,770 engine/MIDI, 2,554 processor and 857 UI assertions. Independent pluginval level 5 completed with SUCCESS, including editor lifecycle checks. Musical-variety checks covered 24 distinct successive discarded melody ideas, eight more after project restoration, and at least 48 distinct melody structures across 64 seeds for every style. See the accompanying reports and separate installer verification record for exact artifact checks.

The installer and plugin are unsigned. Actual installation/uninstallation and FL Studio host loading, MIDI drag/import and live routing were not performed during packaging. Host search settings remain unchanged. Preview sounds are original synthesized approximations; final instruments are selected in FL Studio. The software operates offline without an AI-model service or account.

Source remains in a private owner-controlled repository. This public repository is for approved downloads and documentation. Publication, repository protections and remote-backup verification are separate release steps; local cleanup follows only after verified backups and the owner's concrete cleanup approval.
