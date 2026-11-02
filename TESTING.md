# Implementation and testing report

Windows x64 development milestone, 1 November 2026. This report distinguishes working code and checks from tests that were not performed. It is not a production-readiness or security certification.

## Implemented

The C++17 engine is linked into the Windows VST3. The owner's latest instruction sets the final scope to **VST3 only**. It provides six procedural style profiles, diatonic harmony with automatic inversions and voice leading, five related part roles, half/normal/double-time phrasing, independent musical controls, seeded regeneration, selected-bar regeneration, exact lock preservation, and portable Type 1 MIDI writing.

The JUCE interface implements recoverable A/B candidates, Keep/Discard, project-scoped generation history and favorites, undo/redo, per-part enable/lock/mute/solo/channel/sound/level, optional Add Part controls, and an actual piano roll with note creation/deletion/movement/resizing, multiple selection, velocity, straight/triplet snapping, scale keys, scrolling and zoom. Project and plugin state retain exact accepted notes and a pending candidate. Settings are staged into candidates. No actual AI model is integrated.

The compact default is **1000 × 720**, with a **920 × 620** minimum and drag enlargement. Auto beat scale reads the current tempo and recommends half-time at 140 BPM or above, double-time below 70 BPM, otherwise normal. Manual choices override the guess. Tempo changes do not regenerate accepted MIDI. At 180 BPM, both a 180 BPM feel at 1× and a 90 BPM feel at ½× span **32 quarter-note beats / eight host bars / 10.6667 seconds**. The separate note-editing grid defaults to ½ beat.

Eight original oscillator/envelope preview sounds provide audition audio. They are honestly labeled synthesized approximations; acoustic realism has not been established by listening tests. MIDI files contain no preview audio or receiving-instrument glide data.

## Acceptance evidence

| Requirement | Actual evidence |
| --- | --- |
| Eight bars at 177 BPM with half-time feel | Engine tests retain 32 beats and 10.8474576 seconds; slower motif, chord and bass pacing tested separately from density. Actual stereo WAV contains 520,678 frames at 48 kHz, approximately 10.84746 seconds. |
| 180 BPM normal or 90 BPM half feel, same loop | Processor tests exercise manual 1× and ½× and Auto suggestions, preserving 32 beats / 10.6667 seconds. |
| Regenerate countermelody without altering locked bass/melody | Tests compare note pitches, starts, durations and velocities exactly, including deliberate unusual manual edits. |
| Candidate audition/discard recovers current | Real processor tests exercise A/B, generation, rejection of a second unresolved candidate, Keep/Discard, undo/redo, and manual A edits while B exists. |
| Counter chords follow main harmony | Scale/chord membership, upper register and restrained velocities tested across all roots/styles/feels. |
| Strict Scale generation and editing | All 12 roots, major/minor, styles and feels tested; actual edit API snaps pitch and preserves valid MIDI range. |
| Editor data, playback and export agree | Real edited arrangement feeds schedule and exporter. Live pitch, velocity, onset and duration compared against authoritative notes to one sample; exported MIDI compared with engine bytes. MIDI file timing rounds to 960 PPQ. |
| State and projects restore | Actual project JSON and asynchronous plugin-state callbacks restore current/candidate notes, flags, sounds and preferences; malformed, nested, oversized and out-of-range projects rejected. |
| Host transport robustness | Simulated host tests cover starts/stops, looping, seeking, negative preroll, extreme finite positions, tempo changes and candidate switches without unmatched active notes. |
| VST3 can load and process | Independent pluginval level 5 checks pass, including editor lifecycle and processing. This is not an FL Studio test. |
| Product format | Final build and delivery target VST3 only. Earlier development built a standalone app, but the owner removed it from scope; no standalone app is included in the download. |
| FL Studio loading, MIDI drag, multitrack import and live routing | **Not tested.** FL Studio 2025 launched, but no plugin search path was added and no plugin was installed/scanned. The owner explicitly chose to keep FL Studio search settings unchanged. |

The final musical-variety build passed all three automated suites: **97,770 engine/MIDI**, **2,554 processor**, and **857 UI label/layout assertions**, in a recorded 1.96 seconds. Independent pluginval level 5 also completed with **SUCCESS**, including editor lifecycle checks, on this updated VST3. The plugin binary SHA-256 is `08f1d201ad024df77629a06e32b06318dae87cb7db0f2f579f89b75092e967ef`. Build versions and validation details are recorded in **BUILD_VALIDATION.md**. Raw logs are retained only with private source. **UI_VALIDATION.md** documents the actual component renders and label checks; these do not simulate a running FL Studio window.

## Reported dropdown defect and visual revision

