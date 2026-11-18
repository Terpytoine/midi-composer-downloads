# Ghost Note 1.2.0 — current implementation and verification report

<a id="gatekeep"></a>

# Ghost Note 1.2.0: GateKeep expansion and actual findings

Ghost Note by **TwonOnDaBeat** remains an offline Windows x64 VST3 music printer. This update refines existing procedural/statistical rules. It does not train a machine-learning model or certify genre authenticity.

## Input and classification

Every `.mid` and `.midi` below the requested GateKeep root was examined read-only: **314 paths** across 400 directories. All 314 original SHA-256 hashes matched before and after the work. No source file was moved, renamed, overwritten or deleted.

| Finding | Count |
|---|---:|
| Accepted pitched musical streams | 112 |
| Drum/percussion files excluded | 58 |
| Uncertain files held for review | 110 |
| Valid but empty MIDI files excluded | 2 |
| Non-SMF AppleDouble sidecars excluded | 32 |
| Byte-duplicate occurrences, all sidecars | 30 |

The accepted streams comprise **59 chord, 29 melody, 23 bass and one countermelody**. Thirty-eight became newly eligible after sounding-polyphony/rolled-chord and legato analysis. No exact normalized or >=0.85 event-set near-duplicate musical pair was found under the documented tests; this is a bounded check, not proof of global originality. Seventy-four conservative correlated families prevent transpositions/versions from masquerading as independent evidence. The 112 private note-only extracts passed exact pitch/tick/gate/velocity round-trip checks.

Channels, programs, note patterns, register, overlap and stable sounding pitch sets support role decisions; names are supporting context. Uncertain percussion/voice mixtures stay in review. There was no defensible accepted same-container cross-role pairing, so the update learns no claimed source-stem relationships.

## What actually enters generation

The first rubric identified 20 candidates. Critical review held back one EBK 808 and two Trap 808 candidates: generic pitched bass and filenames did not establish those styles. **Seventeen streams across ten conservative role/source families** supply weak, root-independent aggregates to four existing models:

| Existing model | Used streams | Role families | Changes implemented |
|---|---:|---:|---|
| R&B | 2 | 1 | Small chord articulation/voicing preferences; no functional-harmony inference from conflicted key labels |
| EBK / Dark NorCal | 2 | 2 | Bounded melody articulation/interval/optional-attack guidance and separate clipped chord guidance |
| Modern LA | 3 | 1 | Weak articulation and compatible inversion/voicing tie-breaking; rolled finger entries are not learned as a groove |
| Classic G-Funk | 10 | 6 | Bounded stepwise lead/bass movement, optional attacks, articulation and compatible chord spacing |
| Each of the other 23 existing models | 0 | 0 | Existing catalog and musical rules retained |

Trap, Afrobeats, Drill, Lo-fi, the electronic styles and the remaining models receive no unsupported GateKeep assignment. Ninety-two accepted streams were initially genre-unassigned; three additional weak candidates are held out after critical review. Exact source decisions and every uncertain file are retained in private review records.

Actual monophonic interval weights in the balanced G-Funk lead set put approximately 0.2811 on one semitone and 0.4897 on two; bass gives approximately 0.2280 and 0.5217. Stable harmony favors adjacent three/four-semitone gaps near 0.3651/0.3828. These measured local patterns are not universal genre rules. EBK melody and chord articulation remain separate evidence. LA V1/V2/V3 are one correlated family.

Each source histogram is normalized, averaged within its correlated family, then equally averaged across families. The role strength is capped by the weakest supported field: **0.025**, except G-Funk melody **0.075**. These are engineering blending limits, not confidence/quality percentages. Authored genre grammar, motif structure, voice-leading/register costs and the selected exact scale remain primary. New hooks are required in the West Coast branches, which previously bypassed statistical helpers; the update now has demonstrated runtime influence.

The earlier catalog already contained 304 of these paths, and 12 initial candidates appeared in the prior bounded West Coast study. Existing global distributions and all historical sample counts are preserved. No files are blindly appended and counted twice. No raw notes, complete phrases or reference MIDI are embedded in the plugin. Three higher West Coast style IDs are added to the catalog without changing any of the 27 stable style IDs.

## Metadata and reliable limits

All 282 valid SMFs contain tempo and meter events; none contain embedded key signatures. Embedded BPM is timing metadata, not proof of the intended production tempo. Thirteen accepted streams conflict with filename BPM hints. Forty-eight accepted keys remain ambiguous, 64 have statistical estimates, and eight conflict with filename key collections. No tonic, scale degree or chord progression is learned from these uncertain labels. Chord names/inversions are conditional pitch-set interpretations.

Analysis records gates, velocities, intervals, register, syncopation, repeated phrases, sounding sonorities and voice motion. The runtime only uses eligible aggregate onset, duration, interval and voicing-gap fields. This update does not claim learned velocities, complete phrase development, source-stem relationships, or new harmonic-degree sequences.

## Completed validation and what still needs listening

The Release VST3 passed **CTest 5/5**: 4,515,350 engine, 198,071 scale-adviser, 1,242,390 reference-prior, 5,909 processor and 9,154 UI assertions. All 38 scales, twelve roots and three feels are exercised by the new safety tests. Saved actual prior support/counts/weights and canonical layers round-trip; invalid influence cannot replace valid music. Legacy projects still default to no new prior. The component/controller IDs, one-sheet workflow, manual scale, Undo/Redo, Stop/Mute, host feel and layer export remain.

