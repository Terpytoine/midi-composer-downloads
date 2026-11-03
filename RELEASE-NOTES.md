# Ghost Note by TwonOnDaBeat — v0.2.0-dev

Windows x64 VST3 development prerelease. Run **Ghost-Note-VST3-Setup-0.2.0-dev-Windows.exe** to install the plugin. No standalone music app is included. The manufacturer shown to hosts is **TwonOnDaBeat**.

## New in this build

- A continuous printer workflow: Genre, Key, Scale, Tempo, Complexity and one **Print** action.
- Four coordinated outputs from the start: Melody, Chords, Countermelody and Bass, each with note previews, drag and MIDI export.
- A compact 920 × 650 resizable interface, full-width selected-part editor, expandable Advanced drawer and original Ghost Note artwork.
- 24 genre profiles with different harmony, phrasing, chord articulation and bass behavior.
- All 12 roots and 38 scale options, based on 37 audited FL Studio reference formulas plus Chromatic.
- Bounded library-pattern guidance from 2,111 unique accepted pitched streams. Percussion and uncertain material are excluded from the embedded statistics; original MIDI is not distributed.
- Reprinting keeps committed A intact and archives the previous B in Ideas. Keep/Discard, locks, variations, editing, state recall, explicit seed replay and recent-pattern avoidance remain available.
- Auto/manual ½×, 1× and 2× feel with eight host bars by default and a separate half-beat editing grid.

At 180 BPM, ½× and 1× both fill 32 beats / eight host bars / 10.67 seconds. Preview sounds are original synthesized approximations; the receiving FL Studio instrument supplies the final exported-MIDI sound.

## Verification and limits

The final build passed **3,932,337 engine/MIDI**, **3,354 processor** and **1,406 UI** assertions. Complete CTest result: **3/3 suites passed in 8.03 seconds**. Independent VST3 validation: **SUCCESS (strictness 5; GUI lifecycle enabled)**. The final VST3 hash is recorded in BUILD_VALIDATION.md; installer evidence is recorded separately after packaging. Historical v0.1 results do not establish a pass for this build.

The library analyzer passed 27 checks without changing the 10,868 input MIDI files; the profile exporter passed five additional checks, including the chord-voicing-gap histogram. The FL reference-scale audit passed 17 parser/catalog checks and 444 transposition checks, with all 74 source-score hashes unchanged. Folder-derived genre hints remain unverified. The build does not claim a complete Cymatics MIDI Printer Pro/MAX scale comparison or independently established genre listening accuracy.

The installer and plugin are unsigned. Actual installation and FL Studio loading, MIDI drag/import, live routing and host recall are separate host checks; see TESTING.md for completed outcomes. FL Studio saved settings remain unchanged. Source stays private. Public release and verified backups precede project-only cleanup.