The owner reported corrupted words/symbols in dropdowns and an unfinished visual appearance. The original MSVC compile command lacked an explicit UTF-8 source/execution setting, and narrow text entered JUCE through an ASCII conversion. The revised build adds `/utf-8`, explicit UTF-8 conversion for Unicode labels, custom readable combo and popup rendering, and checks of exact item text and Unicode code points. The initial UI regression run caught the remaining incorrect conversion after the compiler setting alone was changed. Original artwork is embedded in the revised instrument; its prompt and built-in generation provenance are in ARTWORK.md. These changes preserve the music engine and compact resizable workflow.

## Limits and remaining work

- No completed FL Studio integration claim: file dragging, multitrack import, live routing, host project reopening and wrapper behavior still require separate host tests. Setup instructions describe the documented host routes, not verified outcomes for this build.
- No full manual piano-roll usability session, physical-device listening review or broad Windows display-scaling matrix was completed. Offscreen renders and pluginval editor checks cover narrower conditions.
- History/favorites are scoped to each project and capped at 24 entries each; undo/redo retains 40 session snapshots. There is no cloud library or automatic disk backup. Save a composition project or FL Studio project explicitly.
- Key help ranks generated ranges as a starting-point heuristic. It is not a vocal-performance analysis and does not automatically rewrite the lead into a supplied vocal range.
- Major/natural minor are implemented; additional advanced scales, drums, textures, audio rendering/export controls and host-automatable composition parameters are not included in this milestone. The demo WAV is a validation render from actual synthesis, not an application audio-export feature.
- Preview voices have no sample library, detailed acoustic modeling, per-note slide messages or user sound import. FL Studio supplies the audio device; the plugin does not select a separate audio driver.
- Playback/export use enabled parts. Mute and Solo affect audition/live output; MIDI export intentionally includes enabled muted parts. Choose distinct MIDI channels for independent parts; ambiguous overlapping same-pitch events on a shared channel are rejected with an explanation.
- Project files are limited to 8 MB and 4096 notes per part. The app exports MIDI; it does not parse arbitrary MIDI imports. No hostile-input fuzzing campaign or external penetration test was performed.
- Runtime code contains no account, telemetry, remote-control feature, downloader or application network listener. This is source/design inspection, not a guarantee that software is invulnerable. Review dependencies and licenses before distribution.
- Builds are unsigned. No certificate was available. Checksums accompany the artifacts, and signing instructions are provided for an authorized certificate holder.
- GitHub repositories **Terpytoine/midi-composer-source** (Private) and **Terpytoine/midi-composer-downloads** (Public) were created. The public repository has release immutability enabled and its collaborator page reports zero collaborators and that only the owner can contribute. Source backup upload, draft release assets, final publication and remote-download verification are separate steps; repository existence alone does not establish a verified backup. Source is retained privately as a complete archive, not as a public source tree. The owner confirmed use of or eligibility for JUCE Starter within its revenue/funding limit; this is self-reported rather than independently certified.
- A final product brand remains unselected. The neutral development label continues; naming ideas are unverified.

Desktop automation was stopped when the owner pressed Escape during local-app inspection. Subsequent code, rendering and packaging checks used development tools. A later owner-authorized GitHub publishing session is separate from those local UI checks.

## Musical variety and recent-pattern avoidance

New Idea makes up to 32 attempts against up to 64 recent pitch/onset fingerprints per role and arrangement. Fingerprints round onsets to 1/12 beat and ignore velocity, sound, gain, note gate and tiny humanization changes, so those small changes do not count as a new underlying idea. The project's recent fingerprints include discarded candidates and are saved/restored with project state. New instances start with fresh seeds, while an explicit seed request can intentionally reproduce an idea.

Checks passed for 24 successive distinct discarded melody candidates and eight further distinct ideas after project restoration. In all six styles, at least 48 of 64 tested seeds produced distinct melody structures; same-seed determinism also passed. This is bounded best effort. It does not guarantee that a phrase is globally unique, that nothing similar exists in other music, or that every constrained regeneration produces different notes. Locks and intentionally preserved motifs remain meaningful constraints.

## Installer release preparation

The product remains VST3 only. A separate EXE packages the verified plugin as an offline Windows installer, with an uninstaller and the required notices. Its name is **MIDIComposer-VST3-Setup-0.1.0-dev-Windows.exe**. The installer itself has a separate published checksum and verification record; this embedded report does not attempt to contain the checksum of its own enclosing EXE.

Installer verification uses NSIS compilation plus independent 7-Zip archive integrity/extraction and comparisons of every manifest-listed payload file, including the generated uninstaller. Packaging must leave the verified VST3 bytes unchanged. The installer is not executed during those checks, so installation, uninstallation and FL Studio scanning are not verified outcomes. See the separately updated INSTALLER_VALIDATION.md and installer checksum for the actual release artifact's evidence. Source, installer scripts, artwork and current validation records must be backed up privately before local cleanup.