Tracktion pluginval 1.0.4 passed strictness 5, exit 0, seed 180002, with editor tests enabled. Current rendered default/minimum layouts and scale menu were visually reviewed. The separate Steinberg validator is not configured and is not claimed as passed.

The actual paired audit verified **3,312 MIDI exports / 1,656 paired settings**. All were valid Type-0/channel-1, full eight-bar exports with legal balanced notes and correct tempo/meter. Twenty-three unsupported models retained identical notes and exported bytes. All paired harmonic roots, chord qualities and region timings remain unchanged; LA and G-Funk each changed one compatible voicing in the tested set. Actual continuous gate changes and feature distributions are in [the full output comparison](#comparison).

Some measured reference distances improved, while others were unchanged or slightly farther away. For example, G-Funk lead attack JS distance moved 0.467904 to 0.429314; EBK and LA chord-attack distances moved slightly farther. This is not an overall quality score or evidence of heard improvement. No arbitrary progression walk was added to inflate variety.

Complete-score and enabled-role comparisons against all 112 accepted extracts found zero exact/transposition-normalized or quarter-grid complete matches. A limited seventeen-attack coarse phrase screen found zero flagged output roles. These checks do not prove originality against all possible excerpts or external music.

Eight private A/B WAVs use installed Vital/Serum 2 with the same instrument mappings and authored genre contexts: R&B 82 BPM, EBK 90, LA 100, G-Funk 94. Independent PCM checks passed stereo 48 kHz/24-bit, finite/non-silent/unclipped and expected duration. The assistant cannot hear them. Synthesized piano/keys are approximations, there is no full drum production, and synth bass does not automatically provide 808 glide. **Human listening and updated 1.2 DAW acceptance remain pending.**

## Reproduce and review

Private project records retain all source paths/hashes, confidence rubric scores, classification reasons, metadata conflicts, duplicate/correlation groups, accepted extracts and manual-review items. Rubric scores are uncalibrated evidence scores, never probabilities of genre authenticity. Private pipeline tools and the curated numeric aggregate make this update reproducible. Source/reference backups remain separate from public downloads. Original library files and user projects are preserved.

The owner-facing local GateKeep listening page provides paired MIDI, role JSON, audio and downloadable review feedback. The public VST3 contains aggregate statistics only. Existing 1.1.0 remains a separately preserved, verified baseline.


<a id="comparison"></a>

# GateKeep: actual before/after MIDI findings

Verified **3312 actual MIDI exports** across 1656 paired settings. Twenty-three unsupported models retained identical exported bytes and authoritative notes. All paired harmonic roots, qualities and region timings remain unchanged.

| Model | Pairs | MIDI changed | Voicings changed |
|---|---:|---:|---:|
| Melodic Rap | 40 | 0 | 0 |
| Trap | 40 | 0 | 0 |
| R&B | 184 | 184 | 0 |
| Drill | 40 | 0 | 0 |
| Bay Area | 40 | 0 | 0 |
| Dark Latin Guitar | 40 | 0 | 0 |
| Pop | 40 | 0 | 0 |
| House | 40 | 0 | 0 |
| Techno | 40 | 0 | 0 |
| Drum & Bass | 40 | 0 | 0 |
| Lo-fi | 40 | 0 | 0 |
| Jazz | 40 | 0 | 0 |
| Afrobeats | 40 | 0 | 0 |
| Reggaeton | 40 | 0 | 0 |
| Rock | 40 | 0 | 0 |
| Ambient | 40 | 0 | 0 |
| Funk | 40 | 0 | 0 |
| Disco | 40 | 0 | 0 |
| Country | 40 | 0 | 0 |
| Gospel | 40 | 0 | 0 |
| Classical | 40 | 0 | 0 |
| Blues | 40 | 0 | 0 |
| Dubstep | 40 | 0 | 0 |
| Trance | 40 | 0 | 0 |
| EBK - Dark NorCal Piano | 184 | 184 | 0 |
| LA - Modern West Coast | 184 | 184 | 1 |
| Classic G-Funk | 184 | 184 | 1 |

All exports passed Type-0, channel-1, full 32-beat loop, tempo/meter, balanced note-on/off and legal note checks. Engine validation plus all-scale acceptance checks cover exact selected scales.

Compared complete scores and enabled roles against 112 accepted private extracts with transposition/initial-silence normalization and exact or nearest-quarter-beat timing/gates: **0 matches**. Seventeen-attack top-line phrase screen: **0 generated role examples flagged**. These bounded checks do not prove universal originality.

| Model ID / role | Feature | Before JS | After JS | Direction |
|---|---|---:|---:|---|
| 2 / 3 | onsets | 0.000000 | 0.000000 | unchanged or farther |
| 2 / 3 | durations | 0.052122 | 0.052122 | unchanged or farther |
| 2 / 3 | voicingGaps | 0.272124 | 0.272124 | unchanged or farther |
| 24 / 0 | onsets | 0.698040 | 0.695844 | closer |
| 24 / 0 | durations | 1.000000 | 1.000000 | unchanged or farther |
| 24 / 0 | intervals | 0.240516 | 0.222239 | closer |
| 24 / 3 | onsets | 0.096223 | 0.097192 | unchanged or farther |
| 24 / 3 | durations | 0.027656 | 0.026943 | closer |
| 24 / 3 | voicingGaps | 0.043062 | 0.043062 | unchanged or farther |
| 25 / 3 | onsets | 0.208065 | 0.209107 | unchanged or farther |
| 25 / 3 | durations | 0.384880 | 0.385030 | unchanged or farther |
| 25 / 3 | voicingGaps | 0.090077 | 0.089951 | closer |
| 26 / 0 | onsets | 0.467904 | 0.429314 | closer |
| 26 / 0 | durations | 0.538155 | 0.536917 | closer |
| 26 / 0 | intervals | 0.343489 | 0.338597 | closer |
| 26 / 2 | onsets | 0.372060 | 0.351874 | closer |
| 26 / 2 | durations | 0.363651 | 0.362887 | closer |
| 26 / 2 | intervals | 0.441227 | 0.438296 | closer |
| 26 / 3 | onsets | 0.003686 | 0.003686 | unchanged or farther |
| 26 / 3 | durations | 0.016887 | 0.016887 | unchanged or farther |
| 26 / 3 | voicingGaps | 0.176705 | 0.176513 | closer |

Continuous articulation can move within a duration bin while the binned score stays unchanged. The following means are measured in musical pulses. The target is an approximation from family-balanced reference duration-bin centers, not a prescribed note length or a genre-quality score.

| Model ID / role | Approx. reference mean | Before mean gate | After mean gate |
|---|---:|---:|---:|
| 2 / 3 | 3.8000 | 3.6006 | 3.6056 |
| 24 / 0 | 1.4688 | 0.3564 | 0.3605 |
| 24 / 3 | 0.4091 | 0.3605 | 0.3622 |
| 25 / 3 | 2.8205 | 2.5858 | 2.5713 |
| 26 / 0 | 0.7751 | 0.4948 | 0.5106 |
| 26 / 2 | 0.3512 | 0.3513 | 0.3513 |
| 26 / 3 | 3.6167 | 6.6419 | 6.5900 |

JS compares aggregate distributions to the curated local prior; lower distance means closer on that one feature. It is not a listening score. Role 0 is melody, 2 bass and 3 chords. Source and generated register, instruments, accompaniment, expression and arrangement remain separate concerns. No heard improvement, human genre verdict or broad all-genre certification is claimed.

The standard audit includes twenty controlled and twenty varied cases for all 27 styles. The additional 576 paired cases cover four affected styles, all twelve roots, four true scales, three tempos and three feel settings. The separate engine tests exercise all 38 scales with every root and feel. Original material and uncertain classifications stay private.


<a id="testing"></a>

# Ghost Note 1.2.0 validation

The current Windows x64 Release binary is **b55ea5f50767039ef388c891a615446b92bcb6a2d97ae5032b622bb8742b5bf0**. CTest passed 5/5 in 30.07 seconds: engine 4,515,350; scale adviser 198,071; reference priors 1,242,390; processor 5,909; UI 9,154 assertions. Actual default/minimum renders and menu were reviewed. Pluginval 1.0.4 strictness 5 passed, exit 0, seed 180002; GUI/editor tests enabled; separate Steinberg validator skipped because no path is configured.

[GateKeep evidence](#gatekeep) separates all completed input/algorithm/output checks from human judgment. [Actual before/after findings](#comparison) cover 3,312 MIDI exports, 23 unchanged models, mixed reference-feature results and bounded similarity checks. Eight actual-instrument A/B WAVs were technically verified; the assistant could not hear them.

Updated 1.2 Windows installation, owner DAW routing/recall/Stop/Mute/export and subjective genre acceptance remain pending. Installed 1.1.0 was separately verified against all 18 payload hashes; the explicitly approved obsolete VST3 bundle was removed after that verification. That is historical installation evidence, not a claim that 1.2 is installed.

See [Release build](#buildlog), [CTest](#ctestlog), [pluginval](#pluginvallog), and [installer integrity](#installer). Technical validity and uniqueness are not musical quality or authenticity scores. The user is performing DAW/listening acceptance.


<a id="build"></a>

# Ghost Note 1.2.0 build verification

Product Ghost Note; manufacturer TwonOnDaBeat; PE file/product and module version 1.2.0. Exact DLL SHA-256 **b55ea5f50767039ef388c891a615446b92bcb6a2d97ae5032b622bb8742b5bf0**. Stable component `ABCDEF019182FAEB4D6364764D633031`; controller `ABCDEF011234ABCD4D6364764D633031`. The build targets VST3 only.

MSVC 19.44.35229, portable Windows SDK 26100, CMake 4.4.5, Ninja and pinned JUCE 8.0.16-security commit ea77444750de45e036e0279bb0291144bf8e3688. Fresh JUCE/helper compiler probes explicitly use Release to avoid the portable Debug PDB service requirement. Static runtime.

CTest 5/5 passed in 30.07 seconds. Pluginval 1.0.4 strictness 5 passed with editor enabled, seed 180002, exit 0, at 44.1/48/96 kHz, blocks 64/128/256/512/1024 and automation subblocks 32. Separate Steinberg validator skipped, no path supplied. [Testing and scope](#testing) records exact assertion counts and pending owner checks; [GateKeep output evidence](#comparison) records actual MIDI comparisons. No subjective listening or owner 1.2 DAW completion is claimed.


<a id="installer"></a>

# Ghost Note 1.2.0 installer verification

The Windows x64 owner-validation installer passed independent CRC and extraction verification. It is unsigned. Actual 1.2 installation and owner DAW acceptance remain pending.

| Item | Verified result |
|---|---|
| Setup EXE | Ghost-Note-VST3-Setup-1.2.0-Windows.exe |
| Bytes | 7,119,964 |
| Setup SHA-256 | 61f16b72521e60ff3b2ccb47f6bb2a77a52fea3f979c6ea4e54775151b2849c9 |
| Exact VST3 SHA-256 | b55ea5f50767039ef388c891a615446b92bcb6a2d97ae5032b622bb8742b5bf0 |
| Payloads checked | All 18 listed files, each exact SHA and byte count |
| Embedded manifest | Matches external payload manifest |
| Product / vendor / version | Ghost Note / TwonOnDaBeat / 1.2.0 |
| Stable component ID | ABCDEF019182FAEB4D6364764D633031 |
| Standalone music application | None |
| Uninstaller | Present |

The static installed guide and notices accompany the VST3. Current validation reports are delivered separately so post-build verification does not make the installed documentation stale. The installer retains saved FL search settings and uses the standard VST3 path. A hash/CRC result does not establish DAW behavior, musical quality or listening acceptance. See TESTING.md and GATEKEEP-EXPANSION.md.

The earlier installed 1.1.0 matched all 18 payloads and its manifest. Only the specifically approved obsolete differently named VST3 bundle was removed after that verification. No broader cleanup is claimed.


<a id="ui"></a>

# Ghost Note 1.2.0 UI verification

The current build passed 9,154 label/layout assertions. Actual 880 × 620 default, 800 × 540 minimum and dark scale-menu images from the 1.2 build were visually reviewed. The original compact layout, artwork, all 38 scale choices, stable IDs and explicit Suggest Scale interaction are retained. No editor code or artwork changed in the GateKeep update.

These checks do not establish a physical-monitor DPI matrix, accessibility coverage or manual FL Studio editing. The owner is performing DAW acceptance. Complete technical and musical scope is in TESTING.md and GATEKEEP-EXPANSION.md. Historical 1.1 UI evidence remains in the preserved baseline.


<a id="buildlog"></a>

## build-ghost-note-1.2.0.txt

```text

-- Configuring done (0.5s)
-- Generating done (0.1s)
-- Build files have been written to: <workspace>/work/gatekeep-expansion/build-vst3/JUCE/tools
-- Configuring juceaide
-- Building juceaide
-- Exporting juceaide
-- Testing juceaide
-- Finished setting up juceaide
-- Configuring done (1.9s)
-- Generating done (0.3s)
-- Build files have been written to: <workspace>/work/gatekeep-expansion/build-vst3
-- The CXX compiler identification is MSVC 19.44.35229.0
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: <workspace>/work/toolchain-fast/msvc/VC/Tools/MSVC/14.44.35207/bin/Hostx64/x64/cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (1.1s)
-- Generating done (0.1s)
-- Build files have been written to: <workspace>/work/gatekeep-expansion/build-vst3/vst3_helpers/MidiComposer
[0/2] Re-checking globbed directories...
[1/104] Generating processor_tests_artefacts/JuceLibraryCode/processor_tests_resources.rc
[2/104] Generating juce_binarydata_mc_assets/JuceLibraryCode/BinaryData1.cpp, juce_binarydata_mc_assets/JuceLibraryCode/BinaryData2.cpp, juce_binarydata_mc_assets/JuceLibraryCode/BinaryData3.cpp, juce_binarydata_mc_assets/JuceLibraryCode/BinaryData.h
[3/104] Generating ui_tests_artefacts/JuceLibraryCode/ui_tests_resources.rc
[4/104] Building CXX object CMakeFiles\mc_engine.dir\src\ScaleAdvisor.cpp.obj
[5/104] Building CXX object CMakeFiles\mc_assets.dir\juce_binarydata_mc_assets\JuceLibraryCode\BinaryData3.cpp.obj
[6/104] Building RC object CMakeFiles\processor_tests_rc_lib.dir\processor_tests_artefacts\JuceLibraryCode\processor_tests_resources.rc.res
[7/104] Building CXX object CMakeFiles\mc_assets.dir\juce_binarydata_mc_assets\JuceLibraryCode\BinaryData2.cpp.obj
[8/104] Building CXX object CMakeFiles\mc_engine.dir\src\Engine.cpp.obj
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(467): warning C4456: declaration of 'ebk' hides previous local declaration
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(429): note: see declaration of 'ebk'
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(467): warning C4456: declaration of 'classic' hides previous local declaration
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(429): note: see declaration of 'classic'
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(760): warning C4456: declaration of 'shape' hides previous local declaration
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(721): note: see declaration of 'shape'
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(1519): warning C4530: C++ exception handler used, but unwind semantics are not enabled. Specify /EHsc
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(1551): warning C4456: declaration of 'next' hides previous local declaration
<workspace>\work\gatekeep-expansion\product\src\Engine.cpp(1521): note: see declaration of 'next'
[9/104] Building RC object CMakeFiles\ui_tests_rc_lib.dir\ui_tests_artefacts\JuceLibraryCode\ui_tests_resources.rc.res
[10/104] Generating MidiComposer_artefacts/JuceLibraryCode/MidiComposer_resources.rc
[11/104] Linking CXX static library mc_engine.lib
[12/104] Building CXX object CMakeFiles\mc_assets.dir\juce_binarydata_mc_assets\JuceLibraryCode\BinaryData1.cpp.obj
[13/104] Linking CXX static library mc_assets.lib
[14/104] Generating MidiComposer_artefacts/JuceLibraryCode/JuceHeader.h
[15/104] Building CXX object CMakeFiles\scale_advisor_tests.dir\tests\ScaleAdvisorTests.cpp.obj
<workspace>\work\gatekeep-expansion\product\tests\ScaleAdvisorTests.cpp(96): warning C4530: C++ exception handler used, but unwind semantics are not enabled. Specify /EHsc
[16/104] Building CXX object CMakeFiles\engine_tests.dir\tests\EngineTests.cpp.obj
<workspace>\work\gatekeep-expansion\product\tests\EngineTests.cpp(211): warning C4530: C++ exception handler used, but unwind semantics are not enabled. Specify /EHsc
[17/104] Building VST3 manifest helper for MidiComposer
-- Configuring done (0.1s)
-- Generating done (0.1s)
-- Build files have been written to: <workspace>/work/gatekeep-expansion/build-vst3/vst3_helpers/MidiComposer
[1/2] Building CXX object CMakeFiles\vst3_helper.dir\9be41c4d3ba722d7131705369c17ef5b\VST3\juce_VST3ManifestHelper.cpp.obj
[2/2] Linking CXX executable vst3_helper.exe
[18/104] Building CXX object CMakeFiles\MidiComposer.dir\src\PluginProcessor.cpp.obj
[19/104] Building CXX object CMakeFiles\MidiComposer.dir\src\PluginEditor.cpp.obj
[20/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_processors\juce_audio_processors.cpp.obj
[21/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_extra\juce_gui_extra.cpp.obj
[22/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_2.cpp.obj
[23/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_3.cpp.obj
[24/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics.cpp.obj
<workspace>\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics.cpp(61) : Warning: This version of JUCE does not use the splash screen, the flag JUCE_DISPLAY_SPLASH_SCREEN is ignored
[25/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_5.cpp.obj
[26/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_4.cpp.obj
[27/104] Building C object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics_Sheenbidi.c.obj
[28/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_events\juce_events.cpp.obj
[29/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_core\juce_core_CompilationTime.cpp.obj
[30/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_data_structures\juce_data_structures.cpp.obj
[31/104] Building CXX object CMakeFiles\MidiComposer.dir\627702ab34d62840ab0c80fc601fd439\files-pasted-by-the-user-act\work\vendor\JUCE\modules\juce_core\juce_core.cpp.obj
[32/104] Building CXX object CMakeFiles\MidiComposer.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_processors_headless\juce_audio_processors_headless_ara.cpp.obj
[33/104] Building CXX object CMakeFiles\MidiComposer.dir\16fe5c02f104424975af101b1049e058\juce_audio_processors_headless\juce_audio_processors_headless_lv2_libs.cpp.obj
[34/104] Building CXX object CMakeFiles\MidiComposer.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_processors_headless\juce_audio_processors_headless.cpp.obj
[35/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_basics\juce_audio_basics.cpp.obj
[36/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics.cpp.obj
[37/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_utils\juce_audio_utils.cpp.obj
[38/104] Building CXX object CMakeFiles\reference_prior_tests.dir\tests\ReferencePriorTests.cpp.obj
<workspace>\work\gatekeep-expansion\product\tests\ReferencePriorTests.cpp(89): warning C4530: C++ exception handler used, but unwind semantics are not enabled. Specify /EHsc
[39/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\3cc866959cbfc7fb9ab33877136ebeab\JUCE\modules\juce_audio_plugin_client\juce_audio_plugin_client_AAX.cpp.obj
[40/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_plugin_client\juce_audio_plugin_client_AAX_utils.cpp.obj
[41/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\3cc866959cbfc7fb9ab33877136ebeab\JUCE\modules\juce_audio_plugin_client\juce_audio_plugin_client_ARA.cpp.obj
[42/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\3cc866959cbfc7fb9ab33877136ebeab\JUCE\modules\juce_audio_plugin_client\juce_audio_plugin_client_LV2.cpp.obj
[43/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_plugin_client\juce_audio_plugin_client_Standalone.cpp.obj
[44/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\3cc866959cbfc7fb9ab33877136ebeab\JUCE\modules\juce_audio_plugin_client\juce_audio_plugin_client_Unity.cpp.obj
[45/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\3cc866959cbfc7fb9ab33877136ebeab\JUCE\modules\juce_audio_plugin_client\juce_audio_plugin_client_VST2.cpp.obj
[46/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_formats\juce_audio_formats.cpp.obj
[47/104] Building RC object CMakeFiles\MidiComposer_rc_lib.dir\MidiComposer_artefacts\JuceLibraryCode\MidiComposer_resources.rc.res
[48/104] Linking CXX executable engine_tests.exe
[49/104] Linking CXX executable scale_advisor_tests.exe
[50/104] Linking CXX executable reference_prior_tests.exe
[51/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics_Harfbuzz.cpp.obj
[52/104] Building CXX object CMakeFiles\MidiComposer.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_devices\juce_audio_devices.cpp.obj
[53/104] Linking CXX static library "MidiComposer_artefacts\Release\Ghost Note_SharedCode.lib"
[54/104] Generating processor_tests_artefacts/JuceLibraryCode/JuceHeader.h
[55/104] Generating ui_tests_artefacts/JuceLibraryCode/JuceHeader.h
[56/104] Building CXX object CMakeFiles\MidiComposer_VST3.dir\3cc866959cbfc7fb9ab33877136ebeab\JUCE\modules\juce_audio_plugin_client\juce_audio_plugin_client_VST3.cpp.obj
[57/104] Building CXX object CMakeFiles\processor_tests.dir\tests\ProcessorTests.cpp.obj
<workspace>\work\gatekeep-expansion\product\tests\ProcessorTests.cpp(105): warning C4996: 'juce::AudioFormat::createWriterFor': Use the function taking an AudioFormatWriterOptions instead.
[58/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_processors\juce_audio_processors.cpp.obj
[59/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_utils\juce_audio_utils.cpp.obj
[60/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_2.cpp.obj
[61/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_extra\juce_gui_extra.cpp.obj
[62/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_3.cpp.obj
[63/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics.cpp.obj
<workspace>\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics.cpp(61) : Warning: This version of JUCE does not use the splash screen, the flag JUCE_DISPLAY_SPLASH_SCREEN is ignored
[64/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_4.cpp.obj
[65/104] Building C object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics_Sheenbidi.c.obj
[66/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_5.cpp.obj
[67/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_events\juce_events.cpp.obj
[68/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_core\juce_core_CompilationTime.cpp.obj
[69/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_data_structures\juce_data_structures.cpp.obj
[70/104] Building CXX object CMakeFiles\processor_tests.dir\627702ab34d62840ab0c80fc601fd439\files-pasted-by-the-user-act\work\vendor\JUCE\modules\juce_core\juce_core.cpp.obj
[71/104] Building CXX object CMakeFiles\processor_tests.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_processors_headless\juce_audio_processors_headless_ara.cpp.obj
[72/104] Building CXX object CMakeFiles\processor_tests.dir\16fe5c02f104424975af101b1049e058\juce_audio_processors_headless\juce_audio_processors_headless_lv2_libs.cpp.obj
[73/104] Building CXX object CMakeFiles\processor_tests.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_processors_headless\juce_audio_processors_headless.cpp.obj
[74/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_basics\juce_audio_basics.cpp.obj
[75/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_formats\juce_audio_formats.cpp.obj
[76/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics.cpp.obj
[77/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_devices\juce_audio_devices.cpp.obj
[78/104] Building CXX object CMakeFiles\ui_tests.dir\tests\UiTests.cpp.obj
[79/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_utils\juce_audio_utils.cpp.obj
[80/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_processors\juce_audio_processors.cpp.obj
[81/104] Building CXX object CMakeFiles\processor_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics_Harfbuzz.cpp.obj
[82/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_extra\juce_gui_extra.cpp.obj
[83/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_2.cpp.obj
[84/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_4.cpp.obj
[85/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics.cpp.obj
<workspace>\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics.cpp(61) : Warning: This version of JUCE does not use the splash screen, the flag JUCE_DISPLAY_SPLASH_SCREEN is ignored
[86/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_5.cpp.obj
[87/104] Building C object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics_Sheenbidi.c.obj
[88/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_gui_basics\juce_gui_basics_3.cpp.obj
[89/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_events\juce_events.cpp.obj
[90/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_core\juce_core_CompilationTime.cpp.obj
[91/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_data_structures\juce_data_structures.cpp.obj
[92/104] Building CXX object CMakeFiles\ui_tests.dir\627702ab34d62840ab0c80fc601fd439\files-pasted-by-the-user-act\work\vendor\JUCE\modules\juce_core\juce_core.cpp.obj
[93/104] Building CXX object CMakeFiles\ui_tests.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_processors_headless\juce_audio_processors_headless_ara.cpp.obj
[94/104] Building CXX object CMakeFiles\ui_tests.dir\16fe5c02f104424975af101b1049e058\juce_audio_processors_headless\juce_audio_processors_headless_lv2_libs.cpp.obj
[95/104] Building CXX object CMakeFiles\ui_tests.dir\51e77774aa7483f378dd60d02e818813\modules\juce_audio_processors_headless\juce_audio_processors_headless.cpp.obj
[96/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_basics\juce_audio_basics.cpp.obj
[97/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_formats\juce_audio_formats.cpp.obj
[98/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics.cpp.obj
[99/104] Linking CXX executable processor_tests_artefacts\Release\processor_tests.exe
[100/104] Linking CXX shared module "MidiComposer_artefacts\Release\VST3\Ghost Note.vst3\Contents\x86_64-win\Ghost Note.vst3"
removing moduleinfo.json
creating <workspace>/work/gatekeep-expansion/build-vst3/MidiComposer_artefacts/Release/VST3/Ghost Note.vst3/Contents/Resources/moduleinfo.json
[101/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_audio_devices\juce_audio_devices.cpp.obj
[102/104] Building CXX object CMakeFiles\ui_tests.dir\5fec7d9f6c041003f13b756c546929ce\work\vendor\JUCE\modules\juce_graphics\juce_graphics_Harfbuzz.cpp.obj
[103/104] Linking CXX executable ui_tests_artefacts\Release\ui_tests.exe
[0/2] Re-checking globbed directories...
[0/2] Running tests...
Test project <workspace>/work/gatekeep-expansion/build-vst3
    Start 1: engine_acceptance
1/5 Test #1: engine_acceptance ................   Passed   12.30 sec
    Start 2: scale_advisor_acceptance
2/5 Test #2: scale_advisor_acceptance .........   Passed    0.71 sec
    Start 3: reference_prior_acceptance
3/5 Test #3: reference_prior_acceptance .......   Passed    4.55 sec
    Start 4: processor_acceptance
4/5 Test #4: processor_acceptance .............   Passed    2.92 sec
    Start 5: ui_acceptance
5/5 Test #5: ui_acceptance ....................   Passed    7.85 sec

100% tests passed out of 5

Total Test time (real) =  30.07 sec
Build and acceptance tests completed: <workspace>\work\gatekeep-expansion\build-vst3


```

<a id="ctestlog"></a>

## ctest-ghost-note-1.2.0.txt

```text

Start testing: Nov 18 13:14 Pacific Standard Time
----------------------------------------------------------
1/5 Testing: engine_acceptance
1/5 Test: engine_acceptance
Command: "<workspace>/work/gatekeep-expansion/build-vst3/engine_tests.exe"
Directory: <workspace>/work/gatekeep-expansion/build-vst3
"engine_acceptance" start time: Nov 18 13:14 Pacific Standard Time
Output:
----------------------------------------------------------
Scoped first-cell ii->v counts /128: Afrobeats=0 Pop=6 Dark Latin Guitar=8 R&B=13 Lo-fi=9 Disco=10.
Blues D-major Strict On opening bass: 38 45 47 45.
Blues C-major Strict Off actual harmony: C7 G7 F7 F7 C7 G7 C7 G7.
Learned chord-spacing contrast: 40/384 arrangements selected a different compatible voicing; roots and progression stayed unchanged.
West Coast grammar EBK - Dark NorCal Piano: 63 degree sequences, 5 harmonic rhythms, 952 melodies / 1000 fixed-key seeds.
West Coast grammar LA - Modern West Coast: 63 degree sequences, 5 harmonic rhythms, 1000 melodies / 1000 fixed-key seeds.
West Coast grammar Classic G-Funk: 130 degree sequences, 2 harmonic rhythms, 930 melodies / 1000 fixed-key seeds.
West Coast control contrasts /48: darkness harmony 10, register 40, tension 48.
PASS: 4515350 music-engine and MIDI assertions.
<end of output>
Test time =  12.30 sec
----------------------------------------------------------
Test Passed.
"engine_acceptance" end time: Nov 18 13:14 Pacific Standard Time
"engine_acceptance" time elapsed: 00:00:12
----------------------------------------------------------

2/5 Testing: scale_advisor_acceptance
2/5 Test: scale_advisor_acceptance
Command: "<workspace>/work/gatekeep-expansion/build-vst3/scale_advisor_tests.exe"
Directory: <workspace>/work/gatekeep-expansion/build-vst3
"scale_advisor_acceptance" start time: Nov 18 13:14 Pacific Standard Time
Output:
----------------------------------------------------------
Advice matrix: 1026 pairs; 752 unrated, 73 experimental, 4 bounded local MIDI; all 12 roots invariant.
PASS: 198071 scale-advisor and actual-generation assertions.
<end of output>
Test time =   0.71 sec
----------------------------------------------------------
Test Passed.
"scale_advisor_acceptance" end time: Nov 18 13:14 Pacific Standard Time
"scale_advisor_acceptance" time elapsed: 00:00:00
----------------------------------------------------------

3/5 Testing: reference_prior_acceptance
3/5 Test: reference_prior_acceptance
Command: "<workspace>/work/gatekeep-expansion/build-vst3/reference_prior_tests.exe"
Directory: <workspace>/work/gatekeep-expansion/build-vst3
"reference_prior_acceptance" start time: Nov 18 13:14 Pacific Standard Time
Output:
----------------------------------------------------------
Synthetic contrasts /384: durations 384, onsets 36, intervals 238, voicings 14. These prove implementation, not genre authenticity.
Reference prior checks passed: 1242390
<end of output>
Test time =   4.55 sec
----------------------------------------------------------
Test Passed.
"reference_prior_acceptance" end time: Nov 18 13:14 Pacific Standard Time
"reference_prior_acceptance" time elapsed: 00:00:04
----------------------------------------------------------

4/5 Testing: processor_acceptance
4/5 Test: processor_acceptance
Command: "<workspace>/work/gatekeep-expansion/build-vst3/processor_tests_artefacts/Release/processor_tests.exe"
Directory: <workspace>/work/gatekeep-expansion/build-vst3
"processor_acceptance" start time: Nov 18 13:14 Pacific Standard Time
Output:
----------------------------------------------------------
PASS: 5909 processor integration assertions.
<end of output>
Test time =   2.92 sec
----------------------------------------------------------
Test Passed.
"processor_acceptance" end time: Nov 18 13:14 Pacific Standard Time
"processor_acceptance" time elapsed: 00:00:02
----------------------------------------------------------

5/5 Testing: ui_acceptance
5/5 Test: ui_acceptance
Command: "<workspace>/work/gatekeep-expansion/build-vst3/ui_tests_artefacts/Release/ui_tests.exe"
Directory: <workspace>/work/gatekeep-expansion/build-vst3
"ui_acceptance" start time: Nov 18 13:14 Pacific Standard Time
Output:
----------------------------------------------------------
Legacy scale presets: all 38 IDs; exact pitches/velocities/part settings; maximum JSON timing drift 8.88178e-16 host beats.
PASS: 9154 UI label/layout assertions. Actual offscreen renders: <workspace>\work\gatekeep-expansion\build-vst3\ui-review
<end of output>
Test time =   7.85 sec
----------------------------------------------------------
Test Passed.
"ui_acceptance" end time: Nov 18 13:14 Pacific Standard Time
"ui_acceptance" time elapsed: 00:00:07
----------------------------------------------------------

End testing: Nov 18 13:14 Pacific Standard Time


```

<a id="pluginvallog"></a>

## pluginval-ghost-note-1.2.0.txt

```text

Started validating: <workspace>\work\gatekeep-expansion\build-vst3\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3
Random seed: 0x2bf22
Validation started
Strictness level: 5
-----------------------------------------------------------------
Starting tests in: pluginval / Scan for plugins located in: <workspace>\work\gatekeep-expansion\build-vst3\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3...
Num plugins found: 1

Testing plugin: VST3-Ghost Note-1d966048-fad46c05
TwonOnDaBeat: Ghost Note v1.2.0
Completed tests in pluginval / Scan for plugins located in: <workspace>\work\gatekeep-expansion\build-vst3\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3
-----------------------------------------------------------------
Starting tests in: pluginval / Open plugin (cold)...
Completed tests in pluginval / Open plugin (cold)
-----------------------------------------------------------------
Starting tests in: pluginval / Open plugin (warm)...
Running tests 1 times
Completed tests in pluginval / Open plugin (warm)
-----------------------------------------------------------------
Starting tests in: pluginval / Plugin info...

Plugin name: Ghost Note
Alternative names: Ghost Note
SupportsDoublePrecision: no
Reported latency: 0
Reported taillength: 2
Completed tests in pluginval / Plugin info
-----------------------------------------------------------------
Starting tests in: pluginval / Plugin programs...
Num programs: 0
All program names checked
Completed tests in pluginval / Plugin programs
-----------------------------------------------------------------
Starting tests in: pluginval / Editor...
Completed tests in pluginval / Editor
-----------------------------------------------------------------
Starting tests in: pluginval / Open editor whilst processing...
Completed tests in pluginval / Open editor whilst processing
-----------------------------------------------------------------
Starting tests in: pluginval / Audio processing...
Testing with sample rate [44100] and block size [64]
Testing with sample rate [44100] and block size [128]
Testing with sample rate [44100] and block size [256]
Testing with sample rate [44100] and block size [512]
Testing with sample rate [44100] and block size [1024]
Testing with sample rate [48000] and block size [64]
Testing with sample rate [48000] and block size [128]
Testing with sample rate [48000] and block size [256]
Testing with sample rate [48000] and block size [512]
Testing with sample rate [48000] and block size [1024]
Testing with sample rate [96000] and block size [64]
Testing with sample rate [96000] and block size [128]
Testing with sample rate [96000] and block size [256]
Testing with sample rate [96000] and block size [512]
Testing with sample rate [96000] and block size [1024]
Completed tests in pluginval / Audio processing
-----------------------------------------------------------------
Starting tests in: pluginval / Plugin state...
Completed tests in pluginval / Plugin state
-----------------------------------------------------------------
Starting tests in: pluginval / Automation...
Testing with sample rate [44100] and block size [64] and sub-block size [32]
Testing with sample rate [44100] and block size [128] and sub-block size [32]
Testing with sample rate [44100] and block size [256] and sub-block size [32]
Testing with sample rate [44100] and block size [512] and sub-block size [32]
Testing with sample rate [44100] and block size [1024] and sub-block size [32]
Testing with sample rate [48000] and block size [64] and sub-block size [32]
Testing with sample rate [48000] and block size [128] and sub-block size [32]
Testing with sample rate [48000] and block size [256] and sub-block size [32]
Testing with sample rate [48000] and block size [512] and sub-block size [32]
Testing with sample rate [48000] and block size [1024] and sub-block size [32]
Testing with sample rate [96000] and block size [64] and sub-block size [32]
Testing with sample rate [96000] and block size [128] and sub-block size [32]
Testing with sample rate [96000] and block size [256] and sub-block size [32]
Testing with sample rate [96000] and block size [512] and sub-block size [32]
Testing with sample rate [96000] and block size [1024] and sub-block size [32]
Completed tests in pluginval / Automation
-----------------------------------------------------------------
Starting tests in: pluginval / Editor Automation...
Completed tests in pluginval / Editor Automation
-----------------------------------------------------------------
Starting tests in: pluginval / Automatable Parameters...
Completed tests in pluginval / Automatable Parameters
-----------------------------------------------------------------
Starting tests in: pluginval / auval...
Completed tests in pluginval / auval
-----------------------------------------------------------------
Starting tests in: pluginval / vst3 validator...
INFO: Skipping vst3 validator as validator path hasn't been set
Completed tests in pluginval / vst3 validator
-----------------------------------------------------------------
Starting tests in: pluginval / Basic bus...
Completed tests in pluginval / Basic bus
-----------------------------------------------------------------
Starting tests in: pluginval / Listing available buses...
Inputs:
	Named layouts: None
	Discrete layouts: None
Outputs:
	Named layouts: Stereo
	Discrete layouts: None
Main bus num input channels: 0
Main bus num output channels: 2
Completed tests in pluginval / Listing available buses
-----------------------------------------------------------------
Starting tests in: pluginval / Enabling all buses...
Completed tests in pluginval / Enabling all buses
-----------------------------------------------------------------
Starting tests in: pluginval / Disabling non-main busses...
Completed tests in pluginval / Disabling non-main busses
-----------------------------------------------------------------
Starting tests in: pluginval / Restoring default layout...
Main bus num input channels: 0
Main bus num output channels: 2
Completed tests in pluginval / Restoring default layout
SUCCESS


```
