# Ghost Note implementation and testing report

**Ghost Note by TwonOnDaBeat — v0.2.0-dev, Windows x64.** This report separates implemented behavior, recorded evidence and remaining checks. It is not a production-readiness or security certification.

## Final artifact evidence

The final extended-scale VST3 passed the complete build and acceptance run. The record below refers to that exact artifact; installer and host outcomes are identified separately.

| Check | Final v0.2 result |
|---|---|
| Engine and MIDI acceptance | 3,932,337 passed |
| Processor/state/transport acceptance | 3,354 passed |
| Interface workflow/labels/layout | 1,406 passed |
| CTest suites and elapsed time | 3/3 suites passed in 8.03 seconds |
| Independent pluginval level 5 | SUCCESS (strictness 5; GUI lifecycle enabled) |
| Final VST3 binary SHA-256 | d1861a10b020147da90e215918461428a27a4cd5c1e6096a4148c8bc9a631b9c |
| Installer extraction and payload hashes | See the separate final installer verification record. |
| Actual Windows installation | Not performed during packaging; installed-copy verification is a separate follow-up. |
| FL Studio loading, drag, multitrack import and live routing | Not yet verified for this build. |

Earlier v0.1 test counts and hashes do not establish a pass for this redesigned v0.2 artifact. Private validation logs retain the development history.

## Implemented behavior

The offline C++17 engine and JUCE VST3 share the arrangement used by preview playback, editing, state and MIDI export. The main workflow is **Genre → Key/Scale → Tempo → Complexity → Print**. Melody, Chords, Countermelody and Bass start enabled and follow one harmonic timeline. A legacy complementary chord layer remains available in advanced controls.

There are 24 genre rule profiles with different progressions, phrasing, bass attacks, chord articulation, register and harmonic pacing. The library contributes bounded aggregate onset, duration, interval, chord-voicing-gap and reliable chord-transition statistics. Genre names inferred from source folders are weak hints. Voice leading and shared harmony coordinate the parts, with a restrained corpus-derived chord-spacing preference. Five observed cross-role source pairs are not presented as a trained arrangement model. See LIBRARY-METHOD.md.

The selected-scale catalog contains the 37 formulas audited from installed FL Studio 2025/2026 reference scores plus Chromatic, transposed through all 12 roots. Strict Scale constrains generation and edited pitches. Scale names, highlighting, chord notes, persistence and MIDI scale text must agree. There is no verified claim of complete Cymatics MIDI Printer Pro/MAX scale parity. This is twelve-tone equal-tempered MIDI, not a microtuning engine.

Print keeps the committed A arrangement intact. B can be auditioned, kept or discarded. Printing again archives the previous B in Ideas before replacing it. Part regeneration, exact locks, small variations, selected bars and rhythm/pitch-preserving modes remain available. Explicit seeds reproduce settings and statistical-profile snapshots. Recent-pattern memory persists with projects; bounded repeat avoidance is best effort.

The actual piano roll supports note add/delete, move/resize, multi-selection, velocity, strict-scale snapping, straight/triplet grids, zoom and scroll. Per-part enable, lock, mute, solo, channel, sound and gain are distinct controls. MIDI can be dragged or exported individually, or written as a Type 1 multitrack arrangement. Projects retain exact note edits and a pending candidate. The program validates bounded project size, note ranges, timing and malformed state data.

## Timing and compact interface

Default size is **920 × 650**, minimum **880 × 600**, with drag enlargement. Four output rows have real note previews and individual MIDI export. The selected-part piano roll uses the full width until the Advanced drawer opens. Original ghost artwork and the exact **by TwonOnDaBeat** credit identify the instrument; VST3 and Windows publisher metadata use TwonOnDaBeat.

Auto Beat Scale suggests ½× at 140 BPM and above, 2× below 70 BPM, otherwise 1×. Manual choices override it. At 180 BPM, both 1× and ½× retain **32 quarter-note beats / eight host bars / 10.6667 seconds**. Half-time provides a slower 90 BPM feel without changing host tempo. Editing snap is separate and defaults to **½ beat**. A tempo change does not silently regenerate accepted MIDI.

## Completed input audits

The library scan found 10,868 MIDI files, accepted 2,111 unique pitched streams, excluded 649 percussion streams and quarantined 6,586 uncertain streams. The analyzer passed 27 checks and the plugin-profile exporter passed five separate checks, including the chord-voicing-gap profile. All original file hashes matched after analysis; no input MIDI was modified or redistributed. Duplicate and unsupported files are recorded separately.

The FL reference-scale audit parsed all 37 installed formulas, compared the 2025 and 2026 definitions, passed 17 parser/catalog checks and 444 root-transposition checks, and independently cross-checked eight familiar formulas. All 74 original reference-score hashes matched afterward. The plugin contains numeric scale facts, not copies of the proprietary score files. Some named traditions have multiple variants; these formulas establish compatibility with the audited FL installation.

## Validation boundaries

- Engine tests need to establish correct scale membership, shared harmony, exact seeded replay and locks, all selected timing modes and valid exported MIDI. Processor tests cover actual candidates, editing, project/state restoration and simulated transport, including note on/off consistency and export agreement.
- UI tests render the actual JUCE component, check exact dropdown strings and geometry, and exercise Print/reprint, preserved A, four populated parts, discard and the Advanced drawer. A rendered component is not an FL Studio screenshot or a full manual usability session.
- Independent pluginval loading, processing and editor lifecycle checks are separate from FL Studio compatibility. A separate Steinberg validator pass is not claimed unless explicitly recorded.
- Installation, uninstallation, FL Studio discovery, actual MIDI dragging, multitrack import, live routing and host project reopening require their own outcomes. Standard installation instructions are not proof those operations succeeded here. FL Studio search settings remain unchanged.
- Assertions do not measure artistic quality. Genre listening review, acoustic realism, broad physical-device testing and per-monitor display-scaling behavior remain separate assessments.

Eight original oscillator/envelope preview sounds are synthesized approximations. MIDI contains no preview audio, samples or instrument-specific glide implementation. The receiving instrument determines final tone and articulation.

History and favorites are project-scoped and capped at 24 entries each; undo/redo retains 40 session snapshots. Project data is limited to 8 MB and 4096 notes per part. Mute/Solo affect audition; MIDI export includes enabled muted parts. Overlapping same-pitch events on shared output channels are rejected when ambiguous.

The product is **VST3 only** and unsigned. There is no standalone music app, runtime account, telemetry, remote-control feature or network downloader. Source inspection and bounded input checks do not guarantee security. The owner confirmed use of or eligibility for JUCE Starter; that is self-reported eligibility, not independent license certification.


