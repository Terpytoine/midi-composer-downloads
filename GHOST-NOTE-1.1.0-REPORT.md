# Ghost Note 1.1.0 — public implementation and evidence report

Windows x64 VST3 by **TwonOnDaBeat**. The [1.1.0 owner-validation prerelease](https://github.com/Terpytoine/midi-composer-downloads/releases/tag/v1.1.0) is published with the installer, complete VST3 ZIP, installer-validation JSON and payload-manifest JSON. The installer is unsigned and installs the VST3 instrument. The official plugin source remains private.

**Completed technical checks:** Release build; CTest 4/4 in 14.73 seconds; 4,515,350 engine, 198,071 adviser, 5,690 processor and 9,154 UI assertions; actual editor-render review; pluginval 1.0.4 strictness 5, exit 0; independent installer extraction and all 18 payload length/hash checks plus its embedded manifest.

**Owner acceptance still pending:** installation and updated 1.1.0 DAW behavior, routing/Stop/Mute, drag/export, saved-project recall and human listening across all 27 models. The assistant could not hear the rendered examples. Valid/unique MIDI, technical PCM checks, theory-led scale advice and automated assertions do not establish artistic quality or complete genre authenticity. Historical 1.0.0 FL verified scan/load is a separate result.

This file combines the full reviewed public project documents and all six sanitized versioned build/test/pluginval logs. Section content retains its source-freeze provenance, historical versions and scoped limitations; links to project documents lead to sections below. Source-freeze tables that mark publication or backup pending describe that earlier snapshot, not a claim that this now-published release is unavailable. Remote private-backup verification is a separate delivery record. Unchanged third-party license texts remain linked in the public repository instead of being duplicated here.

## Published artifact identities

Compare SHA-256 with the exact file you download. GitHub's automatic source archives contain the public downloads/documentation repository; they do not contain the private plugin source.

| Published asset | SHA-256 |
|---|---|
| [Ghost-Note-VST3-Setup-1.1.0-Windows.exe](https://github.com/Terpytoine/midi-composer-downloads/releases/download/v1.1.0/Ghost-Note-VST3-Setup-1.1.0-Windows.exe) | `e678e914052a9bdd6680949849a27432d521841bdc9d76620311ccdc2ecd2cc9` |
| [Ghost-Note-VST3-1.1.0-Windows-x64.zip](https://github.com/Terpytoine/midi-composer-downloads/releases/download/v1.1.0/Ghost-Note-VST3-1.1.0-Windows-x64.zip) | `29476b494702f3fd9fb87b9fd80319d162c37b46e7d3edc20c8598d0ce89c219` |
| [Ghost-Note-VST3-Setup-1.1.0-Windows-Validation.json](https://github.com/Terpytoine/midi-composer-downloads/releases/download/v1.1.0/Ghost-Note-VST3-Setup-1.1.0-Windows-Validation.json) | `322509954e509340f606ebede851978ce60cb441a6220e3760856e68a8672d81` |
| [Ghost-Note-Installer-Payload-Manifest-1.1.0.json](https://github.com/Terpytoine/midi-composer-downloads/releases/download/v1.1.0/Ghost-Note-Installer-Payload-Manifest-1.1.0.json) | `e37e38d98306fdacb1fcf0e930dab1d09c51b68ccc293bde9c27c4f1eb250064` |

## Contents

- [RELEASE-NOTES.md](#document-release-notes-md)
- [INSTALLER.md](#document-installer-md)
- [SCALE-RECOMMENDATIONS.md](#document-scale-recommendations-md)
- [Scale-Advice-Evidence.md](#document-scale-advice-evidence-md)
- [TESTING.md](#document-testing-md)
- [BUILD_VALIDATION.md](#document-build-validation-md)
- [UI_VALIDATION.md](#document-ui-validation-md)
- [INSTALLER_VALIDATION.md](#document-installer-validation-md)
- [LIBRARY-METHOD.md](#document-library-method-md)
- [THIRD_PARTY.md](#document-third-party-md)
- [GENRE-AUDIT.md](#document-genre-audit-md)
- [GENRE-CORRECTIONS-1.0.1.md](#document-genre-corrections-1-0-1-md)
- [GENRE-REFINED-MIDI-AUDIT-1.0.1.md](#document-genre-refined-midi-audit-1-0-1-md)
- [GENRE-BEFORE-AFTER-COMPARISON-1.0.1.md](#document-genre-before-after-comparison-1-0-1-md)
- [GENRE-INSTALLED-COMPARISON-1.0.1.md](#document-genre-installed-comparison-1-0-1-md)
- [GENRE-CADENCE-COMPARISON-1.0.1.md](#document-genre-cadence-comparison-1-0-1-md)
- [GENRE-BLUES-CONTEXT-1.0.1.md](#document-genre-blues-context-1-0-1-md)
- [GENRE-LISTENING-STATUS.md](#document-genre-listening-status-md)
- [WEST-COAST-REFERENCES.md](#document-west-coast-references-md)
- [ARTWORK.md](#document-artwork-md)
- [GENRE-ARCHITECTURE-AUDIT.md](#document-genre-architecture-audit-md)
- [GENRE-BASELINE-MIDI-AUDIT.md](#document-genre-baseline-midi-audit-md)
- [GENRE-BEFORE-AFTER-COMPARISON.md](#document-genre-before-after-comparison-md)
- [GENRE-BEFORE-MODEL-REVIEW.md](#document-genre-before-model-review-md)
- [GENRE-GENERATED-PROGRESSION-EXAMPLES.md](#document-genre-generated-progression-examples-md)
- [GENRE-OWNED-MIDI-SAMPLE.md](#document-genre-owned-midi-sample-md)
- [GENRE-RESEARCH-ACOUSTIC.md](#document-genre-research-acoustic-md)
- [GENRE-RESEARCH-ELECTRONIC.md](#document-genre-research-electronic-md)
- [GENRE-RESEARCH-HIPHOP-POP.md](#document-genre-research-hiphop-pop-md)
- [GHOST-NOTE-ARTWORK.md](#document-ghost-note-artwork-md)
- [WEST-COAST-REFERENCE-COMPARISON.md](#document-west-coast-reference-comparison-md)
- [validation/build-ghost-note-1.0.0.txt](#document-validation-build-ghost-note-1-0-0-txt)
- [validation/build-ghost-note-1.1.0.txt](#document-validation-build-ghost-note-1-1-0-txt)
- [validation/ctest-ghost-note-1.0.0.txt](#document-validation-ctest-ghost-note-1-0-0-txt)
- [validation/ctest-ghost-note-1.1.0.txt](#document-validation-ctest-ghost-note-1-1-0-txt)
- [validation/pluginval-ghost-note-1.0.0.txt](#document-validation-pluginval-ghost-note-1-0-0-txt)
- [validation/pluginval-ghost-note-1.1.0.txt](#document-validation-pluginval-ghost-note-1-1-0-txt)

<a id="document-release-notes-md"></a>

## RELEASE-NOTES.md

### Ghost Note 1.1.0 — owner-validation update

Windows x64 VST3 by **TwonOnDaBeat**. The product/bundle remains **Ghost Note / Ghost Note.vst3**, with version 1.1.0 and stable IDs. This is an owner-validation prerelease until the owner completes updated DAW acceptance. No all-genre listening or full production certificate is claimed.

<!-- RELEASE_PENDING_VALIDATION: ghost-note-1.1 -->

#### New scale guidance

Genre-aware scale advice adds green Highly Recommended, yellow Compatible, red Experimental and neutral Unrated choices with text/explanations. All 12 roots and 38 formulas remain available. Advice is interval-based and does not prefer one transposed root over another. Unsupported formulas are not automatically rated red. Recommendations are provisional and evidence-scoped.

Manual scales and existing MIDI remain authoritative. Recommendation refresh does not Print; Suggest Scale is explicit and selects a setting for subsequent generation. Strict Scale and genre-specific note rules still apply on the next Print. Pure-adviser tests passed 198,071 assertions. Exact current UI/build results are in TESTING.md and UI_VALIDATION.md; no older UI log is relabeled.

#### Cadence and Blues corrections

The retained aeae3c62 engine gives Afrobeats, Pop, R&B, Lo-fi, Disco and Dark Latin Guitar their scoped cadence policies instead of one shared forced ending. Blues retains its scale-valid walking sixth and has an explicit dominant-seventh I/IV/V eight-bar branch with Strict Scale off. Strict Scale on continues to honor the exact selected collection. The eight-bar interpretation is not twelve-bar form.

The corrected source passed 4,515,350 isolated engine assertions, a 1,080-file actual MIDI audit, 11 analyzer tests, 60 extra Blues fixtures and 27 authored contexts. Versioned musical report filenames retain 1.0.1 because the later adviser does not alter this composition engine.

The private listening pack has 88 WAVs including 27 new contexts. Technical PCM checks passed, and old material remains preserved. The assistant could not hear it; human judgments are pending for all 27 models. Synthesized timbres and note-only exports do not supply full production context, instrument performance or 808 glide.

#### Compatibility and delivery

One sheet, five optional layers, Undo/Redo, Stop/Mute ownership, host feel, Type-0 channel-1 export, all styles/scales and saved-state IDs remain. Fresh FL Studio 2026 scan/load passed for installed 1.0.0 on 17 November; updated 1.1.0 Stop/Mute, routing, transfer, recall and historical-project compatibility belong to the owner's test.

The final 1.1.0 Release build passed CTest 4/4 in 14.73 seconds: 4,515,350 engine, 198,071 adviser, 5,690 processor and 9,154 UI assertions. Actual editor/dark/light menu renders were visually reviewed. Pluginval 1.0.4 strictness 5 passed, exit 0, with editor enabled. Current exact checksums and installer integrity: see BUILD_VALIDATION.md and INSTALLER_VALIDATION.md. Local preparation does not prove publication or a refreshed remote backup. The unsigned installer passed independent CRC/extraction and all 18 payload length/hash checks plus embedded-manifest verification. It installs only the VST3; the actual 1.1.0 installation and DAW review remain for the owner. Source, private references and licensed assets remain private. Existing backups and versions remain preserved; no cleanup deletion occurs without itemized explicit owner approval.

<a id="document-installer-md"></a>

## INSTALLER.md

### Install Ghost Note

Run **Ghost-Note-VST3-Setup-1.1.0-Windows.exe** to install the Windows x64 VST3. The instrument runs inside FL Studio or another VST3 host; the EXE is its installer.

1. Close hosts using an existing Ghost Note instance before installing or updating it.
2. Open the EXE, approve the normal Windows administrator prompt and follow the wizard.
3. In FL Studio, choose **Options → Manage plugins → Find installed plugins**.
4. Look for **Ghost Note**, manufacturer **TwonOnDaBeat**, and load it as an instrument.

The complete plugin is installed at:

`C:\Program Files\Common Files\VST3\Ghost Note.vst3`

The installer leaves FL Studio's saved settings unchanged. A rescan may be needed. See Image-Line's [plugin installation guide](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/basics_externalplugins.htm).

Choose Genre, Key, Scale, Tempo and Complexity, then press **Print**. The complete composition appears directly in **one piano roll** and exports as **one MIDI track**. Undo/Redo recovers previous prints and edits. Advanced optionally selects one of five coordinated layers for editing, regeneration, audition or export. Faint other-layer notes are visual references. There is no A/B Keep/Discard process. Your receiving FL Studio instrument supplies exported MIDI's sound.

Stop overrides a running host until Play. Mute MIDI + audio releases Ghost Note's owned notes and suppresses new output until disabled; Preview Sound is a separate audio-only setting. Successful MIDI export or drag-file preparation stops source playback. Independent MIDI clips in receiving instruments remain controlled by FL Studio and those instruments.

Host sync follows FL Studio's tempo. At 180 BPM, **½×** provides a 90 BPM feel while the default sheet still fills eight host bars / 32 beats / approximately 10.67 seconds. **1×** uses faster phrasing in the same host duration. Auto suggests a feel and manual choices override it. Editing snap separately defaults to **½ beat**.

Documentation and the uninstaller are installed in:

`C:\Program Files\Ghost Note`

To remove the plugin, close hosts using it and choose **Ghost Note VST3** in Windows **Settings → Apps → Installed apps → Uninstall**. The uninstaller removes only manifest-listed product files and empty product folders. Other plugins, FL Studio projects and exported MIDI remain outside its removal list.

The plugin operates offline. No standalone music app, source-library MIDI, compiler tools or signing credentials are included. Only bounded aggregate patterns from accepted musical material are embedded. Percussion and uncertain material are excluded from the profile, and source remains private.

This owner-validation 1.1.0 prerelease is **unsigned**. Verify the actual published installer's SHA-256 against its checksum. The owner will run updated DAW acceptance; current installer and installed-byte results are recorded separately in INSTALLER_VALIDATION.md. Installer extraction/payload checks are separate from actual installation and FL Studio host checks; the final verification reports identify which were performed.

The product is Ghost Note 1.1.0, manufacturer TwonOnDaBeat. This prerelease is for owner validation, with human listening and updated DAW acceptance pending. Preserve class ID ABCDEF019182FAEB4D6364764D633031 and verify old-project recall before removing a previous version. Final consolidation follows an inventory and an exact-path/size/reason cleanup proposal approved explicitly by the owner before deletion. The source master, backup, presets, licenses, original references and FL Studio projects remain preserved.

<a id="document-scale-recommendations-md"></a>

## SCALE-RECOMMENDATIONS.md

### Genre-aware scale recommendations

Ghost Note 1.1.0 adds stylistic advice for the existing 27 genre models and 38 formulas. It guides a starting point without restricting creative choices. All 12 roots remain available; transposing the same formula does not change its rating. No register-suitability score is supplied because receiving-instrument/sample-range evidence is unavailable.

#### Reading the advice

| Indicator | Meaning |
|---|---|
| Green — Highly Recommended | A useful starting point within this model's documented interpretation. Theory-led choices remain provisional. |
| Yellow — Compatible | A related alternative with an explanation; not a second-class musical choice. |
| Neutral — Unrated | Insufficient scoped evidence to rank the formula. It remains selectable and is not automatically Experimental. |
| Red — Experimental | An explained departure from the model's intended color/support. It remains valid and selectable. |

Text labels accompany colors. The menu order is authored Recommended choices, Compatible, neutral Unrated, then explicit Experimental choices. The first Recommended entry is a suggested default, not a command to replace the current scale. Root names update the display while interval ratings remain unchanged.

The matrix covers 1,026 genre/scale pairs: 752 are neutral Unrated, 73 are explicitly Experimental, and only four carry the bounded local-MIDI evidence flag. Other rated advice is theory-led/provisional. These numbers describe implementation coverage, not confidence or authenticity percentages. [Scale-Advice-Evidence.md](#document-scale-advice-evidence-md) lists per-genre starting points, reasons and primary-source/evidence limits.

#### Preserve manual choices and current music

Refreshing recommendations on a genre/root change preserves the selected scale and existing notes. Suggest Scale is explicit; it selects a suggested scale for later generation and does not Print or rewrite MIDI. Manual selection remains authoritative. Choosing a scale follows the existing scale-setting path; the next Print uses that exact formula together with the selected genre's harmony, rhythm and role rules.

The final 1.1.0 suite passed **9,154 actual editor action/layout assertions**. Actual default, compact/resized and dark/light menu renders were visually reviewed. This checks the implemented behavior independently of the pure adviser; updated native DAW behavior remains for the owner. See UI_VALIDATION.md.

#### Evidence and pitch-policy limits

The adviser reuses earlier research and the already parsed West Coast sample. It does not claim new source-file parsing or listening. The four bounded local-MIDI pairs are EBK Natural Minor, Modern LA Natural Minor, Classic G-Funk Natural Minor and Classic G-Funk Minor Pentatonic lead vocabulary. G-Funk's suggested default remains Natural Minor, matching the limited actual minor-centered evidence. Its Dorian/Mixolydian alternatives, and EBK Harmonic Minor/Phrygian choices, are theory-led and provisional.

A pentatonic lead palette is not proof that a full arrangement uses pentatonic harmony. Strict Scale applies to chords as well as melodies and can remove seventh/ninth colors. Jazz/Gospel/R&B/G-Funk mixtures and Blues I7/IV7/V7 often exceed a single fixed formula. Advice never disables Strict Scale or silently broadens the collection. The existing Melodic Minor formula is fixed ascending, not a direction-sensitive performed scale.

The pure adviser does not generate notes or accept mutable settings. It adds no musical-engine changes; the composition source remains **aeae3c62**. Its isolated C++ suite passed **198,071 assertions**, including all 27 × 38 lookups, every root's rating invariance, complete ordering/defaults, no mutation, representative formulas and actual Strict Scale generation across every genre/formula. Full plugin/UI and owner DAW checks remain separate in TESTING.md.

<a id="document-scale-advice-evidence-md"></a>

## Scale-Advice-Evidence.md

### Scale advice: evidence and implementation

17 November 2026. This feature provides stylistic starting points for Ghost Note's 27 documented model interpretations. It does not certify authenticity, rank musical correctness or prevent any of the 38 scales from being selected. The attachment's preliminary table was treated as a proposal. No root is preferred over another root, no confidence percentage is invented, and no listening verdict is claimed. The user will conduct the DAW test.

#### What the ratings mean

- **Recommended:** a useful starting point for this model's documented interpretation. A green theory-led recommendation is explicitly **provisional**.
- **Compatible:** a related tonal or melodic alternative, also provisional when based on theory.
- **Experimental:** a deliberate departure from this model's intended tonal support or color, with an explanation. It remains valid and selectable.
- **Unrated:** there is insufficient scoped evidence to rank this formula. This neutral status is separate from Experimental; an unfamiliar scale name is not evidence against it.

Stylistic tier and evidence are separate fields. `BoundedLocalMidi` identifies a specific fact supported by the previously audited owned sample. It does not establish a whole scene's mode frequencies. `PublishedTheory` identifies an authored inference from scale structure, chord/phrase theory and the researched model scope; its genre/scale ranking is provisional. `Provisional` evidence marks an unrated evidence gap. There are no numerical confidence scores or learned genre percentages.

The implemented matrix has **1,026 genre/scale pairs: 752 Unrated, 73 Experimental and four pairs marked BoundedLocalMidi**. The remaining rated pairs are theory-led/provisional. These are implementation coverage counts, not authenticity statistics. All choices remain in the menu. The order is authored Recommended choices, Compatible choices, neutral Unrated choices, then explicit Experimental choices; the first Recommended choice is the displayed suggested default. A user's current selection need not match that default.

#### Existing MIDI evidence reused

The complete [West Coast reference report](#document-west-coast-references-md) was read, including its seven primary supplied examples and thirteen supplemental owned-library examples. This feature reuses that audit; it does not claim to have newly parsed or heard those source files. No source MIDI is copied into the advisor.

Exactly these pairs receive the local-MIDI flag:

| Model / formula | Bounded observation |
|---|---|
| EBK / Natural Minor | The supplied EBK pitch material and observed minor shapes support a natural-minor interpretation. Sparse subsets alone do not uniquely prove a mode. |
| Modern LA / Natural Minor | The supplied LA harmonic material supports minor-centered voicings, shared tones and iv/i-related motion. |
| Classic G-Funk / Natural Minor | The supplied harmonic example is predominantly natural minor with one leading-tone turnaround exception; supplemental harmony, lead and bass examples also favor minor. |
| Classic G-Funk / Minor Pentatonic | A supplemental A-minor G-Funk lead uses the minor-pentatonic pitch classes. This is evidence for that lead vocabulary, not all G-Funk harmony. |

Natural Minor stays the suggested G-Funk default. The advisor does not demote the actual minor-centered evidence behind a major-only stereotype. Green G-Funk Dorian and Mixolydian are **theory-led/provisional** alternatives. EBK Harmonic Minor and Phrygian are also theory-led/provisional; the two supplied EBK files do not demonstrate harmonic-minor accidentals. A broader West Coast Phrygian harmony example does not prove an EBK-wide convention.

The G-Funk Minor Pentatonic recommendation is specifically a **lead palette**, not proof that the full source arrangement uses one minor-pentatonic formula. Strict Scale applies the selected formula to chords as well as lead notes; strict pentatonic choices can remove seventh/ninth colors demonstrated by local G-Funk harmony. The recommendation's reason and evidence note state this, and other pentatonic alternatives in rich-harmony models carry the same chord-color caveat.

#### Theory and scope sources

All three existing research ledgers were read: [hip-hop/pop/guitar](#document-genre-research-hiphop-pop-md), [electronic/Afrobeats/reggaeton](#document-genre-research-electronic-md), and [acoustic/jazz/vintage-related models](#document-genre-research-acoustic-md). Their artist interviews, producer walkthroughs, official lessons and theory texts establish bounded compositional approaches; they do not supply measured mode distributions for all 27 genres. Catalog pages and quarantined Afrobeat material are not treated as Afrobeats MIDI evidence.

Additional primary educational sources opened for this feature:

- [Gary Burton / Berklee: Jazz Scales You Need to Know](https://online.berklee.edu/takenote/jazz-improvisation-10-scales/) explains modal chord colors and chord-scale choices. This supports theory-led modal alternatives, not a universal whole-song jazz scale or new mode-frequency measurement.
- [Yamaha: A Bassist's Guide to Modes, Part 1](https://hub.yamaha.com/guitars/bass/a-bassists-guide-to-modes-part-1/) distinguishes minor modes, Dorian's natural sixth, Lydian's raised fourth and dominant-colored Mixolydian. The advisor uses those interval facts to explain color; no embedded audio was heard.
- [University of Puget Sound: Scales](https://musictheory.pugetsound.edu/mt21c/JazzScales.html) separates blues, bebop and other chord/scale collections. It reinforces the need to distinguish a fixed selected formula from changing chord-specific improvisation choices.
- [Open Music Theory: Blues Harmony](https://viva.pressbooks.pub/openmusictheory/chapter/blues-harmony/) describes stable dominant qualities, mixed thirds and the limits of treating blues as ordinary diatonic harmony. The advisor explicitly explains the selected Strict Scale constraint.

The numerical order below is an authored interpretation of those facts plus the existing model scope. Except for the four bounded pairs above, no local MIDI measurement is claimed. Green recommendations therefore retain their provisional flag even when the interval theory is well established.

#### Per-model starting points

The first entry in each Recommended list is the suggested default. These lists are not mandatory progressions or required keys. The implementation contains additional Compatible/Experimental explanations and preserves every other formula as Unrated.

| Model and intended scope | Recommended, in order | Why these starts |
|---|---|---|
| Melodic Rap | Natural Minor, Harmonic Minor, Minor Pentatonic, Major | A recalled singable tonal hook with supporting harmony. |
| Trap | Natural Minor, Harmonic Minor | Sparse minor ostinatos; raised-seventh tension is an optional theory-led color. |
| R&B | Major, Natural Minor, Dorian | Connected rich voicings with major/minor and natural-sixth alternatives. |
| Drill | Natural Minor, Harmonic Minor, Phrygian | The engine's dark, spacious UK-influenced interpretation; not all drill. |
| Bay Area | Natural Minor, Minor Pentatonic, Dorian, Mixolydian | Compact groove-oriented vamps and riffs; the regional mode ranking is provisional. |
| Dark Latin Guitar | Natural Minor, Harmonic Minor, Phrygian, Phrygian Dominant | A dark nylon hybrid with descending tension, not every Latin or flamenco practice. |
| Pop | Major, Natural Minor, Major Pentatonic, Minor Pentatonic | Clear tonal support and compact hooks. |
| House | Natural Minor, Major, Dorian | Melodic/deep/funky pitched support rather than a rule for all house. |
| Techno | Natural Minor, Dorian | Minor/modal pedals and restrained sequencer cells; whole tone remains Compatible. |
| Drum & Bass | Natural Minor, Major, Dorian | The model's melodic/liquid-leaning support, not an account of all neurofunk. |
| Lo-fi | Major, Dorian, Natural Minor | Patient compatible extensions and understated repeated phrases. |
| Jazz | Major, Dorian, Mixolydian, Natural Minor | Accessible tonal/modal starts; the fixed global formula cannot supply every chord scale. |
| Afrobeats | Major, Major Pentatonic, Minor Pentatonic | Contemporary pop/fusion hooks and interlocking pockets; mode ranking remains provisional. |
| Reggaeton | Natural Minor, Major | Tonal call/response support for the model's dembow-compatible pocket. |
| Rock | Natural Minor, Major, Minor Pentatonic, Mixolydian | Clear tonic/root-fifth riffs and related lead colors. |
| Ambient | Major, Lydian, Dorian | Sustained open/bright/minor colors; no formula alone supplies ambience or texture. |
| Funk | Dorian, Mixolydian, Minor Pentatonic, Natural Minor | Minor/natural-sixth, dominant and economical riff alternatives. |
| Disco | Natural Minor, Major, Dorian, Mixolydian | Soulful tonal support over the model's continuing octave bass. |
| Country | Major, Major Pentatonic, Mixolydian | Clear alternating-bass support and compact upper phrases. |
| Gospel | Major, Natural Minor, Harmonic Minor | Tonal destinations and compatible rich support; many borrowings exceed one formula. |
| Classical | Major, Natural Minor, Harmonic Minor | The engine's tonal Classical-era phrase/cadence interpretation. |
| Blues | Mixolydian, Blues, Minor Pentatonic | Tonic dominant/major-sixth or focused blues lead color; strict harmony remains a reduction. |
| Dubstep | Natural Minor, Phrygian, Minor Pentatonic | Sparse dark bass-led questions/replies in the classic-leaning model. |
| Trance | Natural Minor, Major, Dorian | The model's melodic/uplifting rolling-harmony interpretation. |
| EBK / Dark NorCal | Natural Minor, Harmonic Minor, Phrygian | Observed minor foundation plus explicitly theory-led darker alternatives. |
| Modern LA | Natural Minor, Dorian, Minor Pentatonic | Observed minor center plus provisional natural-sixth/riff alternatives. |
| Classic G-Funk | Natural Minor, Minor Pentatonic, Dorian, Mixolydian | Bounded minor evidence first, followed by groove-color alternatives. |

Experimental ratings are narrowly authored. For example, Lydian's major third and raised fourth deliberately contrast with the dark Trap/Drill/EBK brief. Whole tone changes familiar perfect-fifth tonal support, but it is Compatible for the Ambient and Techno interpretations. Locrian's diminished tonic is unusual for conventional root/fifth support but remains a Compatible half-diminished color in Jazz. Other unusual or culturally named formulas are not all assigned the same negative judgment; unavailable genre evidence remains neutral.

#### Pitch policy and integration contract

`src/ScaleAdvisor.h/.cpp` exposes pure lookups by existing `Style` and scale ID. The root is deliberately absent, so transposition cannot change a tier, order, reason or evidence flag. Root names are a display/transposition matter. No register suitability score is supplied because this feature has no receiving-instrument/sample-range evidence.

The API does not accept mutable settings, generate notes, change MIDI, choose Strict Off, rewrite a scale or replace the selected scale with its suggested default. The UI can refresh guidance when the genre or root changes while preserving a manually selected scale and the current notes. Selecting a scale continues to use the existing scale-setting path and the existing genre engine on later generation. Saved style/scale IDs remain stable; legacy major/minor settings are resolved with `resolvedScale(settings)`.

Strict Scale is authoritative for all 38 actual formulas. Traditional Blues I7/IV7/V7 cannot all fit one ordinary diatonic scale; a green Mixolydian or blues-lead recommendation does not override that. Jazz/Gospel/R&B/G-Funk borrowing and flamenco-like mixtures can likewise exceed one formula. The advisor explains those limits instead of silently changing pitch policy. Melodic Minor is the existing fixed ascending formula, not an automatically changing ascending/descending scale.

The note engine remains frozen at SHA-256 `AEAE3C626813FFE26D4282D1C99D80525AF4A3295C18A016AFE908037AF38613`; this advisor adds no note-grammar changes.

#### Verification

An isolated LLVM MinGW `clang++ -O2 -std=c++17 -Wall -Wextra -Wpedantic` build of `Engine.cpp`, `ScaleAdvisor.cpp` and `ScaleAdvisorTests.cpp` completed without diagnostics. The new suite passed **198,071 assertions**:

- All 27 × 38 lookup pairs, complete unique choice ordering, explicit defaults, nonempty explanations/evidence and all four readable statuses.
- Invariance across all 12 root selections; no advice call mutates root/scale or existing generated notes.
- Explicit local-MIDI/theory/provisional distinctions, G-Funk natural-minor default, EBK theory-led alternatives and neutral unlisted formulas.
- Exact representative major/minor/modal/pentatonic/blues/whole-tone/chromatic formulas.
- Actual Strict Scale generation for every 27 × 38 pair, with all harmony and role pitches checked against the selected formula.
- EBK + Harmonic Minor, Classic G-Funk + Dorian and Afrobeats + Major Pentatonic actually generated in all 12 roots.
- Invalid IDs rejected without silent fallback.

The final 1.1.0 MSVC build additionally passed all four CTest suites in 14.73 seconds: 4,515,350 engine, 198,071 adviser, 5,690 processor and 9,154 UI assertions. Actual editor renders and dark/light menus were visually reviewed; BUILD_VALIDATION.md and UI_VALIDATION.md record that separate scope and the exact binary identity. This adviser suite alone does not test rendering or hear the music. Updated DAW and human listening acceptance remain with the owner.

<a id="document-testing-md"></a>

## TESTING.md

### Ghost Note implementation and testing report

**1.1.0 owner-validation update, Windows x64.** This release adds genre-aware scale advice above the corrected composition engine. The owner will perform the updated build's DAW acceptance. Existing versioned logs remain historical; no earlier pass is relabeled as a new UI-feature pass.

<!-- RELEASE_PENDING_VALIDATION: ghost-note-1.1 -->

#### Current artifact evidence

Snapshot at source/document freeze, before upload and the owner's installation/DAW review. Remote backup/publication outcomes belong to their separately verified delivery records; later completion is not inferred here.

| Check | 1.1.0 result |
|---|---|
| Release build / exact VST3 identity | Release x64 build passed, 18 November 2026; exact VST3 SHA-256 below. |
| Complete CTest / assertion counts | 4/4 passed in 14.73 seconds. 4,515,350 engine; 198,071 ScaleAdvisor; 5,690 processor; 9,154 UI assertions. |
| Pure ScaleAdvisor tests | 198,071 assertions passed, including actual Strict Scale generation for all 27 × 38 pairs. |
| Actual advisory UI renders/actions | 9,154 actual editor action/layout assertions passed; actual offscreen renders visually reviewed (see UI_VALIDATION.md). |
| Independent pluginval | Tracktion pluginval 1.0.4 strictness 5 passed, exit 0, seed 180001; editor enabled. |
| VST3 SHA-256 | 9c3afcac178c5a63f9bf648713b4072d593736e4a69489d3d680d64e3e62aa70 |
| Module and Windows PE name/version/company | Verified Ghost Note / TwonOnDaBeat / 1.1.0 in VST3 module and Windows PE metadata; stable component ID retained. |
| Installer/extracted payload integrity | Passed independent extraction: all 18 payload lengths/hashes plus embedded manifest; see INSTALLER_VALIDATION.md. |
| Installed updated binary bytes | Pending — owner will install/test the delivered 1.1.0 artifact. |
| Updated DAW Stop/Mute/routing/drag/export/recall | OWNER_DAW_TEST_PENDING — owner will perform |
| Historical-project compatibility | OWNER_DAW_TEST_PENDING |
| Producer listening across all 27 models | LISTENING_REVIEW_PENDING |
| Refreshed 1.1.0 master/private backup | BACKUP_1_1_PENDING |
| Public 1.1.0 upload/publication | PUBLICATION_1_1_PENDING |
| Cleanup | No deletion; itemized explicit owner approval required. |

The owner-validation release may be delivered as a prerelease after binary, installer, automated advisory and render checks pass, while owner DAW/listening outcomes remain explicitly pending. Normal production certification still requires its full acceptance gates. Advice colors are stylistic, provisional and accompanied by text; all roots/scales stay available. Changing recommendations must preserve the manual scale and current notes. Suggest Scale is explicit and does not Print. [SCALE-RECOMMENDATIONS.md](#document-scale-recommendations-md) and [UI_VALIDATION.md](#document-ui-validation-md) record the actual completed behavior.

Current sanitized transcripts: [build](#document-validation-build-ghost-note-1-1-0-txt), [CTest](#document-validation-ctest-ghost-note-1-1-0-txt) and [pluginval](#document-validation-pluginval-ghost-note-1-1-0-txt). Pluginval exercised editor/open-editor-while-processing, state and 44.1/48/96 kHz with 64–1,024-sample blocks and 32-sample sub-blocks. The separate Steinberg validator was skipped because no path was configured.

Legacy restore tests covered all 38 scale IDs, exact pitch/velocity/part settings and JSON timing drift no greater than 4.44089e-16 host beats (tolerance 1e-12). Actual older FL project recall remains the owner's test.

#### Corrected musical engine evidence

Engine **AEAE3C626813FFE26D4282D1C99D80525AF4A3295C18A016AFE908037AF38613** passed **4,515,350 isolated assertions**. A full application build of the intermediate **1.0.1** passed **CTest 3/3 in 9.92 seconds**. That intermediate run predates the 1.1.0 ScaleAdvisor/UI addition and is not its feature validation.

The corrected actual-file audit independently parsed **1,080 exports**: twenty controlled plus twenty varied per model. All MIDI passed; each model/family group held twenty exact and quarter-grid-unique complete scores. Source comparisons found zero complete-score matches against twenty West Coast references; 61 selected source hashes stayed unchanged. These are bounded technical/structural findings, not authenticity or global originality. The analyzer suite passed **11 tests**. [GENRE-AUDIT.md](#document-genre-audit-md) links versioned after-1.0.1, cadence, Blues/context and matched comparisons.

Sixty additional no-library Blues MIDI fixtures verify the intended walking sixth under compatible pitch policy. The 27 authored contexts include 174 BPM DnB, explicit half-time Trap/Drill/Dubstep and C-major Strict-Off Blues. Generated feel is already encoded in events; rendering preserves exact JSON tempo/feel and source bytes. No user setting is silently replaced.

The private listening pack contains **88 technically checked WAVs**: 27 new contexts, 54 preserved historical comparisons and seven private references. All new files are finite, non-silent, unclipped stereo 48 kHz 24-bit PCM and have expected tempo-duration. All 61 previous WAVs and 115 previous source JSON/MIDI files retained their hashes. **No assistant listening occurred; human acceptance is pending for every genre.** Synthesized piano/keys/pluck approximations do not establish acoustic-instrument performance or complete production context.

#### Actual historical host evidence

On **17 November 2026**, installed **1.0.0**, VST3 SHA-256 **3a8d83a6417f7f6b4975af5ffd3ad52bc56ae7279bbdf55c32c88f918f144365**, passed a fresh verified FL Studio 2026 scan and loaded as Ghost Note / TwonOnDaBeat / VST3 / 64-bit / Synth. Search paths and existing projects were unchanged. The owner began auditioning EBK and reported positive initial feedback. This does not certify all genres or Stop/Mute, routing, drag or recall. No separate loaded-module enumeration proof is claimed. The updated 1.1.0 DAW test is assigned to the owner.

Historical **1.0.0** automated evidence remains separately identified: 4,461,313 engine + 5,713 processor + 1,452 UI assertions; CTest 3/3 in 11.56 seconds; pluginval 1.0.4 strictness 5, exit 0, seed 180001. Those logs do not validate the later scale-advice interface.

#### Owner DAW acceptance

Check the exact delivered version first, then exercise Print with recommended and experimental/unrated scales, all roots/scales, save/reopen and previously saved presets. Confirm advice refresh preserves selected scale and existing MIDI; Suggest changes only the explicit scale setting, and the next Print follows it. Test Stop while the host runs, Mute MIDI + audio, Preview Sound, selected-layer ghosts/audition, live MIDI routing, drag/import/export, bypass/reactivation, transport loops/seeks/tempo changes and historical-project recall. Independent imported patterns belong to the receiving instrument and host.

Automated state/ownership tests, offscreen editor renders, actual FL scan/load, outgoing MIDI behavior and human listening are distinct evidence classes. Processor releases require an actual host callback. The plugin cannot stop unrelated imported FL clips. No completed 1.1.0 host/listening result follows from this checklist.

#### Retained behavior and publication boundary

All 27 models, five roles, 12 roots, 38 authoritative formulas, MIDI 0–127, Type-0 channel-1 export, eight host bars, manual feel override and half-beat editing grid remain. Whole-sheet editing merges layer provenance; Undo restores it. Source/library MIDI, raw catalogs, event tables, private paths, credentials and licensed preset assets remain outside public downloads.

Preserve the organized master and existing 1.0.0 backup. A refreshed 1.1.0 backup/public upload requires separately recorded byte verification; restored sign-in alone proves neither. Cleanup remains read-only until an itemized exact-path/size/reason proposal receives explicit owner approval.

<a id="document-build-validation-md"></a>

## BUILD_VALIDATION.md

### Ghost Note build and independent plugin validation

**1.1.0 owner-validation update — Windows x64.** The exact final feature build passed technical checks on 18 November 2026; current identity and results follow. Historical logs retain their original version and are not evidence for the added advisory UI.

<!-- RELEASE_PENDING_VALIDATION: ghost-note-1.1 -->

| Current artifact evidence | Result |
|---|---|
| Release build | Release x64 build passed, 18 November 2026; exact VST3 SHA-256 below. |
| Engine / processor / UI assertions | 4/4 passed in 14.73 seconds. 4,515,350 engine; 198,071 ScaleAdvisor; 5,690 processor; 9,154 UI assertions. |
| Pure ScaleAdvisor tests | 198,071 assertions passed, including actual Strict Scale generation for all 27 × 38 pairs. |
| CTest | 4/4 passed in 14.73 seconds. 4,515,350 engine; 198,071 ScaleAdvisor; 5,690 processor; 9,154 UI assertions. |
| Advisory UI actual renders/action checks | 9,154 actual editor action/layout assertions passed; actual offscreen renders visually reviewed (see UI_VALIDATION.md). |
| VST3 SHA-256 | 9c3afcac178c5a63f9bf648713b4072d593736e4a69489d3d680d64e3e62aa70 |
| Module/PE product/version/company | Verified Ghost Note / TwonOnDaBeat / 1.1.0 in VST3 module and Windows PE metadata; stable component ID retained. |
| VST3 component / controller IDs | Retained ABCDEF019182FAEB4D6364764D633031 / ABCDEF011234ABCD4D6364764D633031. |
| Independent pluginval | Tracktion pluginval 1.0.4 strictness 5 passed, exit 0, seed 180001; editor enabled. |
| Separate Steinberg validator | Skipped: no separate Steinberg validator path configured. |
| Installation / owner DAW acceptance | Pending — owner will install/test the delivered 1.1.0 artifact. / OWNER_DAW_TEST_PENDING |
| Listening acceptance | Pending for all 27 models. |

Sanitized current transcripts: [Release build](#document-validation-build-ghost-note-1-1-0-txt), [complete CTest](#document-validation-ctest-ghost-note-1-1-0-txt), [pluginval](#document-validation-pluginval-ghost-note-1-1-0-txt). Pluginval exercised 44.1/48/96 kHz at 64/128/256/512/1,024-sample blocks and sub-block processing at 32, plus editor/open-editor-while-processing and state tests.

Legacy restore coverage preserved all 38 scale IDs and exact pitches, velocities and part settings. Maximum JSON timing drift was 4.44089e-16 host beats, below the 1e-12 tolerance. This numerical serialization tolerance does not establish actual host-project recall.

#### Reproducible configuration

C++17, Release x64, static Microsoft runtime; JUCE 8.0.16-security pinned at ea77444750de45e036e0279bb0291144bf8e3688; MSVC 19.44.35229.0 / tools 14.44.35207; Windows SDK 10.0.26100.0; CMake 4.4.5 and Ninja 1.13.2. VST3-only Ghost Note / TwonOnDaBeat; unsigned. Original artwork and bounded aggregate profiles are included; original reference MIDI is excluded. Configuration is not a passed build. See BUILD.md.

#### Separate completed snapshots

The corrected **aeae3c62** composition engine passed **4,515,350 isolated engine/MIDI assertions**. Intermediate product **1.0.1** passed Release build and **3/3 CTest in 9.92 seconds** before the scale-advice feature. Its 1,080 actual exported MIDI files and 27 authored contexts were independently checked. The adviser does not change that composition source, and source audit filenames intentionally retain 1.0.1.

Historical **1.0.0** binary **3a8d83a6417f7f6b4975af5ffd3ad52bc56ae7279bbdf55c32c88f918f144365** passed 4,461,313 engine, 5,713 processor and 1,452 UI assertions; CTest 3/3 in 11.56 seconds. Tracktion pluginval 1.0.4 passed strictness 5, exit 0, seed 180001, including Editor and Open editor whilst processing at 44.1/48/96 kHz across listed block sizes. Its separate Steinberg validator was skipped because no path was configured. Original logs: [build](#document-validation-build-ghost-note-1-0-0-txt), [CTest](#document-validation-ctest-ghost-note-1-0-0-txt), [pluginval](#document-validation-pluginval-ghost-note-1-0-0-txt).

Installed 1.0.0 passed fresh FL Studio 2026 verified scan/instrument load on 17 November. This is not updated 1.1.0 routing/transport/recall evidence. Final updated DAW testing belongs to the owner. Owner-validation/prerelease delivery can preserve those explicit pending outcomes; full production acceptance remains separate.

<a id="document-ui-validation-md"></a>

## UI_VALIDATION.md

### Ghost Note interface validation

**1.1.0 owner-validation update.** One Print, one main sheet and the resizable 880 × 620 default remain. The added feature presents genre-aware scale advice without changing manual settings or existing notes. The final 1.1.0 editor suite and actual render review passed on 18 November 2026; historical UI counts remain separate.

<!-- RELEASE_PENDING_VALIDATION: ghost-note-1.1 -->

| Current UI evidence | Result |
|---|---|
| Actual editor action/layout assertions | 9,154 passed in the final 4/4 CTest run. |
| Scale menu labels/order/colors/explanations | Passed action/label checks and actual dark/light menu render review. |
| Manual scale / existing notes preserved on advice refresh | Passed for genre/root changes; all 38 manually selected formulas preserved. |
| Explicit Suggest Scale, no Print/regeneration | Passed actual editor action/state checks. |
| All 12 roots / all 38 scales / 27 genre profiles | Passed coverage and stable selection/ID checks; advice ratings invariant under transposition. |
| Dark/light menu readability, text with color | Actual menus inspected; minimum authored tier contrast 7.99565:1 dark and 5.96382:1 light. Text labels accompany color. |
| Actual renders and visual inspection | Passed default 880 × 620, minimum/resized layouts and full dark/light scale-menu review. |
| Updated FL native-wrapper/physical-display behavior | OWNER_DAW_TEST_PENDING |

Expected behavior follows SCALE-RECOMMENDATIONS.md. Recommended, Compatible, Experimental and neutral Unrated are stylistic labels, not correctness scores. Manual selection must survive genre/root changes; the suggested default is applied only through an explicit action. Advice refresh and Suggest must not Print or corrupt the current sheet. Existing saved scale/style IDs and previous preset state remain valid.

Stop, Mute MIDI + audio, Preview Sound, selected-layer audition and faint reference notes retain their established roles. Full-sheet editing merges layers; Undo restores the prior state. MIDI export matches the selected target. All model labels, scale labels and Unicode timing/grid text must remain readable in compact/resized layouts. A/B acceptance, Keep/Discard and composition-save browser are not reintroduced.

The [final CTest transcript](#document-validation-ctest-ghost-note-1-1-0-txt) records all current counts. Legacy preset restore checks retained all 38 scale IDs, exact pitch/velocity/part settings, and maximum JSON timing drift 4.44089e-16 host beats, below the 1e-12 tolerance. No older test was relabeled to obtain this pass.

Render/contrast inspection is scoped to the actual tested editor images and authored colors. It is not a complete accessibility audit or proof of physical-display DPI transitions/native-wrapper focus.

#### Historical evidence

The 1.0.0 suite passed 1,452 UI assertions on 16 November, rendering 800 × 540, 880 × 620, 920 × 650 and 1,280 × 850 plus 1.5×. Default and G-Funk advanced images were visually inspected. These images and the [1.0.0 CTest log](#document-validation-ctest-ghost-note-1-0-0-txt) predate advisory controls and do not validate them.

The corrected intermediate 1.0.1 application passed CTest 3/3 in 9.92 seconds before the new adviser. The pure adviser separately passed 198,071 assertions; that suite checks lookups, invariance and actual generation under selected formulas, not UI rendering. Current build/pluginval results belong in BUILD_VALIDATION.md.

Installed 1.0.0 passed fresh FL verified scan/instrument load on 17 November. The owner will test the updated 1.1.0 DAW workflow. Offscreen renders do not prove physical DPI transitions, native wrapper focus or all accessibility behavior; exact completed scopes must remain explicit.

<a id="document-installer-validation-md"></a>

## INSTALLER_VALIDATION.md

### Ghost Note installer verification

**Ghost Note 1.1.0 — owner-validation prerelease, Windows x64.** The exact final installer passed independent extraction/payload verification on 18 November 2026. The owner will perform updated DAW acceptance; no all-genre listening pass is claimed.

<!-- RELEASE_PENDING_VALIDATION: ghost-note-1.1 -->

| Current evidence | Result |
|---|---|
| Installer | Ghost-Note-VST3-Setup-1.1.0-Windows.exe |
| Size | 5,812,703 bytes |
| Installer SHA-256 | e678e914052a9bdd6680949849a27432d521841bdc9d76620311ccdc2ecd2cc9 |
| VST3 SHA-256 | 9c3afcac178c5a63f9bf648713b4072d593736e4a69489d3d680d64e3e62aa70 |
| Module/Windows PE product, company, version | Verified Ghost Note / TwonOnDaBeat / 1.1.0 in VST3 module and Windows PE metadata; stable component ID retained. |
| Stable component / controller IDs | Verified ABCDEF019182FAEB4D6364764D633031 / ABCDEF011234ABCD4D6364764D633031, unchanged. |
| Archive CRC/extraction | Passed 7-Zip CRC/integrity test and independent extraction. |
| Payload lengths/hashes | All 18 manifest-listed payload files matched exact lengths and SHA-256; 19 verified items including the embedded manifest. |
| Embedded/external manifests | Embedded manifest verified against the external payload manifest. |
| Updated Windows installation/hashes | Pending — owner will install/test the delivered 1.1.0 artifact. |
| Updated FL Stop/Mute, routing, transfer and recall | OWNER_DAW_TEST_PENDING |
| Historical-project compatibility | OWNER_DAW_TEST_PENDING |
| Human listening | Pending for all 27 models. |
| Generated uninstaller / standalone app | Uninstaller present; no standalone music app in the payload. |
| Authenticode | Unsigned. |

NSIS 3.12 builds the installer. Independent 7-Zip extraction checks archive integrity and every current manifest length/SHA-256, the embedded manifest and metadata. Extraction does not run setup, validate an installation/uninstall transaction or establish host behavior. The installer's final checksum belongs outside its own payload documents.

The bundle installs as **Ghost Note.vst3** under standard Common Files VST3. Documentation/uninstaller use its dedicated program folder. The EXE is an installer, leaves saved FL search paths unchanged and operates offline. The stable installed user guide is separate from evolving external validation reports.

#### Historical installed 1.0.0

The renamed **Ghost Note / TwonOnDaBeat 1.0.0** installation was checked against all **18 payload files plus the installed manifest**. Its VST3 SHA-256 was `3a8d83a6417f7f6b4975af5ffd3ad52bc56ae7279bbdf55c32c88f918f144365`. A fresh FL Studio 2026 verified scan and instrument load passed on **17 November 2026**; the favorite was added and saved search paths were unchanged. This historical success does not validate the later 1.1.0 binary, live routing, Stop/Mute, drag/export, state recall or old-project compatibility.

No signing, external security certificate, unperformed uninstall or updated host result is claimed. Keep prior installations until replacement acceptance. Consolidation requires a read-only inventory and an itemized exact-path/size/reason proposal explicitly approved by the owner before deletion. No cleanup removal is claimed.

<a id="document-library-method-md"></a>

## LIBRARY-METHOD.md

### Library-informed composition

Ghost Note uses an offline procedural engine with bounded statistical guidance from the owner's local MIDI collection. It does not contain an AI model, replay a source phrase, or require access to the original collection at runtime.

#### What was analyzed

A recursive, read-only scan found **10,868 MIDI files**. The analysis accepted **2,111 unique pitched track/channel streams**: 193 melody, 64 bass and 1,854 chords. It excluded **649 percussion streams** and placed **6,586 uncertain streams** in a review list. There were 970 exact duplicate files, 141 further structural stream duplicates and 217 parser-review files. Duplicate material does not receive repeated statistical weight.

A mixed MIDI file is evaluated by track and channel. Only accepted pitched streams contribute to the profile; the file is never imported wholesale. Channel 10 identifies percussion. Program information, register, polyphony, simultaneous attacks, pitch variation, note lengths and rhythmic behavior provide additional evidence. Filenames can corroborate that evidence, but cannot establish an accepted role by themselves. Conflicting, sparse, mixed-role, malformed or percussion-like material remains in review. Tuned percussion instruments are not automatically rejected just because of their program name.

The analyzer passed **27 checks**, and its plugin-profile exporter passed **five separate checks**, including normalized histogram shape and chord-voicing gap extraction. All 10,868 original file hashes matched a readback after analysis. The detailed indexes, review manifests and reproducible analysis tools are retained privately with the source backup. No source MIDI files are redistributed.

#### How the profile affects a new print

Accepted material supplies aggregate distributions of beat-position attacks, durations, relative melodic intervals, adjacent simultaneous chord-voice gaps and confidently estimated diatonic chord transitions. These influence new rhythmic placement, articulation, movement, compatible harmonic choices and restrained chord spacing. The profile contains no full note sequences or complete source phrases.

The catalog now retains 24 earlier genre entries and adds EBK, Modern LA and Classic G-Funk. The broader all-genre audit evaluates what their shared and specialized algorithms actually produce; labels alone do not establish authenticity. Genre names inferred from library folders are **unverified hints**. General library phrasing has bounded influence where matching evidence is absent. These statistics do not establish verified genre accuracy for every clip or generated idea.

##### Afrobeats classification quarantine

The audit found that the historical `afrobeats` path hint included folders labeled **Afrobeat**. Those labels do not establish contemporary Afrobeats, and the traditions must not be conflated. The revised factory catalog therefore replaces profile **12** with the weak **overall general fallback**, marks it `generalFallback`, and suppresses learned harmonic-degree/transition guidance (`harmonySamples = 0`, `chordTransitions = 0`). Reviewed contemporary Afrobeats research and authored musical rules govern that model; the mislabeled folder material does not supply a certified genre-specific prior.

Frozen v0.3 baseline exports preserve the old behavior for an honest comparison. The frozen-source factory-loaded export audit matches the revised catalog and confirms profile 12's general fallback. This quarantine does not relabel the original files, modify the owner's library, establish every other folder label as correct, or turn a weak general fallback into an Afrobeats training set. The 41-file bounded owned sample is documented in GENRE-OWNED-MIDI-SAMPLE.md with its unverified-label and vendor-concentration limits.

The chord-spacing prior uses a 13-bin histogram of adjacent gaps from accepted simultaneous source voicings, rather than borrowing a melodic-interval histogram. Voice leading, register bounds, compatible chord tones and the selected genre remain dominant. A controlled contrast test changed compatible voicings in 44 of 384 generated arrangements while roots and progression stayed identical. Phrase lengths, density and relationships between source parts were also measured, but not every measured feature is a separate generation model. Only five usable cross-role source pairs were available. Countermelody is therefore composed as an answer to the current melody and shared harmony, rather than being presented as a trained independent source role.

A print shares one key, harmonic timeline, loop duration and phrase structure across five coordinated layers. The default combines them into one editable sheet and one MIDI track on channel 1; Advanced selects a layer independently. Other-layer ghost references are visual only. Overlapping/touching equal-pitch notes are united for safe merged playback. A profile snapshot is retained with settings so stored seeds can reproduce their input statistics. Complete-sheet editing merges layer provenance; Undo restores the earlier state.

#### Focused West Coast reference audit

Seven supplied examples and thirteen supplemental files already owned in the local library were parsed as actual MIDI before the new West Coast models were implemented. All twenty remained byte-for-byte unchanged. Their harmonic sets, clustered attacks, lengths, repetition, register, lead/bass patterns and dynamics informed separate EBK, Modern LA and Classic G-Funk rules. No additional external MIDI was downloaded, and no source event sequence is embedded. WEST-COAST-REFERENCES.md records the complete public-safe analysis; WEST-COAST-UPDATE.md separates measured tendencies from theory-led extensions and catalog-only research.

The twenty references do not provide labeled paired counter-melodies or pitch-bend/controller/aftertouch evidence. Swing, optional chromatic tension and paired-part coordination are composed extensions rather than falsely claimed source measurements. GENRE-AUDIT.md separates completed frozen-source baseline/revised comparisons from the final binary, host and listening gates still pending in TESTING.md.

#### Variety and preservation

Print makes bounded attempts against recent pitch/rhythm fingerprints, then writes the result directly into the current sheet. Velocity, sound changes and tiny humanization offsets do not make the same musical structure count as a new idea. Recent print fingerprints survive plugin-state save/restore. Explicit seed replay can intentionally repeat material. This is best effort, not a guarantee of global musical uniqueness. Undo/Redo recovers earlier prints and edits during the session; it is not a separate saved-ideas browser.

The original library remains separate from the plugin. Reviewing uncertain files and changing the accepted profile are deliberate development actions; the plugin does not silently scan drives or import quarantined files.

<a id="document-third-party-md"></a>

## THIRD_PARTY.md

### Dependencies, licensing and sound origins

#### Product, library patterns and preview sounds

Ghost Note contains project-specific procedural music generation, MIDI writing, scheduling, interface and state code. It operates offline without an AI-model service.

The library-informed profile contains bounded aggregate statistics derived from accepted pitched material in the owner's collection. No original library MIDI files, full source phrases, recordings, samples or commercial preset banks are embedded or redistributed. Review lists and original source files remain separate. **LIBRARY-METHOD.md** describes classification, duplicate handling, weak genre hints and the limits of those statistics. Aggregate guidance and repeat checks do not guarantee that a phrase is globally unique.

The eight preview voices use original oscillator/envelope formulas: soft piano-like additive decay, electric-piano-like FM, nylon-like harmonic pluck, short muted pluck, inharmonic FM bell, bright pluck, slow sine pad and sine sub bass. Their names describe synthesized approximations, not realistic multisampled acoustic instruments. Exported MIDI contains no preview audio; receiving instruments determine final tone and glide.

Project-specific source remains private and no open-source license is granted to it by the binary download. Third-party notices have their own terms. **TwonOnDaBeat** is the product/publisher credit requested by the owner; this document does not certify brand-name availability.

#### JUCE

The framework is **JUCE 8.0.16-security**, pinned commit `ea77444750de45e036e0279bb0291144bf8e3688`, from the [official JUCE repository](https://github.com/juce-framework/JUCE). Its exact bundled license is included as JUCE-LICENSE.md. Closed-source distribution requires the applicable JUCE license and continuing eligibility under the [official JUCE 8 terms](https://juce.com/legal/juce-8-licence/).

During this development session, the owner confirmed: **“I use or qualify for JUCE Starter (within its revenue/funding limit).”** This is owner-provided confirmation, not an independent licensing audit, license purchase or certification. The owner remains responsible for continuing eligibility, any required contributor seats and compliance. The version pin supports reproducibility; it does not guarantee absence of dependency defects.

#### VST3 and installer

The exact VST3 SDK bundled with the pinned JUCE tree uses the MIT license, retained as VST3-SDK-LICENSE.txt. [Steinberg's VST SDK information](https://www.steinberg.net/developers/vstsdk/) describes its licensing. Steinberg marks/logos have separate usage rules; this build adds no Steinberg logo.

The offline EXE installer is built using NSIS 3.12. Its notice accompanies the installer. Build tools and compiler packages are development dependencies and are excluded from application downloads. Windows system libraries and compiler runtimes retain their own terms.

#### Other notices and scale facts

Applicable JUCE module notices are retained in the package's `third-party-licenses` folder, including zlib, libpng, libjpeg, HarfBuzz and SheenBidi. Build options disable ASIO, browser integration, curl and optional FLAC/Ogg/MP3 decoding. Recheck the compiled dependency inventory before distribution.

The scale catalog records numeric pitch-class formulas audited from installed FL Studio reference scores, plus standard Chromatic. No proprietary FSC score file, Image-Line logo or vendor interface artwork is bundled. Named scale traditions can have multiple variants; these formulas follow the audited installation. Cymatics and Unison tools served as workflow references; their code, interface assets and sound libraries are not included.

#### Original visual artwork

The new manuscript-paper ghost artwork was generated specifically for this project with the built-in image generation tool and no external reference. See ARTWORK.md and GHOST-NOTE-ARTWORK.md for the saved asset, final prompt and provenance. Generated artwork and naming checks do not establish exclusive trademark rights.

<a id="document-genre-audit-md"></a>

## GENRE-AUDIT.md

### Complete genre audit and refinement

Current musical freeze: **aeae3c62**, 17 November 2026; product **1.1.0 owner-validation update**. The scale adviser is a separate advisory layer and does not modify this engine or existing notes. Priority remains genre accuracy, musical quality, then variety. All 27 model IDs/names, five roles, 12 roots and 38 scale formulas remain.

#### Corrected source and actual outputs

The engine SHA-256 is **AEAE3C626813FFE26D4282D1C99D80525AF4A3295C18A016AFE908037AF38613**. [Scoped corrections](#document-genre-corrections-1-0-1-md) records the six-model cadence policy, scale-valid Blues walking sixth and Strict-Off dominant-seventh eight-bar Blues branch. Selected settings and Strict Scale remain authoritative. A supported eight-bar Blues interpretation is not a twelve-bar-form claim.

[Corrected MIDI audit](#document-genre-refined-midi-audit-1-0-1-md) independently parsed **1,080 actual exports**: twenty controlled plus twenty varied examples for every model. All 1,080 passed; each of the 54 model/family groups had twenty exact and quarter-grid-unique scores. The [original-baseline comparison](#document-genre-before-after-comparison-1-0-1-md) and [installed-1.0.0-source comparison](#document-genre-installed-comparison-1-0-1-md) keep those two earlier snapshots distinct. Zero complete-score matches to twenty West Coast references and 61 unchanged selected source hashes are bounded anti-copy/coverage screens, not global originality or musical-quality certificates. The corrected comparison retains 86 contextual review cues; those are not a usability-failure count.

The [cadence-frequency report](#document-genre-cadence-comparison-1-0-1-md) counts actual generated ending pairs, rather than inferring them from code. The [Blues/context report](#document-genre-blues-context-1-0-1-md) checks scale-valid sixth retention, 60 additional no-library MIDI fixtures and 27 authored listening contexts. The active learned profile can intentionally alter an interval; isolated fixtures distinguish that from the repaired chord-quantization defect. Strict-Off C-major Blues contains complete dominant-seventh pitch sets in all 11 generated harmonic regions.

The corrected source suite passed **4,515,350 isolated engine/MIDI assertions**. The analyzer's **11 tests** passed separately. Product 1.1.0 build/processor/UI/pluginval results belong in [TESTING.md](#document-testing-md); source metrics cannot stand in for them.

#### Listening preparation and remaining judgment

The private audition pack contains **88 WAVs**: 27 new authored-context renders from aeae3c62, 54 preserved controlled before/after WAVs from historical freeze 995dd679, and seven preserved user-owned West Coast references. Actual installed Vital and Serum 2 instruments supplied the renders. All new WAVs independently passed 24-bit stereo 48 kHz PCM format, finite/non-silent/clipping and exact BPM-duration checks. All 61 earlier WAV hashes and 115 earlier JSON/MIDI source hashes remained unchanged.

The new contexts use the exact generated JSON BPM, feel and note events. Feel is already encoded in beat-domain events; the renderer does not apply it twice. The new context composition is not a matched third side of an earlier controlled pair. Jazz/Country/Blues bass uses an explicitly labeled synthesized plucked-string approximation, not sampled upright/acoustic bass. There are no added drums, vocals or receiving-instrument glide/articulation claims.

**The assistant could not hear these files. Human listening acceptance remains pending for all 27 models.** The private review page provides bounded per-genre scopes/questions and records feedback separately for new contexts and historical pairs. Exact private paths, role snapshots and original reference identities stay out of public reports. [GENRE-LISTENING-STATUS.md](#document-genre-listening-status-md) summarizes the evidence boundary.

#### Research and historical snapshots

The existing source/research ledgers retain their historical meaning:

- [Architecture audit](#document-genre-architecture-audit-md), [baseline MIDI audit](#document-genre-baseline-midi-audit-md) and [per-model review](#document-genre-before-model-review-md) describe the earlier 1,080-file baseline.
- [Hip-hop/pop/guitar research](#document-genre-research-hiphop-pop-md), [electronic/Afrobeats/reggaeton research](#document-genre-research-electronic-md) and [acoustic/traditional research](#document-genre-research-acoustic-md) identify primary sources, intended substyles and authored engineering inferences.
- [Owned sample](#document-genre-owned-midi-sample-md) describes 41 actual files with unverified folder hints and vendor concentration. Historical Afrobeat/Afrobeats hints are quarantined; profile 12 uses weak fallback without learned harmonic-degree/transition forcing.
- [West Coast references](#document-west-coast-references-md) measures seven supplied plus thirteen supplemental owned MIDI files. Sources were read-only, not paired stems; no pitch-bend performance was present.
- Unversioned refined/comparison/example reports identify historical **995dd679**, not the corrected aeae3c62 freeze. Their historical measurements remain preserved.

Text lessons/interviews were read; embedded online audio/video was not heard and external MIDI payloads were not downloaded. Original MIDI and reusable source-event sequences are excluded from public downloads. Strict Scale remains authoritative even when source music uses mixture or secondary dominants. Sound, drums, performance, arrangement and cultural context remain material to genre recognition. No uniqueness count, label, valid export or scale recommendation establishes a global genre pass.

<a id="document-genre-corrections-1-0-1-md"></a>

## GENRE-CORRECTIONS-1.0.1.md

### Scoped cadence and Blues corrections

Snapshot: corrected composition engine **aeae3c62**, frozen 17 November 2026. The 1.0.1 filename identifies this musical audit; the advisory-only scale feature in product 1.1.0 does not change this engine or these generated settings. Source evidence is separate from final plugin/UI/host acceptance.

Implemented and frozen 17 November 2026. Scope: `src/Engine.cpp` and `tests/EngineTests.cpp`. The product API, stable style/scale IDs, 38 scale formulas, selected settings, layer/routing structure and loop duration remain intact. Build/version/package changes are owned separately by the parent task. No audio was heard; this report establishes composition-rule behavior and technical validity, not listening acceptance or a genre-authenticity percentage.

#### Frozen files

| File | SHA-256 |
|---|---|
| `src/Engine.cpp` | `AEAE3C626813FFE26D4282D1C99D80525AF4A3295C18A016AFE908037AF38613` |
| `tests/EngineTests.cpp` | `9B93714DFD99DDE51969A7B99E227FB19F4E568579248B99BECD01E46189D1D9` |

The retained prior engine is the retained earlier engine snapshot, SHA-256 `995DD679A5B1D0904A023818394214A6032DE049E137DADDF5CC4103A2FED991`.

#### Cadence policy

The six flagged models no longer all overwrite their final two harmonic events with the same predominant/dominant rule. A cadence is selected once when composing a harmonic cell; the composed cell is then recalled through the loop. Degree priors, holds, functional transitions, compatible voicing and bounded learned influence remain active.

| Model | Phrase policy |
|---|---|
| Afrobeats | Cyclic modal/pop prior; no forced functional cadence. Related harmonic areas and return remain weighted choices. |
| Pop | Open loop or selected half/authentic/plagal cadence. Half-cadence preparation favors IV over ii. |
| R&B | Open loop or selected half/authentic/plagal cadence; existing functional connections and rich compatible voicings remain. |
| Lo-fi | Open loop is more common; optional half/authentic/plagal closure retains its longer harmonic pacing. |
| Disco | Open loop or optional half/authentic/plagal closure over its continuing bass pulse. |
| Dark Latin Guitar | Open loop or a bounded descending seventh/sixth-area approach to V, using the actual selected formula for qualities. |

Numeric branch probabilities are authored engineering decisions, not source-measured genre frequencies. Existing Jazz, Gospel, Country and Classical cadence code paths retain their earlier seeded resolution behavior; other unaffected legacy harmony paths retain their earlier rules. This is a small family of phrase grammars, not a pool of reference MIDI melodies or an independent new degree on every event.

Actual no-library generated output, seeds `93000`–`93127`, A natural minor, Strict On, normal feel, 16 host bars, zero humanization and otherwise default controls:

| First harmonic cell's final ii→v | Count / 128 |
|---|---:|
| Afrobeats | 0 |
| Pop | 6 |
| Dark Latin Guitar | 8 |
| R&B | 13 |
| Lo-fi | 9 |
| Disco | 10 |

The regression inspects actual `Arrangement.chords`, checks multiple ending destinations and differing seeded ending distributions, and verifies the later recall of the four-event cell. These counts diagnose removal of the shared shortcut; they do not measure musical authenticity.

#### Blues walking bass

The authored root/fifth/sixth/fifth walk now passes through scale/range policy rather than being quantized back to a chord triad. Its root register leaves room for the sixth. Strict On still constrains every emitted pitch to the selected formula. With a library profile, bounded learned interval changes can still alter an individual walk; exact-interval regressions therefore isolate the no-library grammar.

Actual D-major Strict On output, seed `120138`, normal feel, zero humanization, no library and otherwise default controls: opening bass **38, 45, 47, 45** = **D2, A2, B2, A2**. The former chord quantization gave D2, A2, A2, A2. Every transposed major opening was checked over 16 seeds; every strict natural-minor opening reduces the sixth to the allowed minor sixth rather than admitting an out-of-scale major sixth.

#### Traditional eight-bar Blues under Strict Off

Strict Off selects explicit dominant-seventh I/IV/V harmony. The full-bar branch is I7–V7–IV7–IV7–I7–V7–I7–V7. A second branch sustains the tonic in bar two and uses selected half-bar changes in the final turnaround. Existing authored call/response phrases, seeded voice leading and optional layers provide variation. No reference MIDI melody was copied.

Actual C-major Strict Off output, root C, scale ID 1, seed `120138`, variation 0, normal feel, zero humanization, no library and otherwise default controls: **C7, G7, F7, F7, C7, G7, C7, G7**. Every generated harmony region contains the actual relative pitch classes **0, 4, 7, 10**, with its true root in its name and I7/IV7/V7 label.

The form occupies eight musical bars under normal feel. The existing feel multiplier remains authoritative; 4/8/16 host-bar prints truncate or recall this cycle as appropriate. No tempo, key or selected scale is silently replaced.

Compatibility detail: `Chord.degree` remains a valid index into the selected formula, including unusual formulas that lack an exact IV or V root. In those strict-off cases it stores the existing nearest-degree mapping. The true root is represented by the actual dominant-seventh pitch set and accurate chord name/Roman label; bass and optional layer root support find that actual dominant root. No new serialized field or schema is introduced. Strict On never takes this chromatic branch and continues to derive both roots and pitches from the exact selected formula.

Sources actually read for the bounded eight-bar form:

- [Your Guitar Academy: How To Play An 8 Bar Blues, Part 1](https://yourguitaracademy.com/blog/guitar-lessons/how-to-play-8-bar-blues-part-1) supplies an eight-bar dominant-chord framework, split turnaround and optional extensions.
- [Fretello: Eight Bar Blues in C major](https://fretello.com/jam/blues/8-bar-blues-i/) explicitly gives the C7–G7–F7–F7–C7–G7–C7–G7 form and a minor-pentatonic lead suggestion. The harmony form is a conventional framework; its audio was not heard and no melody was transcribed.

The independent review and all three existing `docs/GENRE-RESEARCH-*` ledgers were also read. Their stated source/listening limitations still apply.

#### Verification

Built in isolation using the bundled LLVM MinGW toolchain:

```text
clang++.exe -O2 -std=c++17 -Wall -Wextra -Wpedantic
  src/Engine.cpp tests/EngineTests.cpp
  -I src
  -o engine_tests.exe
```

Compilation completed without diagnostics. The complete engine/MIDI suite passed: **4,515,350 assertions**, exit code 0. Added regressions cover scoped cadence distributions and replay; exact D-major walk; all 12 transpositions of major/natural-minor walking policy over 16 seeds; Blues Strict On and Strict Off across all 38 formulas with three feel/loop-length contexts; actual dominant pitch classes, truthful names and actual-root bass; both eight-bar forms; and all six optional layer approaches with targeted bass regeneration while preserving harmony. Existing engine, MIDI serialization, scale, layer, regeneration and West Coast tests also passed.

The parent task owns the full application/processor/UI build. A separate audit agent was notified of this exact source freeze for its 1,080-output comparison and additional no-library Blues fixtures. Their results should be reported separately from these isolated engine checks.

<a id="document-genre-refined-midi-audit-1-0-1-md"></a>

## GENRE-REFINED-MIDI-AUDIT-1.0.1.md

### Actual MIDI output audit

Snapshot: corrected composition engine **aeae3c62**, frozen 17 November 2026. The 1.0.1 filename identifies this musical audit; the advisory-only scale feature in product 1.1.0 does not change this engine or these generated settings. Source evidence is separate from final plugin/UI/host acceptance.

Analyzed **1080 actual exported MIDI files**, with separate role and harmonic snapshots, against 20 read-only local West Coast sources.

Priority: genre accuracy, musical quality, then variety. The table screens musical structure; uniqueness, scale membership, tempo and labels cannot establish authenticity. No audio was rendered or heard in this analysis.

The controlled family holds A natural minor, 120 BPM, normal feel, complexity 0.5, humanization 0 and the same twenty seeds. The varied family changes root, major/minor, BPM, feel and complexity. All examples use the actual active embedded library profile or the plugin-equivalent overall fallback. Disabled Chord Layer notes are measured separately and excluded from the audible score.

| Model | Family | Actual valid | Exact / quarter-grid unique | Degree progressions | Melody attacks / 4 pulses | Median melody gate | Melody repeated intervals | Counter gap entries | Extended harmony |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Melodic Rap | controlled | 20/20 | 20 / 20 | 17 | 3.50 | 0.83 | 19% | 100% | 0% |
| Melodic Rap | varied | 20/20 | 20 / 20 | 18 | 3.50 | 0.83 | 26% | 100% | 50% |
| Trap | controlled | 20/20 | 20 / 20 | 6 | 3.00 | 0.52 | 52% | 100% | 0% |
| Trap | varied | 20/20 | 20 / 20 | 8 | 3.00 | 0.52 | 57% | 100% | 50% |
| R&B | controlled | 20/20 | 20 / 20 | 19 | 2.50 | 0.95 | 54% | 100% | 100% |
| R&B | varied | 20/20 | 20 / 20 | 20 | 2.50 | 0.95 | 50% | 100% | 100% |
| Drill | controlled | 20/20 | 20 / 20 | 6 | 2.50 | 0.46 | 55% | 100% | 0% |
| Drill | varied | 20/20 | 20 / 20 | 8 | 2.25 | 0.46 | 53% | 100% | 50% |
| Bay Area | controlled | 20/20 | 20 / 20 | 5 | 2.75 | 0.40 | 60% | 100% | 0% |
| Bay Area | varied | 20/20 | 20 / 20 | 6 | 2.75 | 0.40 | 53% | 100% | 50% |
| Dark Latin Guitar | controlled | 20/20 | 20 / 20 | 12 | 3.75 | 0.80 | 29% | 100% | 0% |
| Dark Latin Guitar | varied | 20/20 | 20 / 20 | 14 | 3.75 | 0.80 | 24% | 100% | 50% |
| Pop | controlled | 20/20 | 20 / 20 | 18 | 3.50 | 0.90 | 19% | 100% | 0% |
| Pop | varied | 20/20 | 20 / 20 | 19 | 3.50 | 0.90 | 16% | 100% | 50% |
| House | controlled | 20/20 | 20 / 20 | 17 | 3.50 | 0.50 | 85% | 100% | 0% |
| House | varied | 20/20 | 20 / 20 | 17 | 3.50 | 0.50 | 85% | 100% | 50% |
| Techno | controlled | 20/20 | 20 / 20 | 3 | 6.00 | 0.28 | 65% | 100% | 0% |
| Techno | varied | 20/20 | 20 / 20 | 4 | 5.75 | 0.28 | 67% | 100% | 50% |
| Drum & Bass | controlled | 20/20 | 20 / 20 | 17 | 3.25 | 0.90 | 24% | 100% | 0% |
| Drum & Bass | varied | 20/20 | 20 / 20 | 16 | 3.25 | 0.90 | 25% | 100% | 50% |
| Lo-fi | controlled | 20/20 | 20 / 20 | 19 | 2.50 | 0.94 | 53% | 100% | 100% |
| Lo-fi | varied | 20/20 | 20 / 20 | 14 | 2.50 | 0.94 | 54% | 100% | 100% |
| Jazz | controlled | 20/20 | 20 / 20 | 11 | 4.12 | 0.72 | 33% | 100% | 100% |
| Jazz | varied | 20/20 | 20 / 20 | 14 | 4.25 | 0.73 | 30% | 100% | 100% |
| Afrobeats | controlled | 20/20 | 20 / 20 | 17 | 3.25 | 0.42 | 62% | 100% | 0% |
| Afrobeats | varied | 20/20 | 20 / 20 | 18 | 3.38 | 0.42 | 57% | 100% | 50% |
| Reggaeton | controlled | 20/20 | 20 / 20 | 17 | 3.25 | 0.57 | 48% | 100% | 0% |
| Reggaeton | varied | 20/20 | 20 / 20 | 18 | 3.38 | 0.57 | 47% | 100% | 50% |
| Rock | controlled | 20/20 | 20 / 20 | 15 | 4.50 | 0.68 | 64% | 100% | 0% |
| Rock | varied | 20/20 | 20 / 20 | 16 | 4.50 | 0.68 | 59% | 100% | 50% |
| Ambient | controlled | 20/20 | 20 / 20 | 6 | 0.62 | 4.26 | 88% | 100% | 0% |
| Ambient | varied | 20/20 | 20 / 20 | 7 | 0.62 | 4.26 | 100% | 100% | 50% |
| Funk | controlled | 20/20 | 20 / 20 | 3 | 3.50 | 0.24 | 73% | 100% | 0% |
| Funk | varied | 20/20 | 20 / 20 | 5 | 3.50 | 0.24 | 68% | 100% | 50% |
| Disco | controlled | 20/20 | 20 / 20 | 19 | 3.50 | 0.60 | 22% | 100% | 100% |
| Disco | varied | 20/20 | 20 / 20 | 19 | 3.50 | 0.60 | 21% | 100% | 100% |
| Country | controlled | 20/20 | 20 / 20 | 6 | 3.75 | 0.82 | 48% | 100% | 0% |
| Country | varied | 20/20 | 20 / 20 | 10 | 3.88 | 0.82 | 39% | 100% | 50% |
| Gospel | controlled | 20/20 | 20 / 20 | 9 | 2.50 | 0.80 | 37% | 100% | 100% |
| Gospel | varied | 20/20 | 20 / 20 | 13 | 3.00 | 0.80 | 35% | 100% | 100% |
| Classical | controlled | 20/20 | 20 / 20 | 20 | 5.25 | 0.45 | 28% | 100% | 0% |
| Classical | varied | 20/20 | 20 / 20 | 16 | 5.38 | 0.45 | 20% | 100% | 50% |
| Blues | controlled | 20/20 | 20 / 20 | 5 | 4.00 | 0.70 | 47% | 100% | 0% |
| Blues | varied | 20/20 | 20 / 20 | 8 | 4.00 | 0.71 | 48% | 100% | 50% |
| Dubstep | controlled | 20/20 | 20 / 20 | 5 | 1.88 | 0.75 | 73% | 100% | 0% |
| Dubstep | varied | 20/20 | 20 / 20 | 7 | 2.00 | 0.75 | 77% | 100% | 50% |
| Trance | controlled | 20/20 | 20 / 20 | 16 | 8.00 | 0.45 | 25% | 0% | 0% |
| Trance | varied | 20/20 | 20 / 20 | 13 | 8.00 | 0.45 | 27% | 0% | 50% |
| EBK - Dark NorCal Piano | controlled | 20/20 | 20 / 20 | 8 | 2.75 | 0.44 | 25% | 100% | 0% |
| EBK - Dark NorCal Piano | varied | 20/20 | 20 / 20 | 11 | 2.88 | 0.46 | 20% | 100% | 0% |
| LA - Modern West Coast | controlled | 20/20 | 20 / 20 | 8 | 3.25 | 0.42 | 34% | 100% | 100% |
| LA - Modern West Coast | varied | 20/20 | 20 / 20 | 9 | 3.38 | 0.42 | 32% | 100% | 100% |
| Classic G-Funk | controlled | 20/20 | 20 / 20 | 9 | 3.00 | 0.44 | 30% | 100% | 100% |
| Classic G-Funk | varied | 20/20 | 20 / 20 | 11 | 3.12 | 0.44 | 33% | 100% | 100% |

Measurement definitions: chord attacks within 1/12 beat are clustered; melodic contour uses the highest attack note, not arbitrary strum note order. Gates/density are measured in musical pulses, accounting for feel. Quarter-grid uniqueness ignores transposition, velocity, channels and initial silence. Voice movement is symmetric nearest-pitch distance, not fixed labeled voices. Strong/long chord-tone membership is a screen, not a rule that passing notes are wrong. Semitone/unison overlap is reported without assuming all dissonance is a defect. Observed offbeat displacement is not a certified swing ratio.

Exact and nearest-quarter-grid complete-score comparisons detect no matches unless recorded in the JSON. They do not detect excerpt quotation, all possible transpositions/edits, or similarity to music outside the twenty references. Genre authenticity and pleasantness require listening with appropriate instruments and broader reference evidence.

The source-event lists and source paths remain in private records. Source MIDI files were opened read-only and their final SHA-256 hashes verified again. Generated example JSON and metrics permit reproducible role, rhythm, harmony and counterline analysis.

<a id="document-genre-before-after-comparison-1-0-1-md"></a>

## GENRE-BEFORE-AFTER-COMPARISON-1.0.1.md

### Matched before/after MIDI output comparison

Snapshot: corrected composition engine **aeae3c62**, frozen 17 November 2026. The 1.0.1 filename identifies this musical audit; the advisory-only scale feature in product 1.1.0 does not change this engine or these generated settings. Source evidence is separate from final plugin/UI/host acceptance.

Compared 1080 same-model/family/seed pairs from 1080 before and 1080 after actual MIDI files. Controlled examples use the same A minor, 120 BPM, normal feel and complexity 0.5 settings.

These are structural measurements and listening review cues. A metric increasing or decreasing is not automatically an improvement. No authenticity or pleasantness score is calculated; no audio was heard by this tool.

| Model | Lead attacks/4p before→after | Lead gate before→after | Bass span before→after | Chord gate before→after | Degree sequences before→after | Counter gap before→after |
|---|---|---|---|---|---|---|
| Melodic Rap | 3.50 → 3.50 | 0.80 → 0.83 | 13.00 → 7.00 | 0.75 → 0.75 | 3.00 → 17.00 | 1.00 → 1.00 |
| Trap | 4.50 → 3.00 | 0.56 → 0.52 | 19.00 → 12.00 | 1.10 → 1.10 | 13.00 → 6.00 | 1.00 → 1.00 |
| R&B | 3.50 → 2.50 | 1.19 → 0.95 | 12.00 → 10.00 | 3.72 → 3.72 | 13.00 → 19.00 | 1.00 → 1.00 |
| Drill | 3.50 → 2.50 | 0.48 → 0.46 | 17.00 → 12.00 | 0.70 → 0.70 | 9.00 → 6.00 | 1.00 → 1.00 |
| Bay Area | 3.00 → 2.75 | 0.48 → 0.40 | 14.00 → 12.00 | 0.42 → 0.42 | 3.00 → 5.00 | 1.00 → 1.00 |
| Dark Latin Guitar | 4.50 → 3.75 | 0.60 → 0.80 | 17.00 → 15.00 | 0.75 → 0.75 | 3.00 → 12.00 | 1.00 → 1.00 |
| Pop | 3.50 → 3.50 | 0.66 → 0.90 | 12.00 → 10.50 | 1.70 → 1.70 | 12.00 → 18.00 | 1.00 → 1.00 |
| House | 5.00 → 3.50 | 0.33 → 0.50 | 17.00 → 16.00 | 0.36 → 0.36 | 9.00 → 17.00 | 0.50 → 1.00 |
| Techno | 7.00 → 6.00 | 0.15 → 0.28 | 13.00 → 0.00 | 0.22 → 0.22 | 3.00 → 3.00 | 0.50 → 1.00 |
| Drum & Bass | 5.00 → 3.25 | 0.45 → 0.90 | 20.00 → 17.00 | 0.70 → 0.70 | 3.00 → 17.00 | 1.00 → 1.00 |
| Lo-fi | 4.50 → 2.50 | 0.57 → 0.94 | 10.50 → 7.00 | 1.30 → 2.00 | 13.00 → 19.00 | 1.00 → 1.00 |
| Jazz | 5.00 → 4.12 | 0.56 → 0.72 | 17.00 → 18.00 | 0.55 → 0.55 | 3.00 → 11.00 | 1.00 → 1.00 |
| Afrobeats | 4.00 → 3.25 | 0.51 → 0.42 | 15.00 → 12.00 | 0.32 → 0.32 | 3.00 → 17.00 | 1.00 → 1.00 |
| Reggaeton | 3.50 → 3.25 | 0.62 → 0.57 | 13.00 → 12.00 | 0.60 → 0.60 | 3.00 → 17.00 | 1.00 → 1.00 |
| Rock | 4.50 → 4.50 | 0.63 → 0.68 | 14.50 → 14.00 | 0.60 → 0.62 | 3.00 → 15.00 | 1.00 → 1.00 |
| Ambient | 1.75 → 0.62 | 2.28 → 4.26 | 9.00 → 1.00 | 7.44 → 14.03 | 8.00 → 6.00 | 0.00 → 1.00 |
| Funk | 5.00 → 3.50 | 0.28 → 0.24 | 17.00 → 12.00 | 0.18 → 0.18 | 3.00 → 3.00 | 1.00 → 1.00 |
| Disco | 5.00 → 3.50 | 0.51 → 0.60 | 18.00 → 19.00 | 0.50 → 0.50 | 3.00 → 19.00 | 0.38 → 1.00 |
| Country | 4.75 → 3.75 | 0.66 → 0.82 | 16.00 → 14.50 | 0.85 → 0.85 | 3.00 → 6.00 | 1.00 → 1.00 |
| Gospel | 4.50 → 2.50 | 0.73 → 0.80 | 17.00 → 14.50 | 1.25 → 1.25 | 3.00 → 9.00 | 1.00 → 1.00 |
| Classical | 8.00 → 5.25 | 0.47 → 0.45 | 15.00 → 15.00 | 0.46 → 0.46 | 3.00 → 20.00 | 0.00 → 1.00 |
| Blues | 5.50 → 4.00 | 0.50 → 0.70 | 18.00 → 15.00 | 0.75 → 0.75 | 3.00 → 5.00 | 1.00 → 1.00 |
| Dubstep | 3.00 → 1.88 | 0.70 → 0.75 | 15.00 → 12.00 | 0.45 → 0.45 | 3.00 → 5.00 | 1.00 → 1.00 |
| Trance | 8.00 → 8.00 | 0.39 → 0.45 | 20.00 → 17.00 | 0.23 → 0.23 | 3.00 → 16.00 | 0.00 → 0.00 |
| EBK - Dark NorCal Piano | 2.75 → 2.75 | 0.44 → 0.44 | 9.00 → 0.00 | 0.25 → 0.25 | 20.00 → 8.00 | 1.00 → 1.00 |
| LA - Modern West Coast | 3.25 → 3.25 | 0.42 → 0.42 | 19.50 → 19.00 | 0.38 → 3.59 | 20.00 → 8.00 | 1.00 → 1.00 |
| Classic G-Funk | 2.00 → 3.00 | 0.91 → 0.44 | 16.00 → 10.00 | 7.78 → 7.78 | 20.00 → 9.00 | 1.00 → 1.00 |

All after MIDI valid: **True**. Exact complete-score source matches: **0**. Nearest-quarter-grid complete-score source matches: **0**. Distinct selected source MIDI hashes rechecked: **61**, unchanged: **True**.

86 generated examples have at least one contextual listening review cue in the JSON. These cues flag counter overlap, unusually wide bass, repeated complete bars, large lead leaps, semitone pair overlap or a strict-scale violation; they are not a usability failure count. Review the arrangement and isolated roles with appropriate instruments, including cadence/loop seam, rhythmic pocket, motif recognition, vocal space and instrument register. A note starting in a gap can still overlap the following lead phrase.

The paired listening pack, when requested, contains 20 matched controlled examples per model with generated MIDI and all original role/chord/settings JSON. Use identical sounds and levels for before/after. Do not count the paired files as additional independent generations. Public comparison reports omit source paths and reusable source sequences; private evidence must remain private.

<a id="document-genre-installed-comparison-1-0-1-md"></a>

## GENRE-INSTALLED-COMPARISON-1.0.1.md

### Matched before/after MIDI output comparison

Snapshot: corrected composition engine **aeae3c62**, frozen 17 November 2026. The 1.0.1 filename identifies this musical audit; the advisory-only scale feature in product 1.1.0 does not change this engine or these generated settings. Source evidence is separate from final plugin/UI/host acceptance.

Compared 1080 same-model/family/seed pairs from 1080 before and 1080 after actual MIDI files. Controlled examples use the same A minor, 120 BPM, normal feel and complexity 0.5 settings.

These are structural measurements and listening review cues. A metric increasing or decreasing is not automatically an improvement. No authenticity or pleasantness score is calculated; no audio was heard by this tool.

| Model | Lead attacks/4p before→after | Lead gate before→after | Bass span before→after | Chord gate before→after | Degree sequences before→after | Counter gap before→after |
|---|---|---|---|---|---|---|
| Melodic Rap | 3.50 → 3.50 | 0.83 → 0.83 | 7.00 → 7.00 | 0.75 → 0.75 | 17.00 → 17.00 | 1.00 → 1.00 |
| Trap | 3.00 → 3.00 | 0.52 → 0.52 | 12.00 → 12.00 | 1.10 → 1.10 | 6.00 → 6.00 | 1.00 → 1.00 |
| R&B | 2.50 → 2.50 | 0.95 → 0.95 | 12.00 → 10.00 | 3.72 → 3.72 | 13.00 → 19.00 | 1.00 → 1.00 |
| Drill | 2.50 → 2.50 | 0.46 → 0.46 | 12.00 → 12.00 | 0.70 → 0.70 | 6.00 → 6.00 | 1.00 → 1.00 |
| Bay Area | 2.75 → 2.75 | 0.40 → 0.40 | 12.00 → 12.00 | 0.42 → 0.42 | 5.00 → 5.00 | 1.00 → 1.00 |
| Dark Latin Guitar | 3.75 → 3.75 | 0.80 → 0.80 | 15.00 → 15.00 | 0.75 → 0.75 | 12.00 → 12.00 | 1.00 → 1.00 |
| Pop | 3.50 → 3.50 | 0.90 → 0.90 | 12.00 → 10.50 | 1.70 → 1.70 | 12.00 → 18.00 | 1.00 → 1.00 |
| House | 3.50 → 3.50 | 0.50 → 0.50 | 16.00 → 16.00 | 0.36 → 0.36 | 17.00 → 17.00 | 1.00 → 1.00 |
| Techno | 6.00 → 6.00 | 0.28 → 0.28 | 0.00 → 0.00 | 0.22 → 0.22 | 3.00 → 3.00 | 1.00 → 1.00 |
| Drum & Bass | 3.25 → 3.25 | 0.90 → 0.90 | 17.00 → 17.00 | 0.70 → 0.70 | 17.00 → 17.00 | 1.00 → 1.00 |
| Lo-fi | 2.50 → 2.50 | 0.94 → 0.94 | 7.00 → 7.00 | 2.00 → 2.00 | 12.00 → 19.00 | 1.00 → 1.00 |
| Jazz | 4.12 → 4.12 | 0.72 → 0.72 | 18.00 → 18.00 | 0.55 → 0.55 | 11.00 → 11.00 | 1.00 → 1.00 |
| Afrobeats | 3.25 → 3.25 | 0.42 → 0.42 | 15.00 → 12.00 | 0.32 → 0.32 | 10.00 → 17.00 | 1.00 → 1.00 |
| Reggaeton | 3.25 → 3.25 | 0.57 → 0.57 | 12.00 → 12.00 | 0.60 → 0.60 | 17.00 → 17.00 | 1.00 → 1.00 |
| Rock | 4.50 → 4.50 | 0.68 → 0.68 | 14.00 → 14.00 | 0.62 → 0.62 | 15.00 → 15.00 | 1.00 → 1.00 |
| Ambient | 0.62 → 0.62 | 4.26 → 4.26 | 1.00 → 1.00 | 14.03 → 14.03 | 6.00 → 6.00 | 1.00 → 1.00 |
| Funk | 3.50 → 3.50 | 0.24 → 0.24 | 12.00 → 12.00 | 0.18 → 0.18 | 3.00 → 3.00 | 1.00 → 1.00 |
| Disco | 3.50 → 3.50 | 0.60 → 0.60 | 19.00 → 19.00 | 0.50 → 0.50 | 13.00 → 19.00 | 1.00 → 1.00 |
| Country | 3.75 → 3.75 | 0.82 → 0.82 | 14.50 → 14.50 | 0.85 → 0.85 | 6.00 → 6.00 | 1.00 → 1.00 |
| Gospel | 2.50 → 2.50 | 0.80 → 0.80 | 14.50 → 14.50 | 1.25 → 1.25 | 9.00 → 9.00 | 1.00 → 1.00 |
| Classical | 5.25 → 5.25 | 0.45 → 0.45 | 15.00 → 15.00 | 0.46 → 0.46 | 20.00 → 20.00 | 1.00 → 1.00 |
| Blues | 4.00 → 4.00 | 0.70 → 0.70 | 14.00 → 15.00 | 0.75 → 0.75 | 5.00 → 5.00 | 1.00 → 1.00 |
| Dubstep | 1.88 → 1.88 | 0.75 → 0.75 | 12.00 → 12.00 | 0.45 → 0.45 | 5.00 → 5.00 | 1.00 → 1.00 |
| Trance | 8.00 → 8.00 | 0.45 → 0.45 | 17.00 → 17.00 | 0.23 → 0.23 | 16.00 → 16.00 | 0.00 → 0.00 |
| EBK - Dark NorCal Piano | 2.75 → 2.75 | 0.44 → 0.44 | 0.00 → 0.00 | 0.25 → 0.25 | 8.00 → 8.00 | 1.00 → 1.00 |
| LA - Modern West Coast | 3.25 → 3.25 | 0.42 → 0.42 | 19.00 → 19.00 | 3.59 → 3.59 | 8.00 → 8.00 | 1.00 → 1.00 |
| Classic G-Funk | 3.00 → 3.00 | 0.44 → 0.44 | 10.00 → 10.00 | 7.78 → 7.78 | 9.00 → 9.00 | 1.00 → 1.00 |

All after MIDI valid: **True**. Exact complete-score source matches: **0**. Nearest-quarter-grid complete-score source matches: **0**. Distinct selected source MIDI hashes rechecked: **61**, unchanged: **True**.

86 generated examples have at least one contextual listening review cue in the JSON. These cues flag counter overlap, unusually wide bass, repeated complete bars, large lead leaps, semitone pair overlap or a strict-scale violation; they are not a usability failure count. Review the arrangement and isolated roles with appropriate instruments, including cadence/loop seam, rhythmic pocket, motif recognition, vocal space and instrument register. A note starting in a gap can still overlap the following lead phrase.

The paired listening pack, when requested, contains 20 matched controlled examples per model with generated MIDI and all original role/chord/settings JSON. Use identical sounds and levels for before/after. Do not count the paired files as additional independent generations. Public comparison reports omit source paths and reusable source sequences; private evidence must remain private.

<a id="document-genre-cadence-comparison-1-0-1-md"></a>

## GENRE-CADENCE-COMPARISON-1.0.1.md

### Actual generated cadence-frequency comparison

Snapshot: corrected composition engine **aeae3c62**, frozen 17 November 2026. The 1.0.1 filename identifies this musical audit; the advisory-only scale feature in product 1.1.0 does not change this engine or these generated settings. Source evidence is separate from final plugin/UI/host acceptance.

Terminal pair is the last two generated harmonic regions in the complete eight-host-bar controlled arrangement. Degrees stored zero-based; Markdown displays degree numbers 1–7 without imposing chord quality. Every model uses the same 20 seeds, strict A natural minor, 120 BPM, normal feel, complexity .5, humanization 0.

Counts describe a bounded procedural output distribution. Equal frequencies can occur by chance; narrowing or widening is not an authenticity/quality score. No audio was heard.

| Model | Original baseline: terminal degree pair counts | Installed 1.0.0 snapshot: terminal pair counts | Revised snapshot: terminal pair counts | Previous → revised most common whole-sequence count |
|---|---|---|---|---|
| Melodic Rap | 3-7: 8/20, 7-4: 7/20, 6-5: 5/20 | 1-1: 5/20, 1-6: 2/20, 3-2: 1/20, 1-4: 1/20, 6-4: 1/20, 3-4: 1/20, 2-2: 1/20, 6-6: 1/20, 7-1: 1/20, 6-1: 1/20, 4-1: 1/20, 3-1: 1/20, 4-7: 1/20, 2-1: 1/20, 6-5: 1/20 | 1-1: 5/20, 1-6: 2/20, 3-2: 1/20, 1-4: 1/20, 6-4: 1/20, 3-4: 1/20, 2-2: 1/20, 6-6: 1/20, 7-1: 1/20, 6-1: 1/20, 4-1: 1/20, 3-1: 1/20, 4-7: 1/20, 2-1: 1/20, 6-5: 1/20 | 2/20 → 2/20 |
| Trap | 1-5: 7/20, 1-7: 7/20, 6-7: 5/20, 6-5: 1/20 | 1-1: 10/20, 1-4: 4/20, 1-6: 3/20, 1-5: 1/20, 1-2: 1/20, 1-7: 1/20 | 1-1: 10/20, 1-4: 4/20, 1-6: 3/20, 1-5: 1/20, 1-2: 1/20, 1-7: 1/20 | 10/20 → 10/20 |
| R&B | 2-5: 12/20, 5-1: 5/20, 2-1: 2/20, 5-5: 1/20 | 2-5: 13/20, 4-5: 4/20, 2-1: 3/20 | 5-1: 5/20, 2-5: 2/20, 4-5: 2/20, 6-6: 2/20, 1-4: 1/20, 3-6: 1/20, 4-1: 1/20, 4-7: 1/20, 1-5: 1/20, 6-2: 1/20, 2-3: 1/20, 6-3: 1/20, 3-1: 1/20 | 4/20 → 2/20 |
| Drill | 2-7: 7/20, 2-1: 6/20, 1-2: 5/20, 1-1: 1/20, 1-7: 1/20 | 1-1: 11/20, 1-4: 4/20, 1-5: 2/20, 1-6: 1/20, 1-2: 1/20, 1-7: 1/20 | 1-1: 11/20, 1-4: 4/20, 1-5: 2/20, 1-6: 1/20, 1-2: 1/20, 1-7: 1/20 | 11/20 → 11/20 |
| Bay Area | 1-7: 8/20, 4-1: 7/20, 4-5: 5/20 | 1-1: 8/20, 1-4: 7/20, 1-5: 3/20, 1-6: 1/20, 1-7: 1/20 | 1-1: 8/20, 1-4: 7/20, 1-5: 3/20, 1-6: 1/20, 1-7: 1/20 | 8/20 → 8/20 |
| Dark Latin Guitar | 6-5: 8/20, 4-5: 7/20, 7-5: 5/20 | 2-5: 13/20, 4-5: 4/20, 2-1: 3/20 | 6-5: 11/20, 1-4: 1/20, 5-6: 1/20, 1-5: 1/20, 7-6: 1/20, 2-5: 1/20, 7-1: 1/20, 3-1: 1/20, 1-1: 1/20, 4-5: 1/20 | 3/20 → 8/20 |
| Pop | 1-5: 5/20, 6-4: 5/20, 1-4: 5/20, 4-5: 3/20, 6-5: 2/20 | 2-5: 13/20, 4-5: 4/20, 2-1: 3/20 | 5-1: 5/20, 4-5: 4/20, 1-4: 2/20, 4-1: 2/20, 1-1: 2/20, 5-6: 1/20, 6-6: 1/20, 1-5: 1/20, 6-3: 1/20, 6-4: 1/20 | 5/20 → 2/20 |
| House | 4-5: 10/20, 1-1: 6/20, 1-5: 4/20 | 1-1: 6/20, 1-4: 2/20, 1-6: 2/20, 4-1: 2/20, 2-1: 1/20, 6-4: 1/20, 2-2: 1/20, 5-5: 1/20, 7-1: 1/20, 6-1: 1/20, 4-7: 1/20, 6-5: 1/20 | 1-1: 6/20, 1-4: 2/20, 1-6: 2/20, 4-1: 2/20, 2-1: 1/20, 6-4: 1/20, 2-2: 1/20, 5-5: 1/20, 7-1: 1/20, 6-1: 1/20, 4-7: 1/20, 6-5: 1/20 | 2/20 → 2/20 |
| Techno | 1-1: 8/20, 7-1: 7/20, 4-1: 5/20 | 1-1: 16/20, 1-4: 3/20, 1-7: 1/20 | 1-1: 16/20, 1-4: 3/20, 1-7: 1/20 | 16/20 → 16/20 |
| Drum & Bass | 4-7: 8/20, 4-6: 7/20, 6-5: 5/20 | 1-1: 5/20, 4-1: 4/20, 6-6: 2/20, 1-5: 1/20, 7-3: 1/20, 4-5: 1/20, 2-4: 1/20, 1-6: 1/20, 7-1: 1/20, 6-1: 1/20, 1-7: 1/20, 4-7: 1/20 | 1-1: 5/20, 4-1: 4/20, 6-6: 2/20, 1-5: 1/20, 7-3: 1/20, 4-5: 1/20, 2-4: 1/20, 1-6: 1/20, 7-1: 1/20, 6-1: 1/20, 1-7: 1/20, 4-7: 1/20 | 3/20 → 3/20 |
| Lo-fi | 1-6: 7/20, 5-1: 5/20, 1-5: 3/20, 2-5: 2/20, 2-6: 1/20, 5-5: 1/20, 5-6: 1/20 | 2-5: 13/20, 4-5: 4/20, 2-1: 3/20 | 2-5: 3/20, 5-1: 3/20, 6-6: 2/20, 1-4: 1/20, 5-2: 1/20, 5-3: 1/20, 1-6: 1/20, 4-7: 1/20, 1-5: 1/20, 6-2: 1/20, 2-2: 1/20, 6-3: 1/20, 2-1: 1/20, 4-5: 1/20, 1-1: 1/20 | 4/20 → 2/20 |
| Jazz | 2-5: 12/20, 1-6: 8/20 | 5-1: 16/20, 4-1: 4/20 | 5-1: 16/20, 4-1: 4/20 | 4/20 → 4/20 |
| Afrobeats | 4-5: 12/20, 1-5: 8/20 | 2-5: 13/20, 4-5: 4/20, 2-1: 3/20 | 1-1: 6/20, 4-1: 3/20, 1-4: 3/20, 6-1: 2/20, 6-4: 1/20, 1-5: 1/20, 5-5: 1/20, 1-6: 1/20, 4-6: 1/20, 5-4: 1/20 | 4/20 → 2/20 |
| Reggaeton | 6-7: 8/20, 1-5: 7/20, 4-5: 5/20 | 1-1: 6/20, 4-3: 1/20, 1-5: 1/20, 7-4: 1/20, 4-5: 1/20, 3-4: 1/20, 1-6: 1/20, 6-6: 1/20, 7-1: 1/20, 6-1: 1/20, 1-7: 1/20, 5-1: 1/20, 4-1: 1/20, 5-7: 1/20, 7-6: 1/20 | 1-1: 6/20, 4-3: 1/20, 1-5: 1/20, 7-4: 1/20, 4-5: 1/20, 3-4: 1/20, 1-6: 1/20, 6-6: 1/20, 7-1: 1/20, 6-1: 1/20, 1-7: 1/20, 5-1: 1/20, 4-1: 1/20, 5-7: 1/20, 7-6: 1/20 | 3/20 → 3/20 |
| Rock | 5-1: 8/20, 4-5: 7/20, 4-1: 5/20 | 1-1: 6/20, 4-1: 3/20, 1-4: 3/20, 5-5: 2/20, 6-4: 1/20, 1-5: 1/20, 7-1: 1/20, 6-1: 1/20, 1-6: 1/20, 4-7: 1/20 | 1-1: 6/20, 4-1: 3/20, 1-4: 3/20, 5-5: 2/20, 6-4: 1/20, 1-5: 1/20, 7-1: 1/20, 6-1: 1/20, 1-6: 1/20, 4-7: 1/20 | 2/20 → 2/20 |
| Ambient | 4-4: 8/20, 1-6: 7/20, 4-1: 3/20, 1-1: 1/20, 1-4: 1/20 | 1-1: 10/20, 1-4: 6/20, 1-6: 1/20, 1-5: 1/20, 1-3: 1/20, 1-7: 1/20 | 1-1: 10/20, 1-4: 6/20, 1-6: 1/20, 1-5: 1/20, 1-3: 1/20, 1-7: 1/20 | 10/20 → 10/20 |
| Funk | 4-1: 8/20, 1-1: 7/20, 1-5: 5/20 | 1-1: 13/20, 1-4: 6/20, 1-7: 1/20 | 1-1: 13/20, 1-4: 6/20, 1-7: 1/20 | 13/20 → 13/20 |
| Disco | 2-5: 13/20, 5-1: 7/20 | 2-5: 13/20, 4-5: 4/20, 2-1: 3/20 | 5-1: 4/20, 2-5: 3/20, 1-4: 1/20, 5-2: 1/20, 5-6: 1/20, 5-3: 1/20, 6-6: 1/20, 4-1: 1/20, 4-7: 1/20, 1-5: 1/20, 6-2: 1/20, 2-2: 1/20, 6-3: 1/20, 2-1: 1/20, 4-5: 1/20 | 4/20 → 2/20 |
| Country | 4-5: 12/20, 5-1: 8/20 | 5-1: 16/20, 4-1: 4/20 | 5-1: 16/20, 4-1: 4/20 | 6/20 → 6/20 |
| Gospel | 1-5: 8/20, 5-1: 7/20, 4-5: 5/20 | 5-1: 10/20, 4-1: 10/20 | 5-1: 10/20, 4-1: 10/20 | 4/20 → 4/20 |
| Classical | 5-1: 8/20, 4-5: 7/20, 2-5: 5/20 | 5-1: 16/20, 4-1: 4/20 | 5-1: 16/20, 4-1: 4/20 | 1/20 → 1/20 |
| Blues | 4-5: 8/20, 4-1: 7/20, 1-5: 5/20 | 5-1: 14/20, 1-1: 3/20, 5-4: 2/20, 1-4: 1/20 | 5-1: 14/20, 1-1: 3/20, 5-4: 2/20, 1-4: 1/20 | 13/20 → 13/20 |
| Dubstep | 6-1: 8/20, 1-1: 7/20, 7-1: 5/20 | 1-1: 13/20, 1-4: 4/20, 1-6: 1/20, 1-5: 1/20, 1-7: 1/20 | 1-1: 13/20, 1-4: 4/20, 1-6: 1/20, 1-5: 1/20, 1-7: 1/20 | 13/20 → 13/20 |
| Trance | 4-7: 8/20, 1-5: 7/20, 6-5: 5/20 | 1-1: 6/20, 1-7: 2/20, 4-3: 1/20, 1-6: 1/20, 7-4: 1/20, 4-6: 1/20, 3-4: 1/20, 6-6: 1/20, 7-1: 1/20, 6-1: 1/20, 5-1: 1/20, 4-1: 1/20, 4-7: 1/20, 7-6: 1/20 | 1-1: 6/20, 1-7: 2/20, 4-3: 1/20, 1-6: 1/20, 7-4: 1/20, 4-6: 1/20, 3-4: 1/20, 6-6: 1/20, 7-1: 1/20, 6-1: 1/20, 5-1: 1/20, 4-1: 1/20, 4-7: 1/20, 7-6: 1/20 | 2/20 → 2/20 |
| EBK - Dark NorCal Piano | 5-4: 2/20, 4-1: 2/20, 5-5: 1/20, 6-5: 1/20, 4-7: 1/20, 1-1: 1/20, 1-4: 1/20, 7-7: 1/20, 4-4: 1/20, 5-1: 1/20, 3-1: 1/20, 2-7: 1/20, 1-3: 1/20, 5-7: 1/20, 2-1: 1/20, 4-5: 1/20, 1-2: 1/20, 4-6: 1/20 | 1-1: 12/20, 1-5: 4/20, 1-6: 2/20, 1-4: 1/20, 6-1: 1/20 | 1-1: 12/20, 1-5: 4/20, 1-6: 2/20, 1-4: 1/20, 6-1: 1/20 | 6/20 → 6/20 |
| LA - Modern West Coast | 4-1: 3/20, 1-5: 2/20, 6-4: 2/20, 1-4: 2/20, 7-5: 1/20, 1-1: 1/20, 7-7: 1/20, 2-4: 1/20, 6-1: 1/20, 4-6: 1/20, 7-6: 1/20, 5-3: 1/20, 3-7: 1/20, 4-4: 1/20, 1-2: 1/20 | 4-1: 12/20, 1-4: 4/20, 1-3: 1/20, 4-4: 1/20, 2-1: 1/20, 6-1: 1/20 | 4-1: 12/20, 1-4: 4/20, 1-3: 1/20, 4-4: 1/20, 2-1: 1/20, 6-1: 1/20 | 12/20 → 12/20 |
| Classic G-Funk | 4-1: 3/20, 4-5: 3/20, 5-3: 2/20, 1-7: 1/20, 4-2: 1/20, 6-1: 1/20, 4-7: 1/20, 1-6: 1/20, 3-4: 1/20, 1-3: 1/20, 6-4: 1/20, 6-7: 1/20, 7-5: 1/20, 7-1: 1/20, 1-4: 1/20 | 1-7: 8/20, 1-4: 4/20, 4-1: 3/20, 4-7: 3/20, 7-7: 1/20, 4-5: 1/20 | 1-7: 8/20, 1-4: 4/20, 4-1: 3/20, 4-7: 3/20, 7-7: 1/20, 4-5: 1/20 | 7/20 → 7/20 |

The complete JSON preserves whole-sequence frequency tables and exact generated snapshot hashes; it does not publish original-reference events. Check repeated cycles as musical excerpts, not automatically as defects. Jazz/gospel/classical functional resolution and vamp-driven genres require different expectations. All degree labels remain constrained by the selected strict scale. Actual MIDI export validity is independently checked by the corpus analyzer.

These outputs are generated evidence; the installed 1.0.0 binary and its source/backup remain distinct from this revised engine snapshot. No host, listening or production acceptance is inferred.

<a id="document-genre-blues-context-1-0-1-md"></a>

## GENRE-BLUES-CONTEXT-1.0.1.md

### Actual Blues and context verification

Snapshot: corrected composition engine **aeae3c62**, frozen 17 November 2026. The 1.0.1 filename identifies this musical audit; the advisory-only scale feature in product 1.1.0 does not change this engine or these generated settings. Source evidence is separate from final plugin/UI/host acceptance.

Genre accuracy, musical quality, then variety. These are measured structural properties, never an authenticity score.

Bass third attack in each four-pulse block is measured relative to the active scale-degree chord root. Count every exported example; do not infer the walking sixth from source code alone.

| Family | Previous scale-valid sixths retained | Revised scale-valid sixths retained | Revised strict bass outside scale |
|---|---:|---:|---:|
| controlled | 0/44 | 43/44 | 0 |
| varied | 0/71 | 68/71 | 0 |

The active factory profile can intentionally alter walking intervals. A separate 60-file actual-MIDI diagnostic disables library interval influence (20 seeds each in strict C major, strict A minor and C major Strict Off): every scale-valid major-sixth candidate is retained, all strict output remains in scale, and all MIDI passes metadata/length/channel/note validation. These 60 diagnostic files are additional fixtures, not part of the 1,080-example corpus.
Blues context uses C major, Strict Off: all 11 exported harmonic regions contain root, major third, fifth and minor seventh. This is an eight-bar blues-inspired excerpt, not a 12-bar-form claim.

Author-selected listening contexts are illustrative, not universal genre rules. Exact serialized BPM and generated feel timing are supplied to audio. User-selected plugin scales are not automatically changed.

| Model | BPM | Key root (C=0) | Scale | Feel | Strict | Actual MIDI valid |
|---|---:|---:|---|---|---|---|
| Melodic Rap | 92 | 6 | Minor Natural (Aeolian) | Normal | True | True |
| Trap | 140 | 1 | Minor Natural (Aeolian) | HalfTime | True | True |
| R&B | 82 | 9 | Minor Natural (Aeolian) | Normal | True | True |
| Drill | 142 | 2 | Minor Natural (Aeolian) | HalfTime | True | True |
| Bay Area | 100 | 9 | Minor Natural (Aeolian) | Normal | True | True |
| Dark Latin Guitar | 94 | 9 | Phrygian | Normal | True | True |
| Pop | 106 | 0 | Major (Ionian) | Normal | True | True |
| House | 124 | 9 | Minor Natural (Aeolian) | Normal | True | True |
| Techno | 132 | 9 | Minor Natural (Aeolian) | Normal | True | True |
| Drum & Bass | 174 | 2 | Minor Natural (Aeolian) | Normal | True | True |
| Lo-fi | 78 | 2 | Minor Natural (Aeolian) | Normal | True | True |
| Jazz | 112 | 2 | Dorian | Normal | True | True |
| Afrobeats | 105 | 0 | Major (Ionian) | Normal | True | True |
| Reggaeton | 94 | 9 | Minor Natural (Aeolian) | Normal | True | True |
| Rock | 110 | 9 | Minor Natural (Aeolian) | Normal | True | True |
| Ambient | 72 | 0 | Major (Ionian) | Normal | True | True |
| Funk | 104 | 9 | Dorian | Normal | True | True |
| Disco | 116 | 0 | Major (Ionian) | Normal | True | True |
| Country | 100 | 0 | Major (Ionian) | Normal | True | True |
| Gospel | 84 | 0 | Major (Ionian) | Normal | True | True |
| Classical | 100 | 0 | Major (Ionian) | Normal | True | True |
| Blues | 92 | 0 | Major (Ionian) | Normal | False | True |
| Dubstep | 140 | 5 | Minor Natural (Aeolian) | HalfTime | True | True |
| Trance | 136 | 9 | Minor Natural (Aeolian) | Normal | True | True |
| EBK - Dark NorCal Piano | 90 | 1 | Minor Natural (Aeolian) | Normal | True | True |
| LA - Modern West Coast | 100 | 4 | Minor Natural (Aeolian) | Normal | True | True |
| Classic G-Funk | 94 | 4 | Minor Natural (Aeolian) | Normal | True | True |

All strict context MIDI, retained roles (including the disabled legacy layer) and harmony pitches were checked against the selected scale, including Dorian and Phrygian. Audio rendering and human listening are separate. No listening or authenticity pass is claimed.

<a id="document-genre-listening-status-md"></a>

## GENRE-LISTENING-STATUS.md

### Genre listening preparation and status

**Human listening acceptance is pending for all 27 models.** The assistant could not hear the rendered files. Valid MIDI, distinct sequences and unclipped audio do not establish a genre match or artistic quality.

The private review material now contains 88 actual installed-instrument WAVs: 27 authored-context previews from corrected engine aeae3c62, 54 historical controlled before/after WAVs frozen at 995dd679, and seven separate user-owned West Coast references. All new audio independently passed stereo 48 kHz 24-bit PCM format, finite/non-silent/clipping and exact-tempo-duration checks. Earlier audio and original reference/source files retain their hashes.

The new previews use exact serialized BPM, feel and role events. They are separate context compositions, not a third matched side of the historical A/B. The source/audition folder names retain context-1.0.1 because the 1.1.0 adviser does not change composition generation. The review page includes a concise scope/listening question per genre, the existing primary-source links, exact settings, separate notes for new contexts and historical pairs, and JSON export with score/MIDI/audio identities. Local-link and isolated-script interaction checks passed; no acoustic hearing or browser visual pass is inferred from those checks.

Jazz/Country/Blues use an explicitly labeled synthesized plucked-string bass approximation. Synthesized piano/keys are not sampled acoustic grand/Rhodes recordings. There are no added drums/vocals, performed guitar articulation, receiving-instrument 808 glide, production distortion or finished ambient texture. Reference compositions differ in key/tempo/role scope and must not be treated as paired stems.

The owner can audition the pack with suitable instruments and production context, record the exact example/role/bar/time and state what works or needs revision. Repeated motifs, harmonic language, pocket, bass support, phrase trajectory, loop seam and vocal space need audible judgments. Scope is the documented interpretation of a broad genre, not an entire scene or tradition. Private paths, owned reference MIDI, licensed presets and raw role snapshots remain outside public distribution.

<a id="document-west-coast-references-md"></a>

## WEST-COAST-REFERENCES.md

### Ghost Note: supplied West Coast MIDI reference analysis

Seven user-selected files were read as Standard MIDI, with SHA-256 hashes taken before and after analysis. All seven remained unchanged. All are valid Type 1 files at 96 ticks per quarter note, with 4/4 metadata, a 32-beat/eight-bar musical length, one populated pitched track on MIDI channel 1 and no channel-10 percussion. The parser found no unmatched/unterminated notes or other warnings. No file contains an explicit instrument-program selection. Track names are template hints, not proof of a required instrument.

The EBK C-sharp-minor and D-minor files are **different compositions**, not transposed duplicates. None of the seven files is an exact transposed duplicate after comparing every pitch, onset, gate, velocity and channel relative to its named tonic. Related LA examples share harmonic vocabulary but use different rhythms, registers, voicings and decorations; seven examples cannot establish complete genre probabilities.

#### Measurement method

An exact-tick onset count would misread strummed chords as rapid single-note melodies. Therefore the report separately clusters note attacks occurring within **1/12 beat** of a group's first note. This captures the supplied 1–7 tick chord spreads while preserving longer intentional rolls. Sustained pitch sets are also inspected between events; a chord may sound after its notes have entered at different times. The private JSON preserves both exact events and interpreted measurements. `reference-aggregate.json` contains distributions only, without a reusable source note sequence.

#### 1. Tempo and meter

| Reference | Embedded tempo | Meter | Length |
|---|---:|---|---:|
| EBK C-sharp minor | 89.999955 BPM | 4/4 | 32 beats |
| EBK D minor | 91.999988 BPM | 4/4 | 32 beats |
| Bouncy WC | 100 BPM | 4/4 | 32 beats |
| Easy LA original | 89.999955 BPM | 4/4 | 32 beats |
| Easy LA V2 | 100 BPM | 4/4 | 32 beats |
| Easy LA V3 | 100 BPM | 4/4 | 32 beats |
| Go 2 G-Funk | 89.999955 BPM | 4/4 | 32 beats |

The D-minor file's embedded 92 BPM differs from its filename's 85–90 BPM description. Neither filenames nor these examples establish mandatory tempo limits; host tempo and musical feel remain separate plugin controls.

#### 2. Key and scale estimates

The six EBK/LA files use pitches compatible with the natural-minor key named in their filenames. Limited pitch collections also fit other modes or relative major scales, so pitch membership alone does not prove a tonic. The observed minor chord shapes and repeated centers corroborate the stated minor interpretation. There are no trustworthy labeled key-signature meta events on which to base a stronger claim.

The EBK C-sharp reference uses tonic-relative classes **0, 2, 3, 7, 10**; its D-minor counterpart uses **0, 2, 3, 5, 7**. Neither demonstrates out-of-scale chromatic passing notes. Harmonic-minor/chromatic EBK tension is therefore a requested, theory-led extension rather than a measured property of these two files.

G-Funk uses E-natural-minor material plus one D-sharp in a final diminished turnaround. Both D-natural and D-sharp occur, so the whole file is not simply one unchanging harmonic-minor scale. Natural minor covers **98.767% of duration-weighted note material**. A scale-locked generator must use a compatible turnaround or omit the outside-scale leading tone; it must not silently violate the selected scale.

#### 3. Note distribution and register

| Reference | Notes | Clustered musical attacks | MIDI range | Maximum concurrent notes |
|---|---:|---:|---|---:|
| EBK C-sharp minor | 132 | 40 | 44–63 | 5 |
| EBK D minor | 32 | 32 | 74–81 | 2, from legato overlap |
| Bouncy WC | 76 | 28 | 61–69 | 3 |
| Easy LA original | 48 | 16 | 59–76 | 5 |
| Easy LA V2 | 44 | 36, including a slower rolled entry | 57–79 | 8 |
| Easy LA V3 | 46 | 10 | 45–74 | 8 |
| Go 2 G-Funk | 25 | 5 | 52–71 | 5 |

EBK demonstrates a low, compact chord riff and a contrasting high, narrow melodic line. LA contains both clipped compact stabs and spacious sustained electric-piano-style writing. G-Funk's supplied example is a sustained harmonic bed; it does not itself demonstrate a separate lead or moving bassline.

#### 4. Intervals

After grouping chord strums, EBK C-sharp's upper attack voice primarily holds or moves by a fourth/fifth, with occasional falling fifths. EBK D-minor's actual monophonic contour favors descending whole steps: ten -2-semitone movements, with smaller numbers of descending semitones/thirds and upward fourth/fifth resets. This supports repeated descending phrases with controlled resets, rather than a random walk.

Bouncy WC's top attack voice is exceptionally restrained: **12 repeated notes, eight +1 and seven -1 semitone movements**. Easy LA V3's principal attack voice also holds or moves mostly by one/two semitones. The G-Funk attack voice moves between sustained chord-top notes; its small sample is insufficient to infer a lead-solo interval model. Exact-tick interval histograms from strummed chord notes should not be treated as independent melodic leaps.

#### 5. Chord structures, inversions and Roman-numeral interpretation

These are functional interpretations of observed pitch sets in the stated minor key. Enharmonic/rootless/symmetric sets can have more than one defensible chord name.

- **EBK C-sharp minor:** clipped **i(add9)** and i shapes contrast with **v minor**. Lower-register close-position thirds/fourths, octave/root doubling and a ninth provide darkness without random chromatic material. Recurrent adjacent voicing gaps include 3, 4 and 5 semitones, with a 2-semitone upper color.
- **EBK D minor:** a high single melodic line; it does **not** encode enough simultaneous harmony to infer a unique chord progression. Inventing a progression from its filename would overstate the evidence.
- **Bouncy WC:** **i → iv** vocabulary with a tonic-pedal **sus4** pitch set between them. The suspension can also be heard as iv(sus2), depending on the bass/harmonic interpretation. Chords remain within an eight-semitone window and the top line resolves by a semitone. Common voicing gaps are 3/4, 5/3 and 5/2 semitones.
- **Easy LA original:** an **iv(add9) / tonic-bass** color leads to **i(add9) / fifth-bass**, with related voicing shapes, short initial harmony and long response sustain. The initial four-class set can also receive a suspended/rootless interpretation. Functional **iv ↔ i** is supported; a unique nomenclature for every inversion is not.
- **Easy LA V2:** the same **i(add9) ↔ iv(add9)** family is presented as a descending rolled upper entry, then held lower chord tones. This is arrangement variation, not proof of a wholly different harmonic style.
- **Easy LA V3:** **v7 → iv9 → VImaj7**, often with the bass doubled an octave below. The first v7 has an upper neighbor decoration while the underlying chord sustains. Long common tones and stepwise upper motion give continuity.
- **G-Funk:** **iv9 ↔ i9**, with smooth minor-ninth stacks and a final fully diminished pitch set **D-sharp/F-sharp/A/C over F-sharp**. In E minor this supports a **vii°7 inversion** turnaround; the symmetric diminished-seventh set also permits other root spellings. Four full eight-beat chord regions become a six-beat final tonic plus a two-beat turnaround. Frequent adjacent voice gaps are 3/4/3/4 semitones.

These few progressions should establish weighted harmonic tendencies, not a fixed menu of copied loops. Further scale-aware motion, substitutions and voice-leading rules are implementation choices. Major, dominant-seventh, altered or chromatic options absent from a particular reference should be identified as theory-led variations and constrained by the user's selected scale.

#### 6. Note lengths

| Reference | Mean gate, beats | Median gate, beats | Observed behavior |
|---|---:|---:|---|
| EBK C-sharp minor | 0.399 | 0.479 | Quarter-/half-beat stabs, slightly shorter upper strum notes |
| EBK D minor | 1.292 | 1.313 | One-beat-spaced melody attacks with overlapping legato gates |
| Bouncy WC | 0.303 | 0.250 | Mostly quarter-beat stabs, selected half-beat gates |
| Easy LA original | 3.311 | 1.500 | 1.5-beat first chord, long 6.5-beat responses and later fills |
| Easy LA V2 | 4.466 | 5.865 | Long upper notes plus rolled/shorter lower entries |
| Easy LA V3 | 4.056 | 4.714 | Seven-, six- and two-beat harmonic regions with decorations |
| Go 2 G-Funk | 6.387 | 7.979 | Predominantly eight-beat held chords, final two-beat turnaround |

Thus a G-Funk model that merely reuses EBK's short gates would contradict the supplied examples.

#### 7. Rhythm, placement and syncopation

EBK C-sharp's clustered attacks favor sixteenth positions **0, 6, 10, 13, 14, 15** in a four-beat bar: strong entry, a 1.5-beat syncopated stab and short late-bar pickups/turnarounds. EBK D-minor enters on each integer beat. Bouncy WC favors **0, 6, 10, 14**: downbeat, 1.5, 2.5 and 3.5-beat pockets, with omissions between phrases.

Easy LA original also uses downbeat/1.5-beat exchanges, but with held notes and a late half-beat fill near a four-bar boundary. V2 contains a purposeful descending roll spanning about half a beat, not a randomly shifted groove. V3 and G-Funk use sparse, longer harmonic entries. The examples show small chord spreads and deliberate rolls, **not enough evidence for a measured swing ratio**. Swing is a requested optional design control, not a statistic claimed from these files.

#### 8. Repetition and motif structure

Comparing exact onset/pitch/gate segments while ignoring velocity: EBK C-sharp and Bouncy WC each repeat the same two-bar structure four times. EBK D-minor and Easy LA original each repeat a four-bar structure twice. Easy LA V2/V3 and G-Funk have no two identical full four-bar event segments because of different voicings, gates, entries or final decorations, while recurring harmonic families remain evident. This supports motif reuse with phrase-level changes and occasional turnaround behavior.

#### 9. Melodic range

The D-minor EBK line spans only seven semitones high in the keyboard; the C-sharp riff spans 19 semitones lower down. Bouncy WC's complete chord material spans eight semitones. Wider Easy LA ranges include bass/voicing movement; they are not evidence that every lead should leap across that full register. G-Funk's 19-semitone range describes chord voicings, not a separate lead melody.

#### 10. Countermelody and bass relationships

No supplied file has separately labeled melody/countermelody/bass tracks. The EBK D-minor melody is in a different key and is not established as a paired counterline to the C-sharp file. Easy LA V3 has possible upper-neighbor decorations over sustained harmony and low octave doubles, but assigning those notes to an independent countermelody/bass engine is an interpretation.

Therefore separate counterlines, gap-answer rules, melodic bass phrases and five compatible layers must be **new theory-led composition logic**, informed by register/groove/harmony evidence. The report does not claim to have learned true paired part relationships or bassline training labels from these seven files.

#### 11. Velocity

| Reference | Velocity range | Mean |
|---|---|---:|
| EBK C-sharp minor | 87–113 | 99.82 |
| EBK D minor | 90–95 | 92.88 |
| Bouncy WC | 103 exactly | 103.00 |
| Easy LA original | 54–66 | 60.96 |
| Easy LA V2 | 52–79 | 71.18 |
| Easy LA V3 | 25–71 | 59.46 |
| Go 2 G-Funk | 54–66 | 60.80 |

The clipped EBK riff has more forceful attacks than the softer long EP-style references. Bouncy WC contains no velocity humanization. V2's rolled entry increases velocity toward lower chord tones; V3's bass doubles are quieter than several upper voices. These support role-/phrase-based accents rather than independent random velocity jitter.

#### 12. Phrase length, variation and implementation consequences

All references cover eight host bars. EBK should combine low repeated two-bar harmonic riffs with sparse high answering/descending motifs, without assuming all EBK uses the same progression or register. Modern LA can use tight syncopated stabs, restrained top-note motion and space for vocals. A separate Classic G-Funk option should favor slower harmonic changes, warm extended voicings, common tones and sustained phrases; any added synth lead or funky moving bass is an explicitly composed genre convention, not falsely attributed to this chord-only reference.

Fresh generation should use these aggregate tendencies with scale-aware construction, weighted degree movement, inversions, bounded tension and independent phrase decisions. Seed variety must affect harmony and arrangement as well as velocities. Strict scale selection remains authoritative. The supplied sample supports useful constraints, not an objective claim of the world's best MIDI or complete genre authenticity.

#### Files and reproducibility

`analyze_references.py` reads the seven exact user paths and writes reports only in this work folder. `reference-analysis-private.json` contains file hashes, metadata, measured features, pitch-set candidates, source-event details and before/after integrity results; keep it private. `reference-aggregate.json` is the sequence-free implementation input. Source MIDI is never changed or copied into the plugin. No external MIDI downloads were needed for this seven-file audit.


---

### Supplemental owned-library MIDI evidence

After the seven primary examples, thirteen additional files were selected from the user's existing accepted-material catalog and their **actual MIDI bytes were read again**. This is a bounded supplemental sample, not an Internet training set. Files attributed by their names/folders to IIInfinite and Cymatics already exist in the user's library; producer attribution and genre labels are not independently certified. Filename hints selected candidates, while observed note content establishes the measured roles and musical behavior below.

All thirteen files remain byte-for-byte unchanged, all parsed without warnings, and all use pitched channel 1 with 96 PPQ and 4/4 metadata. None is an exact transposition-normalized duplicate of another file in this supplemental set. No source MIDI or reusable source event sequence is included in the generator's aggregate resource. The private JSON contains exact paths, hashes and evidence; do not distribute its source-event tables publicly.

#### Actual sample

| File | Content role | Embedded BPM | Notes / beats | MIDI range | Median gate, beats |
|---|---|---:|---|---|---:|
| Cymatics Oracle West Coast MIDI 5, F-sharp Min | Polyphonic harmony | Not present | 29 / 16 | 42–76 | 3.729 |
| Gfunk Synth Lead (2), A minor, IIInfinite | Lead | 102.000051 | 12 / 15.979 | 62–74 | 0.240 |
| Dr Dre Synth Lead, A minor | Lead | 89.999955 | 17 / 16 | 79–93 | 0.562 |
| Gfunk Lead, D-sharp minor | Lead | 100 | 40 / 32 | 63–87 | 0.333 |
| Smooth Synth Lead, D minor (1) | Lead | 96.999953 | 42 / 32 | 62–77 | 0.562 |
| Gfunk Chords, D minor | Polyphonic harmony | 97.999984 | 12 / 16 | 43–67 | 6.990 |
| Smooth Rhodes, F-sharp minor | Polyphonic harmony | 89.999955 | 46 / 32 | 50–69 | 1.995 |
| Smooth Rhodes, G-sharp minor | Polyphonic harmony | 89.999955 | 42 / 32 | 49–66 | 3.469 |
| Gfunk Bassline, A minor | Bass | 101.000069 | 54 / 32 | 43–53 | 0.250 |
| Gfunk Bassline, D-sharp minor | Bass | 100 | 42 / 32 | 39–47 | 0.302 |
| Larry June Bassline, D-sharp minor | Bass | 91.999988 | 21 / 16 | 25–34 | 0.333 |
| Too Short Bassline, D minor | Bass | 82.000036 | 22 / 16 | 38–43 | 0.271 |
| West Coast Bassline, A minor | Bass | 89.999955 | 30 / 32 | 45–53 | 0.542 |

Tempo metadata sometimes differs from filename ranges: the Too Short example is approximately 82 BPM, and the A-minor G-Funk bass is approximately 101 BPM. The Oracle file has no tempo event, so its BPM is unknown; no tempo is inferred from its filename.

#### Harmony and Roman numerals

- **Oracle F-sharp:** the named “Min” file uses relative pitch classes **0,1,3,5,7,8,10**, compatible with F-sharp Phrygian, including G-natural rather than G-sharp. Audible pitch-set candidates give **i → bII → bVII minor** vocabulary, with wide register contrasts and low support. This supports an optional borrowed/Phrygian color, not forcing bII into a strict natural-minor setting. It is a broader West Coast example and is not proof of an EBK-specific convention.
- **G-Funk Chords in D:** a low single-note entry supports later upper **v7 → i7** voicings. Long seven-beat gates and octave displacement show that all notes of one harmonic gesture need not begin together.
- **Rhodes F-sharp:** observed **i9**, **bVII(add9)** and **bVImaj9** colors, with six-beat held harmony and two-beat responses. Close upper neighbors resolve while lower common tones remain. Functional alternatives for rootless/suspended sets remain possible.
- **Rhodes G-sharp:** **v7 → bVImaj9 → iv7 → bVII7** families, long voicings and upper-note semitone/whole-step adjustments. Diatonic minor can support a dominant-seventh chord on bVII without implying an outside-scale V7.

The seven primary examples plus these four harmony samples show more than one progression family and chord-change rate. A flexible engine should generalize scale-aware degree movement, extensions, common-tone voice leading and substitutions, rather than store these source progressions as fixed loops.

#### Leads and phrasing

The four actual lead files confirm the register and sparse phrase behavior missing from the primary G-Funk chord example. They span 12–42 notes over four or eight bars, with repeated short gestures, longer held arrivals and predominant one-/two-semitone movement. The A-minor Gfunk Synth Lead uses only minor-pentatonic classes **0,3,5,7,10**. The D-sharp lead emphasizes descending whole-step figures and short repeated entries, with occasional octave displacement.

The smooth D-minor lead contains two E-flat notes outside natural minor: a small controlled chromatic color rather than general chromatic saturation. Such color must be optional under a compatible scale or when strict scale is disabled. These sources do not justify outside-scale notes when the user explicitly selects a strict formula.

The source note attacks and gates demonstrate legato overlap, but **none of the twenty analyzed files contains pitch-bend events, controller changes or aftertouch**. Instrument-specific portamento, pitch-bend range and receiving-synth glide settings are therefore not measured evidence. A glide-aware MIDI feature would be a new optional design with routing/bend-channel constraints, not something claimed to have been learned from these files.

#### Bass movement and groove

The five bass files are low-register, predominantly monophonic material with short/medium gates, repeated root-area notes and frequent one-/two-semitone connections. Their global ranges are five to eleven semitones except for octave placement between files; these are practical register bounds, not a requirement to jump octaves continuously. Root/fourth/fifth relationships and minor-scale connective notes dominate. The A-minor West Coast line places 24 of its 30 notes on the tonic or fourth, with a few fifth/flat-sixth approaches.

Attacks include offbeats and sixteenth pickups. The two “Gfunk Bassline” examples have different pockets; pooling them into one rigid bass grid would lose meaningful variety. Dynamics also differ: one bass file is fixed at 127, another at 92, and the Larry June file at 72, whereas others vary. None supports a claim that every authentic bassline must contain velocity jitter.

These are **independent bass and lead examples**, not stems documented as paired with the primary chord files. New bass-to-chord and counterline coordination must still be composed using the current harmonic timeline and phrase gaps. No true labeled counter-melody pairs were found or claimed in this bounded sample.

#### Evidence boundaries and generation use

Primary seven-file findings remain the basis of EBK/Modern LA/Classic G-Funk separation. The thirteen supplemental files provide actual lead, bass, additional harmonic and Phrygian-color evidence. They are not independent proof of a whole historical genre, a universal progression probability, or subjective production quality.

`additional-local/reference-analysis-private.json` records every actual file read and its before/after hash. `additional-local/selection-provenance.json` links each to the prior content-classified catalog. `additional-local/reference-aggregate.json` contains separate lead, bass and harmony distributions without copying event sequences. `analyze_additional.py` reproduces this audit from the same existing library. No new MIDI was downloaded, and no source file was modified.

<a id="document-artwork-md"></a>

## ARTWORK.md

### Original Ghost Note artwork

The current Ghost Note interface uses an original transparent manuscript-paper ghost with flowing dark musical ribbons and restrained copper edges. It is embedded from `assets/ghost-note-art.png` and displayed as a compact header emblem, keeping the working interface small.

The image was generated specifically for this project with the built-in image generation tool. No reference image, existing character, artist recording, stock illustration or commercial asset was supplied. Its full prompt, creation method, dimensions, alpha check and SHA-256 are recorded in **GHOST-NOTE-ARTWORK.md**.

The public-facing name and publisher credit were selected by the owner: **Ghost Note**. The generated image contains no lettering; interface typography supplies the exact credit. Artwork provenance does not establish trademark exclusivity. Existing products use similar Ghost Note/Ghostnote names, so the development record makes no name-availability clearance claim.

An earlier abstract ink-and-copper sculpture asset remains in private development history. The new ghost illustration is the current visual identity.

<a id="document-genre-architecture-audit-md"></a>

## GENRE-ARCHITECTURE-AUDIT.md

### Composition engine audit before legacy refinements

This is a source audit, completed before changing the 24 legacy algorithms. The frozen 0.3 source and 960 generated baseline MIDI/role-JSON examples are retained separately. Source inspection establishes implementation facts, not listening judgments.

#### Shared systems and weaknesses

All 27 styles use the selected one of 38 scale formulas; Strict Scale must remain authoritative. All 24 legacy styles select one of three four-degree lists, repeat it, and use the same nearest-inversion voicer. A library profile can reweight only degrees already in those three lists. Harmony ordinarily changes every four musical pulses; Techno/Ambient/Dubstep double this. This is a narrow progression menu, not a flexible functional grammar.

The legacy melody builder chooses a rhythm-grid variant, draws a broadly rising/falling contour, anchors strong notes to chord tones, and repeats it per four pulses. Only Techno, Trance, Ambient and Classical override contour. Country/Blues apply a pentatonic filter. Identical register bounds 65–87 and a common velocity arc serve nearly all models. The common counter builder uses two late replies, always in 77–96, with occasional swing/ambient/classical timing exceptions. Bass has four shared behaviors; Jazz/Blues walking movement repeats the same 0/4/7/9 pitch offsets rather than targeting the next chord. Chord articulation is more differentiated than melody: broken, held, stabs, strum, comp, Alberti and rolling. The optional fifth layer is shared upper harmony. These are meaningful existing elements to preserve, but on their own insufficient evidence of genre identity.

#### Per-model audit and refinement targets

| ID / model | Correct existing ingredients | Limitation observed in code | Required refinement direction |
|---|---|---|---|
| 0 Melodic Rap | vocal gaps; broken accompaniment | generic scalar contour; three loops | singable two/four-bar hook, held arrival, sparse relative-chord grammar |
| 1 Trap | short high hooks; octave bass | melody moves too continuously; harmony changes automatically | repeated neighbor cells, rests, tonic pedal and prepared minor-color departures |
| 2 R&B | seventh/ninth eligibility; held voicings | no expressive phrase grammar; same counter | delayed entry, chord-tone enclosure and held arrivals, functional substitutions |
| 3 Drill | short stabs; displaced bass | no regional scope; shared random contour | dark descending ostinato, sparse answers, tonic/neighbor tension, no invented glide messages |
| 4 Bay Area | offbeat stabs and sparse rhythm | common scalar melody/harmony | repeated-note bounce, restrained motion, tonic/plagal vamps |
| 5 Dark Latin Guitar | nylon sound; selectable broken/strum rhythm | broad name lacks defined scope; generic lead | retain dark guitar scope, idiomatic arpeggio/stepwise answer and cadence |
| 6 Pop | strums; steady bass | same generic contour and three cycles | antecedent/consequent hook, repeated apex, final arrival, functional variation |
| 7 House | offbeat chord pulses | generic scalar melody and bass octave alternation | short repeated-note/chord-tone hook, interlocked bass, retained offbeat stabs |
| 8 Techno | tonic-vamp list; clocked short ostinato | random chord-cycle variants and no gradual phrase logic | long pedal, small pitch cell, sparse evolving upper response |
| 9 Drum & Bass | syncopated bass; chord comp | common lead and slow-genre feel defaults | break-compatible bass holds/pickups, four/eight-bar harmonic/motif shape |
| 10 Lo-fi | swung comp; seventh/ninth chords | busy common contour/counter; formulaic harmony | understated repeated fragments, soft delayed replies and smooth turnaround |
| 11 Jazz | swing, extended harmony, walking option | walking ignores next root; fixed progression menu | guide-tone phrases, ii–V resolution tendencies, next-root approaches |
| 12 Afrobeats | short syncopated grid and root/fifth bass | generic lead/counter are not an interlock; not a genre proof | two-bar plucked cycle, complementary answers, distinct bass pocket; do not import Afrobeat horns or amapiano log bass |
| 13 Reggaeton | tresillo-adjacent rhythm; clipped strums | lead/counter generic; tresillo alone conflates styles | stable dembow-compatible call/response and restrained supportive bass |
| 14 Rock | guitar strums, root/fifth bass | scalar lead, no riff grammar | repeated root/fifth riff, phrase-end fill and functional/power-chord support |
| 15 Ambient | slow held chords; low density | still starts a melody and counter every four pulses | long rests and notes, open/common-tone pad, sparse independent upper entry |
| 16 Funk | short sixteenth comp and octave bass | no pitch/rhythm motif interlock | repeated muted cells, chord-tone/bass responses and tonic vamps |
| 17 Disco | octave bass, offbeat comp | generic melody and automatic chord loop | regular octave groove, singable repeated hook, functional lift |
| 18 Country | pentatonic filter, strums, root/fifth | pentatonic filter not instrumental phrasing | repeated pickup/answer, third/sixth shape, restrained cadence fill |
| 19 Gospel | richer voicings; plagal candidate | common lead and occasional arbitrary loops | plagal and dominant preparation, expressive pickup/arrival |
| 20 Classical | Alberti, balanced contour override | no real antecedent/consequent or cadence control | scalar sequence, four/eight-bar sentence and prepared dominant/tonic |
| 21 Blues | swing, pentatonic filtering | compressed four-cycle grammar; literal 12-bar not available in bars control | explicitly blues-inspired loop, riff/reply and I/IV/V function; do not claim full 12-bar form |
| 22 Dubstep | long anchor; sparse lead | octave bass is generic, not bass-led phrase | two-bar low cell with timed gaps/pickup and sparse answer; timbral wobble is receiving synth's job |
| 23 Trance | rolling arpeggio; clocked repeated shape | common phrase/counter; three harmony loops | continuous chord-tone arp, longer hook, stable pulse bass and harmonic lift |
| 24 EBK | dedicated low piano/short-gate/add9 engine | excessively fast diverse random harmonic changes | two/four-bar recurring plan, tonic pedal, limited departure and prepared cadence |
| 25 Modern LA | dedicated clipped/rolled harmony, bounce controls | degree freedom can overpower reference-derived i/iv pocket | cyclic pocket, common-tone/plagal weight, phrase-level variation |
| 26 Classic G-Funk | long extensions, independent lead/bass | overly many new harmonic sequences still possible | stronger iv/i bed, six-plus-two ending option, smooth common tones |

The latter three use dedicated melody/counter/bass/chords/accent functions already implemented before this audit. Their completed work is retained. The major-seventh Roman-numeral regression fix is present in both legacy and West Coast label functions and has an explicit test.

#### Validation boundaries

Functional validity, bounded pitch, scale membership, determinism, no same-pitch overlap, source-sequence non-copying, motif recurrence and measured articulation can be tested automatically. Counts of distinct degree strings are diagnostic only and must not serve as an authenticity/quality pass threshold. At least twenty distinct review examples per model remain a coverage requirement. Human reference-versus-generated listening and real FL Studio routing/drag tests are separate acceptance work; none is claimed by this source audit.

<a id="document-genre-baseline-midi-audit-md"></a>

## GENRE-BASELINE-MIDI-AUDIT.md

### Actual MIDI output audit

Analyzed **1080 actual exported MIDI files**, with separate role and harmonic snapshots, against 20 read-only local West Coast sources.

Priority: genre accuracy, musical quality, then variety. The table screens musical structure; uniqueness, scale membership, tempo and labels cannot establish authenticity. No audio was rendered or heard in this analysis.

The controlled family holds A natural minor, 120 BPM, normal feel, complexity 0.5, humanization 0 and the same twenty seeds. The varied family changes root, major/minor, BPM, feel and complexity. All examples use the actual active embedded library profile or the plugin-equivalent overall fallback. Disabled Chord Layer notes are measured separately and excluded from the audible score.

| Model | Family | Actual valid | Exact / quarter-grid unique | Degree progressions | Melody attacks / 4 pulses | Median melody gate | Melody repeated intervals | Counter gap entries | Extended harmony |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Melodic Rap | controlled | 20/20 | 20 / 20 | 3 | 3.50 | 0.80 | 17% | 100% | 0% |
| Melodic Rap | varied | 20/20 | 20 / 20 | 7 | 3.88 | 0.78 | 18% | 100% | 50% |
| Trap | controlled | 20/20 | 20 / 20 | 13 | 4.50 | 0.56 | 23% | 100% | 0% |
| Trap | varied | 20/20 | 20 / 20 | 11 | 4.50 | 0.56 | 19% | 100% | 50% |
| R&B | controlled | 20/20 | 20 / 20 | 13 | 3.50 | 1.19 | 22% | 100% | 100% |
| R&B | varied | 20/20 | 20 / 20 | 13 | 3.50 | 1.19 | 25% | 100% | 100% |
| Drill | controlled | 20/20 | 20 / 20 | 9 | 3.50 | 0.48 | 23% | 100% | 0% |
| Drill | varied | 20/20 | 20 / 20 | 11 | 3.88 | 0.48 | 18% | 100% | 50% |
| Bay Area | controlled | 20/20 | 20 / 20 | 3 | 3.00 | 0.48 | 43% | 100% | 0% |
| Bay Area | varied | 20/20 | 20 / 20 | 7 | 3.00 | 0.48 | 35% | 100% | 50% |
| Dark Latin Guitar | controlled | 20/20 | 20 / 20 | 3 | 4.50 | 0.60 | 30% | 100% | 0% |
| Dark Latin Guitar | varied | 20/20 | 20 / 20 | 6 | 4.50 | 0.60 | 25% | 100% | 50% |
| Pop | controlled | 20/20 | 20 / 20 | 12 | 3.50 | 0.66 | 19% | 100% | 0% |
| Pop | varied | 20/20 | 20 / 20 | 12 | 3.88 | 0.66 | 20% | 100% | 50% |
| House | controlled | 20/20 | 20 / 20 | 9 | 5.00 | 0.33 | 22% | 50% | 0% |
| House | varied | 20/20 | 20 / 20 | 12 | 5.00 | 0.33 | 15% | 50% | 50% |
| Techno | controlled | 20/20 | 20 / 20 | 3 | 7.00 | 0.15 | 40% | 50% | 0% |
| Techno | varied | 20/20 | 20 / 20 | 4 | 7.00 | 0.15 | 34% | 50% | 50% |
| Drum & Bass | controlled | 20/20 | 20 / 20 | 3 | 5.00 | 0.45 | 27% | 100% | 0% |
| Drum & Bass | varied | 20/20 | 20 / 20 | 7 | 5.00 | 0.41 | 26% | 100% | 50% |
| Lo-fi | controlled | 20/20 | 20 / 20 | 13 | 4.50 | 0.57 | 26% | 100% | 100% |
| Lo-fi | varied | 20/20 | 20 / 20 | 14 | 4.50 | 0.57 | 23% | 100% | 100% |
| Jazz | controlled | 20/20 | 20 / 20 | 3 | 5.00 | 0.56 | 23% | 100% | 100% |
| Jazz | varied | 20/20 | 20 / 20 | 7 | 5.00 | 0.56 | 24% | 100% | 100% |
| Afrobeats | controlled | 20/20 | 20 / 20 | 3 | 4.00 | 0.51 | 26% | 100% | 0% |
| Afrobeats | varied | 20/20 | 20 / 20 | 6 | 4.44 | 0.51 | 27% | 100% | 50% |
| Reggaeton | controlled | 20/20 | 20 / 20 | 3 | 3.50 | 0.62 | 23% | 100% | 0% |
| Reggaeton | varied | 20/20 | 20 / 20 | 7 | 3.75 | 0.61 | 23% | 100% | 50% |
| Rock | controlled | 20/20 | 20 / 20 | 3 | 4.50 | 0.63 | 20% | 100% | 0% |
| Rock | varied | 20/20 | 20 / 20 | 7 | 4.50 | 0.63 | 17% | 100% | 50% |
| Ambient | controlled | 20/20 | 20 / 20 | 8 | 1.75 | 2.28 | 38% | 0% | 0% |
| Ambient | varied | 20/20 | 20 / 20 | 8 | 1.75 | 2.28 | 57% | 0% | 50% |
| Funk | controlled | 20/20 | 20 / 20 | 3 | 5.00 | 0.28 | 28% | 100% | 0% |
| Funk | varied | 20/20 | 20 / 20 | 7 | 5.00 | 0.28 | 26% | 100% | 50% |
| Disco | controlled | 20/20 | 20 / 20 | 3 | 5.00 | 0.51 | 31% | 38% | 0% |
| Disco | varied | 20/20 | 20 / 20 | 6 | 5.00 | 0.51 | 27% | 47% | 50% |
| Country | controlled | 20/20 | 20 / 20 | 3 | 4.75 | 0.66 | 7% | 100% | 0% |
| Country | varied | 20/20 | 20 / 20 | 7 | 5.00 | 0.66 | 7% | 100% | 50% |
| Gospel | controlled | 20/20 | 20 / 20 | 3 | 4.50 | 0.73 | 24% | 100% | 100% |
| Gospel | varied | 20/20 | 20 / 20 | 6 | 4.50 | 0.73 | 23% | 100% | 100% |
| Classical | controlled | 20/20 | 20 / 20 | 3 | 8.00 | 0.47 | 29% | 0% | 0% |
| Classical | varied | 20/20 | 20 / 20 | 7 | 8.00 | 0.47 | 23% | 0% | 50% |
| Blues | controlled | 20/20 | 20 / 20 | 3 | 5.50 | 0.50 | 9% | 100% | 0% |
| Blues | varied | 20/20 | 20 / 20 | 6 | 5.50 | 0.50 | 7% | 100% | 50% |
| Dubstep | controlled | 20/20 | 20 / 20 | 3 | 3.00 | 0.70 | 52% | 100% | 0% |
| Dubstep | varied | 20/20 | 20 / 20 | 5 | 3.00 | 0.70 | 45% | 100% | 50% |
| Trance | controlled | 20/20 | 20 / 20 | 3 | 8.00 | 0.39 | 13% | 0% | 0% |
| Trance | varied | 20/20 | 20 / 20 | 7 | 8.00 | 0.39 | 12% | 0% | 50% |
| EBK - Dark NorCal Piano | controlled | 20/20 | 20 / 20 | 20 | 2.75 | 0.44 | 27% | 100% | 0% |
| EBK - Dark NorCal Piano | varied | 20/20 | 20 / 20 | 20 | 2.88 | 0.46 | 23% | 100% | 0% |
| LA - Modern West Coast | controlled | 20/20 | 20 / 20 | 20 | 3.25 | 0.42 | 35% | 100% | 100% |
| LA - Modern West Coast | varied | 20/20 | 20 / 20 | 20 | 3.38 | 0.42 | 35% | 100% | 100% |
| Classic G-Funk | controlled | 20/20 | 20 / 20 | 20 | 2.00 | 0.91 | 38% | 100% | 100% |
| Classic G-Funk | varied | 20/20 | 20 / 20 | 20 | 2.00 | 0.91 | 31% | 100% | 100% |

Measurement definitions: chord attacks within 1/12 beat are clustered; melodic contour uses the highest attack note, not arbitrary strum note order. Gates/density are measured in musical pulses, accounting for feel. Quarter-grid uniqueness ignores transposition, velocity, channels and initial silence. Voice movement is symmetric nearest-pitch distance, not fixed labeled voices. Strong/long chord-tone membership is a screen, not a rule that passing notes are wrong. Semitone/unison overlap is reported without assuming all dissonance is a defect. Observed offbeat displacement is not a certified swing ratio.

Exact and nearest-quarter-grid complete-score comparisons detect no matches unless recorded in the JSON. They do not detect excerpt quotation, all possible transpositions/edits, or similarity to music outside the twenty references. Genre authenticity and pleasantness require listening with appropriate instruments and broader reference evidence.

The source-event lists and source paths remain in private records. Source MIDI files were opened read-only and their final SHA-256 hashes verified again. Generated example JSON and metrics permit reproducible role, rhythm, harmony and counterline analysis.

<a id="document-genre-before-after-comparison-md"></a>

## GENRE-BEFORE-AFTER-COMPARISON.md

### Matched before/after MIDI output comparison

> Frozen engine-source audit, 16 November 2026. Engine.cpp SHA-256: 995DD679A5B1D0904A023818394214A6032DE049E137DADDF5CC4103A2FED991. The factory catalog includes the style-12 weak-general-fallback quarantine. These measurements verify the recorded source snapshot, not final binary/installer/FL Studio behavior or producer listening.


Compared 1080 same-model/family/seed pairs from 1080 before and 1080 after actual MIDI files. Controlled examples use the same A minor, 120 BPM, normal feel and complexity 0.5 settings.

These are structural measurements and listening review cues. A metric increasing or decreasing is not automatically an improvement. No authenticity or pleasantness score is calculated; no audio was heard by this tool.

| Model | Lead attacks/4p before→after | Lead gate before→after | Bass span before→after | Chord gate before→after | Degree sequences before→after | Counter gap before→after |
|---|---|---|---|---|---|---|
| Melodic Rap | 3.50 → 3.50 | 0.80 → 0.83 | 13.00 → 7.00 | 0.75 → 0.75 | 3.00 → 17.00 | 1.00 → 1.00 |
| Trap | 4.50 → 3.00 | 0.56 → 0.52 | 19.00 → 12.00 | 1.10 → 1.10 | 13.00 → 6.00 | 1.00 → 1.00 |
| R&B | 3.50 → 2.50 | 1.19 → 0.95 | 12.00 → 12.00 | 3.72 → 3.72 | 13.00 → 13.00 | 1.00 → 1.00 |
| Drill | 3.50 → 2.50 | 0.48 → 0.46 | 17.00 → 12.00 | 0.70 → 0.70 | 9.00 → 6.00 | 1.00 → 1.00 |
| Bay Area | 3.00 → 2.75 | 0.48 → 0.40 | 14.00 → 12.00 | 0.42 → 0.42 | 3.00 → 5.00 | 1.00 → 1.00 |
| Dark Latin Guitar | 4.50 → 3.75 | 0.60 → 0.80 | 17.00 → 15.00 | 0.75 → 0.75 | 3.00 → 12.00 | 1.00 → 1.00 |
| Pop | 3.50 → 3.50 | 0.66 → 0.90 | 12.00 → 12.00 | 1.70 → 1.70 | 12.00 → 12.00 | 1.00 → 1.00 |
| House | 5.00 → 3.50 | 0.33 → 0.50 | 17.00 → 16.00 | 0.36 → 0.36 | 9.00 → 17.00 | 0.50 → 1.00 |
| Techno | 7.00 → 6.00 | 0.15 → 0.28 | 13.00 → 0.00 | 0.22 → 0.22 | 3.00 → 3.00 | 0.50 → 1.00 |
| Drum & Bass | 5.00 → 3.25 | 0.45 → 0.90 | 20.00 → 17.00 | 0.70 → 0.70 | 3.00 → 17.00 | 1.00 → 1.00 |
| Lo-fi | 4.50 → 2.50 | 0.57 → 0.94 | 10.50 → 7.00 | 1.30 → 2.00 | 13.00 → 12.00 | 1.00 → 1.00 |
| Jazz | 5.00 → 4.12 | 0.56 → 0.72 | 17.00 → 18.00 | 0.55 → 0.55 | 3.00 → 11.00 | 1.00 → 1.00 |
| Afrobeats | 4.00 → 3.25 | 0.51 → 0.42 | 15.00 → 15.00 | 0.32 → 0.32 | 3.00 → 10.00 | 1.00 → 1.00 |
| Reggaeton | 3.50 → 3.25 | 0.62 → 0.57 | 13.00 → 12.00 | 0.60 → 0.60 | 3.00 → 17.00 | 1.00 → 1.00 |
| Rock | 4.50 → 4.50 | 0.63 → 0.68 | 14.50 → 14.00 | 0.60 → 0.62 | 3.00 → 15.00 | 1.00 → 1.00 |
| Ambient | 1.75 → 0.62 | 2.28 → 4.26 | 9.00 → 1.00 | 7.44 → 14.03 | 8.00 → 6.00 | 0.00 → 1.00 |
| Funk | 5.00 → 3.50 | 0.28 → 0.24 | 17.00 → 12.00 | 0.18 → 0.18 | 3.00 → 3.00 | 1.00 → 1.00 |
| Disco | 5.00 → 3.50 | 0.51 → 0.60 | 18.00 → 19.00 | 0.50 → 0.50 | 3.00 → 13.00 | 0.38 → 1.00 |
| Country | 4.75 → 3.75 | 0.66 → 0.82 | 16.00 → 14.50 | 0.85 → 0.85 | 3.00 → 6.00 | 1.00 → 1.00 |
| Gospel | 4.50 → 2.50 | 0.73 → 0.80 | 17.00 → 14.50 | 1.25 → 1.25 | 3.00 → 9.00 | 1.00 → 1.00 |
| Classical | 8.00 → 5.25 | 0.47 → 0.45 | 15.00 → 15.00 | 0.46 → 0.46 | 3.00 → 20.00 | 0.00 → 1.00 |
| Blues | 5.50 → 4.00 | 0.50 → 0.70 | 18.00 → 14.00 | 0.75 → 0.75 | 3.00 → 5.00 | 1.00 → 1.00 |
| Dubstep | 3.00 → 1.88 | 0.70 → 0.75 | 15.00 → 12.00 | 0.45 → 0.45 | 3.00 → 5.00 | 1.00 → 1.00 |
| Trance | 8.00 → 8.00 | 0.39 → 0.45 | 20.00 → 17.00 | 0.23 → 0.23 | 3.00 → 16.00 | 0.00 → 0.00 |
| EBK - Dark NorCal Piano | 2.75 → 2.75 | 0.44 → 0.44 | 9.00 → 0.00 | 0.25 → 0.25 | 20.00 → 8.00 | 1.00 → 1.00 |
| LA - Modern West Coast | 3.25 → 3.25 | 0.42 → 0.42 | 19.50 → 19.00 | 0.38 → 3.59 | 20.00 → 8.00 | 1.00 → 1.00 |
| Classic G-Funk | 2.00 → 3.00 | 0.91 → 0.44 | 16.00 → 10.00 | 7.78 → 7.78 | 20.00 → 9.00 | 1.00 → 1.00 |

All after MIDI valid: **True**. Exact complete-score source matches: **0**. Nearest-quarter-grid complete-score source matches: **0**. Distinct selected source MIDI hashes rechecked: **61**, unchanged: **True**.

74 generated examples have at least one contextual listening review cue in the JSON. These cues flag counter overlap, unusually wide bass, repeated complete bars, large lead leaps, semitone pair overlap or a strict-scale violation; they are not a usability failure count. Review the arrangement and isolated roles with appropriate instruments, including cadence/loop seam, rhythmic pocket, motif recognition, vocal space and instrument register. A note starting in a gap can still overlap the following lead phrase.

The paired listening pack, when requested, contains 20 matched controlled examples per model with generated MIDI and all original role/chord/settings JSON. Use identical sounds and levels for before/after. Do not count the paired files as additional independent generations. Public comparison reports omit source paths and reusable source sequences; private evidence must remain private.

Actual generated seed-120001 progressions for all 27 models, with priority-model role measurements, are recorded in [GENRE-GENERATED-PROGRESSION-EXAMPLES.md](#document-genre-generated-progression-examples-md). These are generated demonstrations, not original-reference transcriptions or listening results.

<a id="document-genre-before-model-review-md"></a>

## GENRE-BEFORE-MODEL-REVIEW.md

### Per-model before audit: preserve, weakness, improvement

This matrix interprets **1,080 actually generated/exported MIDI files**: frozen 0.3 older 24 models and frozen pre-audit 0.4 West Coast three models, each with 20 varied and 20 controlled seeds. It is a symbolic composition audit. No audio was heard; no model earns an authenticity or subjective quality pass from this matrix. Research and subsequent listening must test the proposed changes.

Every model has 20/20 valid, transposition/velocity-independent quarter-grid-unique controlled scores. That result establishes a bounded structural variety check only. Seventeen older models nevertheless expose only three controlled harmonic sequences. Existing scale membership and nearest-voice motion are useful constraints, while every strong/long lead being a chord tone can also indicate over-constraint rather than musical sophistication.

| Model | Measured controlled evidence (median) | Existing useful behavior | Inaccuracy / weakness | Priority refinement target |
|---|---|---|---|---|
| Melodic Rap | 3.50 lead attacks/4p; 0.80p gate; 3 degree sequences; 100% gap replies | Repeated lead motifs and broken-chord support leave counterline gaps. | The same four-position motif and high chord-tone answer engine dominate; only three controlled harmonic sequences. | Develop a recurring vocal-like hook over longer phrase arcs; vary response register, rhythm and final cadence together. |
| Trap | 4.50 lead attacks/4p; 0.56p gate; 13 degree sequences; 100% gap replies | Short high lead gestures and single sparse chord attacks support a dark arrangement. | The controlled lead still averages 4.5 attacks/four pulses; generic replies and octave bass movement resemble Drill. No measured regional/timbral distinction. | Prefer longer harmonic pedals, restrained hook repetition and explicit sparse answering phrases; evaluate room for 808 and vocals with suitable sounds. |
| R&B | 3.50 lead attacks/4p; 1.19p gate; 13 degree sequences; 100% gap replies | Held extended harmony is present in every controlled sample; nearest-voice movement is smooth. | Chord complexity is mostly global richness; responses use the shared high register rather than expressive harmonic interaction. | Preserve sevenths/ninths and common tones; introduce phrase-aware suspensions, controlled anticipations and countermelody restraint. |
| Drill | 3.50 lead attacks/4p; 0.48p gate; 9 degree sequences; 100% gap replies | Clipped sparse harmony and a high repeated motif are implemented. | Trap and Drill share octave-bass motion and the general melody/counter mechanism. Fixed four-chord sequences do not encode regional Drill practice. | Keep sparse dark phrases but distinguish regional rhythm/phrase behavior in supported variants; avoid inventing a universal Drill formula. |
| Bay Area | 3.00 lead attacks/4p; 0.48p gate; 3 degree sequences; 100% gap replies | Sparse stabs and a higher repeated-note ratio than Melodic Rap produce an audible structural contrast. | Only three controlled progression families; counterlines follow the same general high chord-tone answer mechanism. | Develop compact rhythmic riffs, independently chosen phrase rests and low-register bass answers; retain existing sparse character. |
| Dark Latin Guitar | 4.50 lead attacks/4p; 0.60p gate; 3 degree sequences; 100% gap replies | Broken/strummed support, root/fifth bass and multiple guitar approaches exist. | The label covers a mood/instrument rather than one Latin tradition; default natural-minor chord loops alone do not demonstrate a regional Latin idiom. | Define the intended guitar idiom, preserve scale authority, and coordinate bass/strum/melodic accents and playable register. |
| Pop | 3.50 lead attacks/4p; 0.66p gate; 12 degree sequences; 100% gap replies | Functional four-chord families, strums and singable density provide useful pop priors. | Eight-bar looping has little verse/chorus or hook/answer hierarchy; seed uniqueness is not song development. | Build a stable hook with phrase endings and a contrasting response; preserve simple harmony and avoid gratuitous complexity. |
| House | 5.00 lead attacks/4p; 0.33p gate; 9 degree sequences; 50% gap replies | Offbeat short chord stabs and active octave bass distinguish the rhythmic skeleton. | The generic high counterline overlaps melody entry in many samples; broad House cannot identify deep/garage/tech-house behavior from this one pattern. | Keep the offbeat pocket, vary phrase-level chord/bass conversation and state substyle scope before extending the model. |
| Techno | 7.00 lead attacks/4p; 0.15p gate; 3 degree sequences; 50% gap replies | Seven short lead attacks/four pulses, repeated cells and two-bar harmonic regions create a persistent ostinato. | Cell ordering and common counterline remain fixed across a broad Techno label; global richness adds extensions at high complexity. | Maintain modal/pedal focus and introduce restrained evolving cell/rhythm variants rather than busy new counterpoints every bar. |
| Drum & Bass | 5.00 lead attacks/4p; 0.45p gate; 3 degree sequences; 100% gap replies | Broken-position lead/bass pulses and cycling harmony differ from four-on-floor models. | The broad label lacks liquid/jungle/dancefloor separation; no drums are exported, so breakbeat authenticity cannot be inferred from pitched MIDI. | Refine bass phrase length, melodic pads and offbeat answers around an explicit intended substyle and audition against a breakbeat context. |
| Lo-fi | 4.50 lead attacks/4p; 0.57p gate; 13 degree sequences; 100% gap replies | Extended harmony, ternary-position comping and relaxed gates are implemented. | Fixed swung positions and generic high replies do not produce the expressive timing or melodic restraint of a human performance. | Retain seventh/ninth voice leading, use coherent pocket displacement and quieter sparse phrase responses instead of independent jitter. |
| Jazz | 5.00 lead attacks/4p; 0.56p gate; 3 degree sequences; 100% gap replies | Extended voicings, comping and a walking-bass branch are real structural differences. | Bass walk values are repeatedly snapped to chord tones, limiting connective motion; only three controlled degree sequences and a shared lead formula. | Phrase guide tones and scale-compatible approaches deliberately; support clearer harmonic rhythm/turnaround behavior and audition bass continuity. |
| Afrobeats | 4.00 lead attacks/4p; 0.51p gate; 3 degree sequences; 100% gap replies | Short syncopated comping, root/fifth bass and spaced counter entries support interlocking parts. | The model uses the common melody/counter engine over only three controlled harmonic sequences. A path-hint corpus conflates Afrobeat/Afrobeats and cannot validate this identity. | Use researched contemporary Afrobeats interlocking hooks, repeated plucked gestures, call/response and vocal space; distinguish it from Afrobeat/Amapiano/Dancehall. |
| Reggaeton | 3.50 lead attacks/4p; 0.62p gate; 3 degree sequences; 100% gap replies | Tresillo-like positions, short strummed support and repeated harmonic loops exist. | The same broad four-chord and high-answer mechanisms do not establish dembow coordination; the plugin exports no percussion. | Preserve recurring syncopated hooks; coordinate melodic accents and bass rests against an explicit dembow context and test listening. |
| Rock | 4.50 lead attacks/4p; 0.63p gate; 3 degree sequences; 100% gap replies | Strums and root/fifth bass give a different articulation from held-pad styles. | Close keyboard-like voicings and shared melody mechanics do not establish guitar playability, band interaction or a chosen Rock substyle. | Refine register, riff/strum coordination, power/open voicing alternatives and phrase cadence without assuming every Rock arrangement is guitar-led. |
| Ambient | 1.75 lead attacks/4p; 2.28p gate; 8 degree sequences; 0% gap replies | Slow two-bar harmonic changes, held support and only 1.75 lead attacks/four pulses create space. | The counter is forcibly scheduled under the lead rather than entering gaps in every controlled sample. The general eight-bar grid and bass cycle remain conspicuous. | Allow genuinely absent/sustained counterparts, fewer harmonic changes and gradual common-tone evolution; check density by ear. |
| Funk | 5.00 lead attacks/4p; 0.28p gate; 3 degree sequences; 100% gap replies | Short syncopated chord gates and active octave bass establish a tight rhythmic surface. | The general melodic algorithm and fixed harmonic families limit the bass-led conversation; global richness alone supplies color. | Compose interlocking bass/riff/chord rests, purposeful sixteenth accents and short ghost-like notes without filling every gap. |
| Disco | 5.00 lead attacks/4p; 0.51p gate; 3 degree sequences; 38% gap replies | Offbeat stabs and continuous eighth-position octave bass are distinct from Funk. | Counter entry overlaps melody in most samples; three controlled harmonic sequences and fixed bass ordering can become mechanical. | Preserve the consistent dance pulse while developing bass octave/approach phrasing and longer chord/lead answers. |
| Country | 4.75 lead attacks/4p; 0.66p gate; 3 degree sequences; 100% gap replies | Strums, root/fifth support and pentatonic-like lead turns are present. | The general scale/harmony engine and high replies are not instrument-specific; controlled melodies have relatively frequent large leaps. | Keep simple functional harmony, shape idiomatic bounded phrases and coordinated bass/strum accents, and state modern/traditional scope. |
| Gospel | 4.50 lead attacks/4p; 0.73p gate; 3 degree sequences; 100% gap replies | Rich comped harmony, some plagal movement and swung positions are implemented. | Three controlled progression families and shared answers do not capture independent inner-voice/church keyboard movement. | Develop controlled passing diminished/suspended colors only when selected scale permits, and phrase-level plagal/dominant resolutions. |
| Classical | 8.00 lead attacks/4p; 0.47p gate; 3 degree sequences; 0% gap replies | A distinct Alberti support branch, eight-note lead pattern and balanced functional degree priors exist. | A repeated scale-cell over generic chord-tone melody is a narrow Classical texture; no voice independence or formal development is demonstrated. | State the intended tonal keyboard style, control voice-leading/contrary motion and phrase cadences, and reduce automatic high counterline doubling. |
| Blues | 5.50 lead attacks/4p; 0.50p gate; 3 degree sequences; 100% gap replies | Swung placement, tonic/subdominant vamps and pentatonic-shaped turns are implemented. | Strict natural minor/major cannot reproduce every blue note; repeated snapped walking shapes and three degree families do not establish twelve-bar form. | Use scale-compatible blue-note colors when selected, preserve strict mode, and provide purposeful call/response, turnaround and form-aware phrase endings. |
| Dubstep | 3.00 lead attacks/4p; 0.70p gate; 3 degree sequences; 100% gap replies | Two-bar harmonic pedals, sparse leads and clipped octave bass distinguish the model. | The same generic bass octave rule does not encode bass timbre/motion or distinguish classic/deep/brostep; no audio modulation is represented by MIDI notes. | Clarify substyle, compose coherent bass call/answer motifs and rests, and judge them with an appropriate receiving instrument. |
| Trance | 8.00 lead attacks/4p; 0.39p gate; 3 degree sequences; 0% gap replies | Continuous arpeggiation, repeated eight-note lead shapes and functional cycling harmony are present. | Lead and rolling support can remain simultaneously busy; generic replies overlap lead in every controlled sample. | Coordinate melodic/harmonic density, build phrase-level tension/release and preserve a memorable repeated hook over evolving inversions. |
| EBK - Dark NorCal Piano | 2.75 lead attacks/4p; 0.44p gate; 20 degree sequences; 100% gap replies | A separate West Coast engine creates compact low chord riffs and sparse descending/repeated lead gestures. | Compared with the one actual EBK lead source, generated controlled leads are shorter (.44 vs1.31 beat median) and slightly wider; this is a drift observation, not a universal genre rule. | Support both low clipped riffs and a contrasting high narrow legato/held answer interpretation; audition the phrase as a complete arrangement. |
| LA - Modern West Coast | 3.25 lead attacks/4p; 0.42p gate; 20 degree sequences; 100% gap replies | A separate model includes short syncopated stabs, restrained lead contour and extended voiced harmony. | The controlled chord sample median favors clipped gates despite actual LA sources also containing long EP beds; a compact lead plus high answer can over-constrain register. | Retain short/held arrangement alternatives and develop common-tone voicing plus understated top-line variations; choose variants coherently per idea. |
| Classic G-Funk | 2.00 lead attacks/4p; 0.91p gate; 20 degree sequences; 100% gap replies | Held two-bar extended harmony, common tones and restrained lead density separate it from EBK. | Actual four lead sources are denser/shorter/wider than generated leads; actual five bass sources are denser, narrower and shorter. Source counts are too small for universal limits. | Keep the long warm harmonic bed while refining lead short/held gesture contrast and compact moving bass phrases; instrument portamento is not inferred from legato MIDI. |

Common quality review: density, gate, register, melodic contour, repeated bar motifs, structural chord-tone support, nearest-pitch voicing continuity, phrase-ending notes, lead/counter gaps and pairwise semitone/unison overlaps are measured per file in the private evidence. Overlap and dissonance are reported as events, not automatically labeled errors. Counter gap entry alone is insufficient: a note may start in a gap and then collide with the next phrase. The combined export merges same-pitch overlaps, which can hide a role-level collision, so both the retained parts and exported MIDI are audited.

Evidence limits: exact and nearest-quarter-grid complete-score checks against 20 actual West Coast references detect zero matches in all 1,080 outputs. This is a bounded source-copy screen, not a plagiarism detector, excerpt-match guarantee or proof of musical originality. The separate owned-library sample adds 41 actual file reads across 16 unverified path hints; it does not certify any genre. All 61 distinct selected source MIDI files remain unchanged.

Genre priority is accuracy first, musical quality second, variety third. Fixes should preserve musical strengths, be tested at the same key/tempo/feel/settings, then be heard on appropriate instruments. Variation should affect coherent motifs, harmony and arrangement; random changes are not a substitute for a credible genre identity.

<a id="document-genre-generated-progression-examples-md"></a>

## GENRE-GENERATED-PROGRESSION-EXAMPLES.md

### Generated before/after progression examples

These are **actual generated controlled example 01**, seed **120001**, for all 27 models: A natural minor, strict scale, 120 BPM, normal feel, eight bars / 32 beats, complexity 0.5 and humanization 0. The paired-listening JSON retains separate roles and harmony snapshots. The baseline uses frozen v0.3 for the first 24 styles and the pre-refinement West Coast implementation for the last three. The after snapshot uses Engine.cpp SHA-256 **995DD679A5B1D0904A023818394214A6032DE049E137DADDF5CC4103A2FED991** and the final factory catalog quarantine.

The labels and parenthesized durations in beats below are read from generated harmony snapshots; they are not transcriptions of original reference MIDI. A repeated chord label can still use different inversions, gates, rhythms and role events. One seed illustrates behavior and cannot establish a style's full distribution or artistic quality. See GENRE-BEFORE-AFTER-COMPARISON.md for the twenty-seed matched distributions and GENRE-FINAL-540-MIDI-AUDIT.md for the separately generated final check. No audio was heard by this extraction.

| Model | Before generated progression (duration in beats) | After generated progression (duration in beats) |
|---|---|---|
| Melodic Rap | Am (4) → C (4) → G (4) → Dm (4) → Am (4) → C (4) → G (4) → Dm (4) | Am (4) → Am (4) → C (4) → Bdim (4) → Am (4) → Am (4) → C (4) → Bdim (4) |
| Trap | Am (4) → Am (4) → Am (4) → Em (4) → Am (4) → F (4) → Am (4) → Em (4) | Am (8) → Am (8) → Am (8) → Am (8) |
| R&B | Am7 (4) → Dm7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) → Fmaj7 (4) → Bm7b5 (4) → Em7 (4) | Am7 (4) → Am7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) → Am7 (4) → Bm7b5 (4) → Em7 (4) |
| Drill | Am (4) → Am (4) → Bdim (4) → Am (4) → Am (4) → Dm (4) → Bdim (4) → Am (4) | Am (8) → Am (8) → Am (8) → Am (8) |
| Bay Area | Am (4) → F (4) → Dm (4) → Am (4) → Am (4) → F (4) → Dm (4) → Am (4) | Am (4) → Am (4) → Am (4) → Am (4) → Am (4) → Am (4) → Am (4) → Am (4) |
| Dark Latin Guitar | Am (4) → F (4) → Dm (4) → Em (4) → Am (4) → F (4) → Dm (4) → Em (4) | Am (4) → Am (4) → Bdim (4) → Em (4) → Am (4) → Am (4) → Bdim (4) → Em (4) |
| Pop | F (4) → Dm (4) → Am (4) → Em (4) → F (4) → Em (4) → Am (4) → Em (4) | Am (4) → Am (4) → Bdim (4) → Em (4) → Am (4) → Am (4) → Bdim (4) → Em (4) |
| House | Bdim (4) → Em (4) → Am (4) → Am (4) → Bdim (4) → Em (4) → Am (4) → Am (4) | Am (4) → Am (4) → Bdim (4) → Am (4) → Am (4) → Am (4) → Bdim (4) → Am (4) |
| Techno | Am (8) → Am (8) → G (8) → Am (8) | Am (8) → Am (8) → Am (8) → Am (8) |
| Drum & Bass | Am (4) → G (4) → Dm (4) → F (4) → Am (4) → G (4) → Dm (4) → F (4) | Am (8) → Am (8) → Dm (8) → Am (8) |
| Lo-fi | Fmaj7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) → Fmaj7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) | Am7 (8) → Am7 (8) → Bm7b5 (8) → Em7 (8) |
| Jazz | Am7 (4) → Fmaj7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) → Fmaj7 (4) → Bm7b5 (4) → Em7 (4) | Am7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) → Am7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) |
| Afrobeats | Am (4) → Em (4) → Dm (4) → Em (4) → Am (4) → Em (4) → Dm (4) → Em (4) | Am (4) → Am (4) → Bdim (4) → Em (4) → Am (4) → Am (4) → Bdim (4) → Em (4) |
| Reggaeton | F (4) → Dm (4) → Am (4) → Em (4) → F (4) → Dm (4) → Am (4) → Em (4) | Am (4) → Am (4) → Dm (4) → C (4) → Am (4) → Am (4) → Dm (4) → C (4) |
| Rock | Am (4) → F (4) → Dm (4) → Em (4) → Am (4) → F (4) → Dm (4) → Em (4) | Am (4) → Am (4) → Dm (4) → Am (4) → Am (4) → Am (4) → Dm (4) → Am (4) |
| Ambient | Am (8) → Am (8) → Dm (8) → Dm (8) | Am (16) → Am (16) |
| Funk | Bdim (4) → Em (4) → Am (4) → Am (4) → Bdim (4) → Em (4) → Am (4) → Am (4) | Am (4) → Am (4) → Am (4) → Am (4) → Am (4) → Am (4) → Am (4) → Am (4) |
| Disco | F (4) → Bdim (4) → Em (4) → Am (4) → F (4) → Bdim (4) → Em (4) → Am (4) | Am7 (4) → Am7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) → Am7 (4) → Bm7b5 (4) → Em7 (4) |
| Country | Am (4) → Am (4) → Dm (4) → Em (4) → Am (4) → Am (4) → Dm (4) → Em (4) | Am (4) → Am (4) → Em (4) → Am (4) → Am (4) → Am (4) → Em (4) → Am (4) |
| Gospel | Fmaj7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) → Fmaj7 (4) → Bm7b5 (4) → Em7 (4) → Am7 (4) | Am7 (4) → Am7 (4) → Em7 (4) → Am7 (4) → Am7 (4) → Am7 (4) → Em7 (4) → Am7 (4) |
| Classical | Am (4) → C (4) → Dm (4) → Em (4) → Am (4) → C (4) → Dm (4) → Em (4) | Am (4) → Am (4) → Bdim (4) → Em (4) → Am (4) → F (4) → Em (4) → Am (4) |
| Blues | Am (4) → Am (4) → Dm (4) → Am (4) → Am (4) → Am (4) → Dm (4) → Am (4) | Am (4) → Dm (4) → Em (4) → Am (4) → Am (4) → Dm (4) → Em (4) → Am (4) |
| Dubstep | Am (8) → Dm (8) → Am (8) → Am (8) | Am (8) → Am (8) → Am (8) → Am (8) |
| Trance | F (4) → Dm (4) → Am (4) → Em (4) → F (4) → Dm (4) → Am (4) → Em (4) | Am (8) → Am (8) → Dm (8) → C (8) |
| EBK - Dark NorCal Piano | Em (8) → Dm (4) → Em (4) → Dm (4) → Em (4) → Am (2) → Em (4) → Em (2) | Am (8) → Am (4) → Em (4) → Am (8) → Am (4) → Em (4) |
| LA - Modern West Coast | Em7 (8) → Dm7 (4) → Em7 (4) → Dm(add9) (6) → Em7 (4) → Am7 (2) → Em7 (4) | Am(add9) (8) → Cmaj7 (8) → Am7 (8) → Cmaj7 (8) |
| Classic G-Funk | Dm7(add9) (8) → Dm7(add9) (8) → Em7(add11) (8) → Cmaj7(add9) (8) | Am7(add9) (8) → Dm7(add9) (8) → Am7(add9) (8) → Dm7(add9) (8) |

#### Priority-model generated role examples

These measurements use the same generated seed and retained separate role notes, rather than estimating roles from merged MIDI. Durations are unnormalized quarter-note beats. The counter attack count alone does not establish space or successful call and response.

| Model | Before generated roles | After generated roles |
|---|---|---|
| Trap | 28 lead attacks, lead median gate 0.72 beats, bass span 20 semitones, 12 counter attacks | 24 lead attacks, lead median gate 0.52 beats, bass span 12 semitones, 8 counter attacks |
| R&B | 24 lead attacks, lead median gate 1.19 beats, bass span 12 semitones, 8 counter attacks | 24 lead attacks, lead median gate 0.93 beats, bass span 12 semitones, 1 counter attacks |
| Drill | 32 lead attacks, lead median gate 0.48 beats, bass span 17 semitones, 8 counter attacks | 16 lead attacks, lead median gate 0.46 beats, bass span 12 semitones, 8 counter attacks |
| Lo-fi | 36 lead attacks, lead median gate 0.57 beats, bass span 10 semitones, 4 counter attacks | 20 lead attacks, lead median gate 0.94 beats, bass span 7 semitones, 4 counter attacks |
| Afrobeats | 36 lead attacks, lead median gate 0.58 beats, bass span 15 semitones, 8 counter attacks | 26 lead attacks, lead median gate 0.42 beats, bass span 15 semitones, 14 counter attacks |
| EBK - Dark NorCal Piano | 20 lead attacks, lead median gate 0.47 beats, bass span 7 semitones, 8 counter attacks | 20 lead attacks, lead median gate 0.47 beats, bass span 5 semitones, 8 counter attacks |
| LA - Modern West Coast | 16 lead attacks, lead median gate 0.47 beats, bass span 14 semitones, 8 counter attacks | 16 lead attacks, lead median gate 0.47 beats, bass span 9 semitones, 8 counter attacks |
| Classic G-Funk | 16 lead attacks, lead median gate 0.91 beats, bass span 11 semitones, 4 counter attacks | 24 lead attacks, lead median gate 0.44 beats, bass span 8 semitones, 4 counter attacks |

The matched examples require the same suitable receiving sounds and levels for producer review. Check the whole arrangement and isolated roles, loop seam/cadence, motif recognizability, vocal space, register, rhythmic pocket and bass/chord agreement. EBK, LA and G-Funk harmonic narrowing in some seeds is intentional bounded style conditioning, not automatic evidence of improvement. G-Funk uses no pitch-bend/portamento events. The Afrobeat/Afrobeats folder-label issue remains quarantined; these generated Afrobeats labels do not validate that original classification. Real listening remains **pending**.

<a id="document-genre-owned-midi-sample-md"></a>

## GENRE-OWNED-MIDI-SAMPLE.md

### Bounded actual owned-library MIDI sample

Re-read **41 actual MIDI files/accepted track-channel streams** covering **16 path-hint categories**. All SHA-256 hashes match the prior catalog and remain unchanged after this read-only analysis. Sources were not copied into generated outputs or the plugin.

These are already-owned files. No external MIDI was downloaded. Content roles were re-read from the exact accepted track/channel; genre names remain unverified path hints. Almost all categories come from one vendor folder, so different packs are not claimed as independent genre authorities. **The `afrobeats` classifier includes folders named `Afrobeat`; that ambiguity is unresolved and does not establish contemporary Afrobeats.**

Values are minimum / median / maximum across the bounded sample, in host beats. All role evidence is monolithic source material, not paired counterline/bass/harmony stems.

| Unverified hint | Observed role | Actual streams | Attacks /4beats | Median gate | MIDI span | Repeated top intervals |
|---|---|---:|---|---|---|---|
| afrobeats | chords | 3 | 5.02 / 5.59 / 5.63 | 0.12 / 0.64 / 0.71 | 26.00 / 31.00 / 48.00 | 0.19 / 0.19 / 0.36 |
| ambient | chords | 3 | 0.50 / 1.00 / 1.00 | 4.00 / 4.00 / 8.00 | 14.00 / 15.00 / 41.00 | 0.00 / 0.00 / 0.14 |
| disco | chords | 1 | 1.25 / 1.25 / 1.25 | 3.00 / 3.00 / 3.00 | 47.00 / 47.00 / 47.00 | 0.44 / 0.44 / 0.44 |
| dnb | chords | 3 | 0.38 / 1.56 / 4.00 | 1.50 / 3.00 / 8.00 | 31.00 / 50.00 / 58.00 | 0.00 / 0.04 / 0.39 |
| drill | chords | 3 | 0.50 / 1.50 / 1.62 | 2.00 / 2.00 / 8.00 | 32.00 / 38.00 / 44.00 | 0.00 / 0.18 / 0.44 |
| funk | chords | 1 | 0.75 / 0.75 / 0.75 | 4.00 / 4.00 / 4.00 | 24.00 / 24.00 / 24.00 | 0.00 / 0.00 / 0.00 |
| gospel | chords | 2 | 2.26 / 2.63 / 3.00 | 1.93 / 2.21 / 2.50 | 27.00 / 29.00 / 31.00 | 0.00 / 0.06 / 0.12 |
| hip_hop | bass | 2 | 4.00 / 4.25 / 4.50 | 0.50 / 0.75 / 1.00 | 8.00 / 10.50 / 13.00 | 0.00 / 0.27 / 0.53 |
| hip_hop | chords | 1 | 4.50 / 4.50 / 4.50 | 2.00 / 2.00 / 2.00 | 29.00 / 29.00 / 29.00 | 0.12 / 0.12 / 0.12 |
| house | bass | 3 | 2.12 / 5.07 / 6.69 | 0.25 / 0.50 / 1.25 | 8.00 / 12.00 / 23.00 | 0.00 / 0.28 / 0.65 |
| jazz | chords | 1 | 1.00 / 1.00 / 1.00 | 4.00 / 4.00 / 4.00 | 29.00 / 29.00 / 29.00 | 0.33 / 0.33 / 0.33 |
| lofi | chords | 3 | 1.00 / 3.75 / 4.00 | 2.00 / 2.00 / 4.00 | 29.00 / 53.00 / 55.00 | 0.00 / 0.03 / 0.67 |
| pop | chords | 3 | 0.88 / 1.00 / 1.25 | 2.50 / 3.50 / 4.00 | 22.00 / 26.00 / 26.00 | 0.00 / 0.00 / 1.00 |
| reggaeton | chords | 3 | 1.00 / 1.00 / 1.00 | 4.00 / 4.00 / 4.00 | 24.00 / 27.00 / 33.00 | 0.29 / 0.33 / 0.33 |
| rnb | chords | 3 | 1.50 / 1.60 / 8.01 | 2.00 / 2.48 / 3.89 | 19.00 / 24.00 / 26.00 | 0.00 / 0.09 / 1.00 |
| soul | chords | 3 | 2.00 / 2.00 / 3.01 | 1.95 / 1.98 / 4.00 | 23.00 / 24.00 / 28.00 | 0.00 / 0.29 / 0.45 |
| trap | chords | 3 | 2.02 / 6.50 / 8.15 | 0.19 / 0.50 / 0.86 | 9.00 / 32.00 / 62.00 | 0.13 / 0.16 / 0.19 |

Use: these observations can corroborate register, voicing, articulation and rhythmic hypotheses from reliable named sources. They cannot by themselves authorize assigning a genre identity, validate authenticity, establish historical rules, or justify automatically replacing all musical priors. The private evidence preserves hashes, source paths and stream selection; the public table contains only aggregates.

<a id="document-genre-research-acoustic-md"></a>

## GENRE-RESEARCH-ACOUSTIC.md

### Genre research: jazz, classical, country, gospel, blues, rock, funk and disco

Research date: **16 November 2026**. This is a public-safe research and implementation brief for eight of Ghost Note's 27 models. It records material actually opened online, musical observations from that material, and **proposed generative rules**. It does not certify finished implementation or audible genre accuracy. See TESTING.md for final-artifact evidence and the separate every-genre export comparison.

The priority is **genre accuracy, then musical quality, then variety**. Distinct hashes, random seeds and numerous chord combinations cannot establish the first two. These broad labels cover several traditions; a generated eight-bar idea can represent a chosen interpretation without representing every era or artist.

#### Evidence and method

The sources below are original educational publications, official instrument-maker lessons, and tutorials written or contributed by practicing musicians. Public lesson descriptions, syllabi, explanations and example descriptions were read. Berklee course pages establish curriculum topics, not access to their paid course demonstrations. Embedded audio/video was **not listened to**, complete scores were **not transcribed**, and no new external MIDI files were downloaded or event-analyzed for these eight genres. The Jeff Lorber PDF's explanatory text was read; no machine-readable event reconstruction is claimed.

These sources are complementary to the actual-file West Coast analysis in WEST-COAST-REFERENCES.md. That separate evidence must not be presented as MIDI evidence for these eight styles. Likewise, a library folder name is an unverified style hint.

All numerical registers, probabilities, gates and density limits proposed below are **engineering interpretations**, not measured source distributions. Roman numerals refer to musical functions; the selected scale remains authoritative. If a characteristic chromatic chord cannot be expressed under strict scale, preserve the scale and report the limitation. Do not silently change the user's key/scale or force a conventional major/minor label onto every scale formula.

#### Source-to-rule matrix

| Model | Intended interpretation and alternatives | Rhythm and phrase decisions | Harmony and part relationship | Distinction to check |
|---|---|---|---|---|
| Jazz | Small-ensemble tonal swing; also allow a sparser two-feel interpretation. This brief does not cover all modal, fusion or free jazz. | Stable swing subdivision; phrases with rests and developed motifs, rather than continuous scale runs. | Guide-tone voice leading, compact comping and a separate walking or two-feel bass. | Chord changes should be audible in the line; jazz must differ from Lo-fi through phrase activity and bass/comping behavior. |
| Classical | Late-eighteenth-century tonal keyboard theme; sentence or period, with broken-chord or block support. | Recalled opening, continuation or contrasting idea, deliberate weaker/stronger endings. | Tonic prolongation and cadential destination; accompaniment subordinate to melody. | Eight measures need a phrase trajectory rather than eight similar arpeggio bars. |
| Country | Straight alternating-bass country; alternate shuffle/honky-tonk or fingerstyle interpretation. Modern country-rock is another valid branch. | Dependable bass/chord alternation, recognizable upper phrase, selected turnaround and response. | Clear triads, root/fifth support and selective sixth/third harmonization. | The bass/accompaniment relationship should distinguish this from generic Pop or Rock. |
| Gospel | Hymn/call-and-response keyboard idea, with optional more active contemporary passing motion. | Main statement, supporting answer, restrained fills and planned cadence. | Smooth inversion movement, suspensions and connected bass approaches; extensions where appropriate. | Extra chord tones alone do not establish gospel; call/response and resolution need a role. |
| Blues | Eight-bar blues-inspired phrase/excerpt within the retained loop; straight or shuffle feel. Full twelve-bar form remains a separate requirement. | Repeated call, answering space, chord-related riff and turnaround. | Tonic/subdominant/dominant orientation; characteristic dominant quality when the pitch policy permits. | Do not turn every cadence into a jazz ii–V–I or describe a generic diatonic eight-bar loop as twelve-bar blues. |
| Rock | Driving riff/power-chord interpretation; alternate arpeggiated or sustained keyboard/guitar approach. | Even eighths or a selected shuffle branch; repeated riff and bass lock, followed by a fill. | Root/fifth emphasis, clear triads and sparse higher answers. | More deliberate pulse and stronger bass/riff alignment than Funk; avoid obligatory rich jazz extensions. |
| Funk | Interlocking small-ensemble groove; slower spacious pocket or denser sixteenth-note interpretation. | Repeating pocket that combines anchored and displaced attacks; short gates and purposeful silence. | Midrange comping leaves bass and upper line room; complementary bass/lead/chord rhythms. | A velocity change or swing percentage is insufficient; the roles need an interlocking onset pattern. |
| Disco | Live-band disco with an octave-bass interpretation; alternate restrained groove with longer soulful harmony. | Steady dance pulse, syncopated pitched parts, repeated hook with selective fill/answer. | Bass follows harmonic foundation; compatible extended or simplified voicings and upper accents. | Octave bass and repeating dance continuity should distinguish it from Funk's more broken pocket. |

#### Jazz: observations and proposed behavior

**Sources read.** [Bob Reynolds, “Focus on the Framework,” Berklee](https://www.berklee.edu/berklee-today/spring-2016/focus-on-the-framework) advocates developing short material, outlining thirds/sevenths, respecting form and leaving space. The page includes a credited transcription, but this review did not reconstruct its notes. [Gary Burton, “Jazz Scales You Need to Know,” Berklee](https://online.berklee.edu/takenote/jazz-improvisation-10-scales/) connects chord-scale choices to harmonic quality, including different dominant colors. [Berklee's Jazz Bass syllabus](https://online.berklee.edu/courses/jazz-bass) describes walking lines built from chord tones and half-step approaches across changes.

**Proposed rules.** Choose the next guide-tone target from the active chord and minimize travel from the previous phrase. Develop a short rhythmic contour; allow offbeat starts, held arrivals and silence. Walking bass should connect target chords through predominantly quarter-note motion; a two-feel branch uses fewer attacks. Use upper chord tones for comping so that the bass carries the foundation. Counter-melody should be a sparse answer, not a second continuous solo. Compatible sevenths/ninths and inversions add color without making every harmony maximally extended.

**Proposed implementation bounds.** Bass around MIDI 36–55, comping 53–76, lead 60–86; prioritize separation over rigid octave placement. Distinguish short comp attacks from connected bass/lead gates. Phrase accents should recur with the motif rather than assigning independent random loudness. Chromatic approaches are conditional on pitch policy. Modal or non-seven-note user scales need their own compatible reduction instead of an automatic altered-scale substitution.

#### Classical: observations and proposed behavior

**Sources read.** [Open Music Theory, “The sentence”](https://openmusictheory.github.io/sentence.html) explains a repeated basic idea followed by continuation, including fragmentation, sequences and increased rhythmic or harmonic activity toward a cadence. Its Mozart K. 283 discussion permits varied repetition of rhythm/contour. [Open Music Theory, “The period”](https://openmusictheory.github.io/period.html) describes antecedent/consequent balance, return of the opening idea and a stronger final cadence, using a Haydn trio example. [University of Puget Sound, “Arpeggiated Accompaniments”](https://musictheory.pugetsound.edu/mt21c/ArpeggiatedAccompaniments.html) distinguishes the low–high–middle–high Alberti ordering from simple ascending/descending arpeggiation.

**Proposed rules.** Select a sentence or period plan before emitting notes. A sentence can state/variously repeat a two-bar idea, then fragment it and approach closure. A period should recall its opening in the second half, with a weaker middle and stronger final ending. Generate cadence-aware bass/harmony first, then fit the melodic destination. Choose one accompaniment texture per phrase, with a controlled change at the boundary; avoid obligatory simultaneous block chords over an Alberti stream. Counterpart motion should remain subordinate and occasionally contrary rather than merely doubling lead rhythm.

**Proposed implementation bounds.** Keep the lead principally above the accompaniment, for example lead MIDI 60–84 and support 40–67 with crossing checks. Connected phrase interiors and a shorter breath before a cadential arrival are more useful than indiscriminate staccato. Phrasing accents can follow two-/four-bar structure. These examples support a Classical-era keyboard interpretation; they do not justify claims about the entire Baroque-to-contemporary classical repertoire.

#### Country: observations and proposed behavior

**Sources read.** [Fender, “Learn Classic Country Guitar Techniques”](https://www.fender.com/articles/techniques/how-to-play-classic-country-on-guitar) explains alternate bass-note strumming, Travis and tic-tac alternatives, accessible triads/sevenths, and major/minor pentatonic vocabulary. [Berklee's Country Guitar syllabus](https://online.berklee.edu/courses/country-guitar) separates Sun Records rhythm, honky-tonk/shuffle, Western swing, country rock/pop and fingerstyle. It includes common-tone/inversion study, thirds/sixths and a lesson on leaving space.

**Proposed rules.** Choose a coherent interpretation per print. For straight country, alternate low root/fifth support with higher chord responses and use a short pentatonic/triadic melody. For shuffle, apply a consistent subdivision to the phrase rather than jittering notes independently. Fingerstyle may distribute chord tones across the existing low/chord roles. Use occasional thirds/sixths as a response or phrase-end harmonization, with small turnaround activity leading to the next harmony. Do not force the same dense Western-swing harmony into every traditional or modern branch.

**Proposed implementation bounds.** A useful starting register separates bass MIDI 36–55, chord tones 48–72 and lead 60–84. Chords/answers need controlled short or plucked gates; a chosen sustained branch can lengthen them. Accent the repeating picking relationship and reserve fills for selected gaps. Pedal-steel bends and guitar-specific slides are documented stylistic resources, but this note-only exporter does not reproduce those articulations. Avoid claiming that changing preview timbre supplies the composition's country identity.

#### Gospel: observations and proposed behavior

**Sources read.** [Berklee's Gospel Music for Keyboard syllabus](https://online.berklee.edu/courses/gospel-music-for-keyboard) distinguishes traditional, contemporary, hymn, choir and praise/worship contexts; call-and-response and church cadences recur throughout. [PianoGroove, “Gospel Chord Progressions”](https://www.pianogroove.com/blues-piano-lessons/gospel-chord-progressions/) describes introductions, bass walk-ups/down, suspended voicings, a 3–6–2–5–1 framework, dominant chains and possible plagal/turnaround treatments. Its walkthrough aims an introduction toward a destination chord rather than filling time with unrelated voicings.

**Proposed rules.** Build the cadence destination into the harmony plan, then connect the bass and inversions to it. Select hymn-like support or a more active contemporary response instead of treating Gospel as one density setting. Introduce a suspension and its resolution as a paired event. Use a bass walk-up only when it approaches a chosen chord. Main phrase and response should exchange space; optional upper fills can increase late in the phrase. Compatible sevenths/ninths are useful color, but function, pacing and voice leading need to be audible first.

**Proposed implementation bounds.** Low foundation around MIDI 36–55, connected inner voicings 50–76, lead/answer 60–86. Use longer support under a statement, shorter response attacks and phrase-shaped dynamics. Do not randomly add parallel dense chords to every melody note. Many secondary dominants, diminished passing chords and substitutions require notes outside one selected scale. Strict mode must constrain them, so a strict minor/pentatonic result cannot be advertised as unrestricted traditional gospel reharmonization.

#### Blues: observations and proposed behavior

**Sources read.** [Open Music Theory, “Blues Harmony”](https://viva.pressbooks.pub/openmusictheory/chapter/blues-harmony/) separates blues from common-practice/jazz function: dominant sevenths can be stable tonic/subdominant chords; a typical twelve-bar form has three four-bar phrases and V–IV–I closing motion. It also contrasts jazz-blues ii–V changes. [Fender, “Blues in A With 7th Chords”](https://www.fender.com/play/courses/blues-in-a-with-7th-chords) offers dominant-seventh exercises with shuffle, bass-note strumming and anticipation variants. [Berklee's Blues and Rock Keyboard Techniques syllabus](https://online.berklee.edu/courses/blues-and-rock-keyboard-techniques) names blue notes, grace notes, shuffle bass, different comping approaches and phrasing.

**Proposed rules.** Choose a straight or shuffle riff and retain its call/response identity. Let the harmony's tonic/subdominant/dominant roles guide replies and the final turn. Short grace/passing gestures should resolve to an intended target; do not sustain every available “blue” pitch equally. Root/fifth/sixth-type bass vocabulary and stronger chord-quality targets can differentiate this from generic minor pentatonic runs. Counter-melody fills should answer rests instead of competing throughout. Repeated ideas with changed endings are more informative than uniformly random licks.

**Format and pitch limits.** Ghost Note retains eight host bars. Describe this as a blues-inspired idea/excerpt; an eight-bar print is not the standard twelve-bar form merely because it uses I, IV and V. The I7/IV7/V7 collection also exceeds one ordinary diatonic scale. Keep strict scale authoritative and identify the resulting reduction. MIDI pitch/length/velocity can suggest attack and phrasing but cannot reproduce microtonal bends or a performed blues articulation by itself.

#### Rock: observations and proposed behavior

**Sources read.** [Nick Stoubis/Fender, “Distortion, Power Chords & Rock Tunes”](https://www.fender.com/articles/chords/distortion-power-chords-path-rock-glory) emphasizes two-pitch-class power-chord sonority and sustain. [Berklee's Pop/Rock Keyboard syllabus](https://online.berklee.edu/courses/pop-rock-keyboard) includes triads, inversions, voice leading, quarter-/eighth-note comping and arpeggiated parts. [Berklee, “Funk and Rock Drum Rhythms”](https://online.berklee.edu/takenote/basic-funk-for-drums/) explicitly contrasts driving eighth-note bass with lighter sixteenth-note funk over a shared drum foundation and includes a shuffle branch.

**Proposed rules.** Choose a repeated riff whose accents are reinforced by bass. A power-chord interpretation prioritizes roots/fifths, while an arpeggiated branch uses compatible triads/inversions and longer ring. Preserve a memorable one-/two-bar contour, then alter selected phrase endings. Upper pentatonic/chord-tone replies should fit around the riff. Keep extensions optional and purposeful; rich four-/five-note chords on every attack would weaken the intended distinction from Jazz/Gospel. Use a selected straight or shuffle interpretation rather than a mixture caused by timing noise.

**Proposed implementation bounds.** Bass around MIDI 28–52, low/mid chord support 40–69, upper answer 60–86, with low chords kept sparse. Strong repeated accents and deliberate short/long gate contrast can suggest muted versus ringing passages. These are note-level approximations; distortion, pick attack, palm muting and amplifier sustain remain receiving-instrument concerns. MIDI cannot establish an authentic guitar performance from chord names alone.

#### Funk: observations and proposed behavior

**Sources read.** [Jeff Lorber, “Funk Comping,” hosted by the musician](https://www.lorber.com/wp-content/uploads/2024/07/Jeff_Lorber_on_Funk_Comping.pdf) explains interlocking repeated parts, combinations of anchored eighth notes and displaced sixteenths, midrange comping that avoids the bass/lead, and left-/right-hand counterpoint. The explanatory text contrasts 108 BPM and more spacious 84 BPM examples. [Chelsea Stevens/Fender, James Brown's “I Got the Feelin'” lesson](https://www.fender.com/play/lessons/bass-i-got-the-feelin) specifically identifies syncopation and string muting in the bass role. Berklee's rock/funk comparison above reinforces the importance of the ensemble relationship.

**Proposed rules.** Select a repeating onset pocket first, including an anchor and displaced answers; retain it long enough to create recognition. Allocate selected gaps to the answering role rather than independently filling every gap in every layer. Short chord stabs, low bass punctuation and an upper fragment should interlock. A slow interpretation can use more space; greater complexity can add a selected pickup or phrase-end fill without dissolving the pocket. Tonic-oriented vamps with an occasional late harmonic turn are a useful branch, not a universal definition.

**Proposed implementation bounds.** Start comping around MIDI 53–67, bass 28–52 and lead/answer 64–84. Clip selected gates and preserve silence; use repeatable accent hierarchies. Register separation and actual onset complementarity matter more than a universal swing amount. Instrumental dead-string sounds are not the plugin's faint visual ghost notes. Do not generate independent sounding “ghost” layers or claim MIDI velocity alone reproduces slap/muting technique.

#### Disco: observations and proposed behavior

**Sources read.** [Jafunk/Splice, “How to make disco music”](https://splice.com/blog/how-to-make-disco-music/) combines the producer's firsthand account with extended harmony, sixteenth-note syncopation over a dance pulse and small variations in performed repetitions; it also distinguishes live-band roots from modern production. [Tim Cant/Native Instruments, “How to write a disco song”](https://www.native-instruments.com/blogs/blog/disco) provides a sequenced tutorial with octave-skipping bass, simplified keyboard voicings, repeated hooks and section contrast. In its bass example, lower on-beat notes alternate with octave-up notes between beats. These are examples, not a corpus-wide frequency estimate.

**Proposed rules.** Use an octave-alternating bass branch tied to the current harmonic foundation, with selected anticipations/fills. Keep a recurring upper hook or comp rhythm over it; complementary chords may use compatible sevenths/ninths or deliberately omit the fifth for clarity. Preserve dance continuity while introducing an answer or turnaround around four-/eight-bar boundaries. A restrained branch can sustain soulful harmony over the bass instead of putting a full chord on every eighth note. Avoid making every layer share the octave-bass rhythm.

**Proposed implementation bounds.** Bass MIDI 28–55 with octave jumps above its chosen lower anchor, chords 53–77 and upper accents 67–88. Use controlled short bass/comp gates and smoother held support when the branch calls for it. Recurrent accents plus modest end-of-phrase changes are preferable to uniform velocity jitter. The pitched-MIDI model contains no drum arrangement; a reference's four-on-the-floor percussion is context, not an event sequence present in Ghost Note's export.

#### Verification required after implementation

For each of these models, retain at least twenty actual exported examples in a reproducible settings/seed matrix, and compare baseline/refined outputs under equivalent conditions. Report phrase/rhythm fingerprints, harmonic movement, range, gates, density, silence and part relationships. Separate complete-sheet measurements from layer measurements: merging equal-pitch overlaps can obscure a role's articulation.

Inspect intended distinctions explicitly: Jazz versus Lo-fi, Rock versus Country, Funk versus Disco, Gospel versus Jazz, and Blues versus generic minor-scale writing. A metric can flag excessive density, weak repetition or missing octave behavior; it cannot decide whether a phrase feels convincing or supports a performer.

Audition actual exports with appropriate receiving instruments and compare them to the referenced musical approach. Record what was heard, the exact export/settings, useful/problematic moments and the reviewer's judgment. Until that happens, mark listening review **pending**. Do not assign an objective authenticity/usability percentage or turn sample uniqueness into an artistic verdict. Do not publish original MIDI, copied source-event sequences or private library paths with this report.

<a id="document-genre-research-electronic-md"></a>

## GENRE-RESEARCH-ELECTRONIC.md

### Electronic, Afrobeats and reggaeton evidence ledger

Research performed online on 2026-11-16 before legacy-engine edits. These are publisher/producer educational texts, original artist interviews and legitimate MIDI catalog pages. No online MIDI payload was downloaded or parsed, no embedded video/audio was listened to, and no note-sequence/transcription claim follows from a catalog description. Exact timing, probability and register choices below are proposed implementation rules, not measurements of unseen MIDI. The actual owned MIDI audit is documented separately.

| Model | Primary references actually consulted | Observation supported by text | Composition rule inferred for this engine |
|---|---|---|---|
| House | [NI deep-house walkthrough](https://www.native-instruments.com/blogs/blog/how-to-make-a-deep-house-track); [NI bass-line walkthrough](https://www.native-instruments.com/blogs/blog/how-to-write-a-bassline) | Deep-house example uses a two-bar harmonic idea, root-following bass, a third-area change and a more rhythmic organ response. Bass tutorial develops a funky house groove from harmony and adds rhythm, departures from roots and longer development. | Keep offbeat comping; compose a repeated compact chord-tone hook; use two-bar bass pocket with root anchor and selected octave/third approaches. A house model is scoped to this melodic/deep/funky pocket, not every house subgenre. |
| Techno | [NI techno walkthrough](https://www.native-instruments.com/blogs/blog/how-to-make-techno); [NI melodic-techno walkthrough](https://www.native-instruments.com/blogs/blog/melodic-techno) | First distinguishes repetitive Detroit-rooted sequencing and several bass approaches. Second describes two-bar chord changes, short stutter lead entries and rolling root bass. | Favor long tonic/modal pedal and small short sequencer cells; occasional phrase-level harmonic contrast and quiet upper response. Preserve differences from House's regular offbeat chords. Melodic-techno conventions are optional contrasts, not universal techno rules. |
| Drum & Bass | [NI DnB walkthrough](https://www.native-instruments.com/blogs/blog/drum-and-bass); [NI official production lesson](https://www.youtube.com/watch?v=bfPZ_ywTVhc); [Test Press liquid DnB MIDI catalog](https://splice.com/sounds/packs/test-press/liquid-dnb-2/midi) | Written walkthrough constructs a two-bar bass phrase and layers sustained sub support; supporting synths include sparse small pitch ideas. Official lesson description explicitly scopes neurofunk; catalog offers distinct chord, bass and synth roles, but yields no inspectable note data. | Choose syncopated held bass plus short pickups, chord-support hooks with gaps, distinct restrained upper reply. Avoid equating liquid harmony with all neurofunk. No timbral distortion or sample-break generation is claimed. |
| Dubstep | [NI dubstep walkthrough](https://blog.native-instruments.com/how-to-make-dubstep/); [Ableton MIDI effects manual](https://www.ableton.com/en/live-manual/11/live-midi-effect-reference/) | NI's original/classic-leaning example uses half-time snares, a repeated two-note/two-bar bass gesture with a shifted ending and a sparse lead. Ableton explains beat-synchronized note sequencing, gate and retrigger behavior; this is a technical source, not independent genre validation. | Bass-led two-bar question/reply with an ending pickup, long harmonic ground and a sparse lead answer. Sound-design wobble, growls and effects remain receiving-instrument responsibilities. |
| Trance | [NI uplifting-trance walkthrough](https://www.native-instruments.com/blogs/blog/trance-music); [Ableton arpeggiator manual](https://www.ableton.com/en/live-manual/11/live-midi-effect-reference/); [Ableton Tom Cosm template notice](https://www.ableton.com/en/blog/new-template-sets-and-tutorials-certified-trainer-tom-cosm/) | NI describes repeating layered riffs and short offbeat bass with intentional omissions. Manual explains deterministic chord-note ordering. Template notice confirms a separate psytrance resource; its contents were not downloaded/analyzed. | Scope current model to melodic/uplifting loops; chord-tone rolling sixteenths, longer repeated hook and offbeat pulse bass, occasional phrase-end omission. Do not silently turn it into psytrance or claim a downloaded template. |
| Ambient | [Splice ambient tutorial](https://splice.com/blog/how-to-make-ambient-music/); [NI atmospheric-production tips](https://www.native-instruments.com/blogs/blog/7-ways-to-amp-up-the-atmosphere) | Splice emphasizes isolated sounds/silence, extended sustains and gradual voicing evolution; NI emphasizes spaces, effects and ambience. | Longer harmonic regions, open/common-tone voicing, very sparse long lead and independent high response. Reverb/texture is outside note-only generation; arbitrary fast tempo must not force dense note placement. |
| Afrobeats | [Splice's original Mystro, LeriQ and Dunnie interview](https://splice.com/blog/beyond-afrobeats/); [NI rhythm discussion](https://blog.native-instruments.com/what-makes-a-good-song/); [Dunnie original pack catalog](https://splice.com/sounds/packs/splice/dunnie-sample-pack/samples) | Interview identifies a broad contemporary pop/fusion culture, central groove and percussive or soulful melodies; explicitly separates Afrobeat. NI notes interlocking rhythmic influences. Artist catalog confirms muted-guitar, bass, synth/vocal/percussion roles; no event-data measurements follow. | Two-bar repeating plucked/chord-tone phrase with offbeat attacks, complementary counter pocket and bass support, restrained variation and vocal gaps. No required log drum, four-on-floor house pattern or long Fela-style brass jam. Named progression frequencies cannot be estimated from this evidence. |
| Reggaeton | [NI full reggaeton walkthrough](https://www.native-instruments.com/blogs/blog/reggaeton); [Splice Originals MIDI catalog](https://splice.com/sounds/packs/splice-originals/serum-2-reggaeton-essentials/midi) | NI anchors a production to dembow, root-following sub, inverted chords and distinct lead/rhythm roles, with simpler verse versions. Catalog lists major/minor chord, lead, arp and bass material; does not expose event bytes. | Stable repeating call/response in a dembow-compatible pocket, root-led bass with deliberate pickups, smooth inverted harmony. Tresillo is one melodic resource, not a substitute for dembow or proof that every Latin style is the same. |

#### Musical scope and acceptance limits

Every named electronic genre is broad. Refinements specify an internally consistent melodic interpretation, retaining stable IDs/names. Host tempo and selected scale remain authoritative; mode or chromatic examples from articles do not license outside-scale notes under Strict Scale. Cadence/substitution probabilities and per-style numeric gates are authored design choices, not fitted statistics. These sources guide testable rhythm/phrase/harmony/bass behavior; they cannot establish subjective authenticity. Formal before/after measurements and human reference-versus-generated listening are separate validation steps.

The future-house URL surfaced a useful search excerpt but redirected to a category page when opened; it is not used as an independently verified source here. The Splice Iss 814 tutorial is explicitly about **Afrobeat**, so it is retained only as a distinction and was not used to define Afrobeats output.

<a id="document-genre-research-hiphop-pop-md"></a>

## GENRE-RESEARCH-HIPHOP-POP.md

### Hip-hop, pop and guitar model research — 16 November 2026

This is a source-to-rule design matrix, not an authenticity certificate. Text lessons and interviews below were opened/read. Embedded audio/video was not listened to, and online MIDI was not downloaded. The separately documented 20 owned MIDI references were actually parsed and measured. Catalog labels and interviews supply context; their musical event content cannot be inferred from a product description.

#### Source register

- **S1:** [Native Instruments: making a trap beat, Tim Cant](https://www.native-instruments.com/blogs/blog/how-to-make-a-trap-beat). Sparse accompaniment, one or two foreground melodies, straight rather than universal swing, and space around a pitched bass part. The tutorial's drum details inform context rather than adding percussion to this composition library.
- **S2:** [Splice: developing a melody](https://splice.com/blog/how-to-develop-a-melody/). The author develops a short trap motif through rhythmic changes and restrained phrase-ending development. Its Phrygian mixture example is an optional harmonic color, never permission to break a selected strict scale.
- **S3:** [Native Instruments: hip-hop chord progressions](https://www.native-instruments.com/blogs/blog/hip-hop-chord-progressions). Distinguishes melodic, chilled and trap contexts and discusses short harmonic loops. The final listed Roman numeral and spelled chord disagree; implementation must calculate actual intervals instead of copying that label. A handful of worked examples is not an exhaustive generation vocabulary.
- **S4:** [Native Instruments: writing a melody](https://www.native-instruments.com/blogs/blog/how-to-write-a-melody). Hook identity, phrase contour and interaction with accompaniment; descriptive examples cover multiple contexts rather than a single genre formula.
- **S5:** [Native Instruments: drill, Tim Cant](https://www.native-instruments.com/blogs/blog/drill). Separates Chicago origins from later UK rhythmic conventions. Its written bass/lead example uses simple repeated pitch anchors and a late overlapping flourish with an instrument configured for glide. MIDI note overlap and synthesizer portamento are separate behaviors.
- **S6:** [Splice: UK drill tutorial, Nick Chen](https://splice.com/blog/uk-drill-with-drill/). An original production walkthrough offering MIDI/stems and demonstrating atmospheric sound construction. The page was read; the project was not downloaded and the video was not heard, so exact note probabilities are not attributed to it.
- **S7:** [Native Instruments: R&B harmony](https://www.native-instruments.com/blogs/blog/rhythm-and-blues-chord-progressions). Extended chords, inversions, common tones and borrowed harmony. Its examples include pitches outside a single major collection; those require compatible modes or explicit Strict Scale off.
- **S8:** [Berklee: voice-leading paradigms](https://online.berklee.edu/takenote/voice-leading-paradigms-for-harmony-in-music-composition/). Preserve common tones and favor short movement in individual chord voices, with purposeful register changes. These are arranging principles, not a universal ban on expressive leaps.
- **S9:** [Native Instruments: lo-fi hip-hop](https://www.native-instruments.com/blogs/blog/lo-fi-hip-hop-beats). Minimal evocative extended harmony, repeated phrases, a counterline in melodic gaps, relaxed timing and optional root-support bass. Audio degradation belongs to the receiving sound/mix rather than being faked as a MIDI property.
- **S10:** [Splice: lo-fi chord progressions, Matt Brooks](https://splice.com/blog/lo-fi-chord-progressions/). Patient harmonic pacing, extended voicings and economical loops can remain effective with few chord roots. Complexity should not simply add chord changes.
- **S11:** [Splice: pop production with Esthy](https://splice.com/blog/how-to-make-pop-music/). A topline-centered arrangement supported by MIDI bass/keys/synths. Reading the article establishes its workflow, not a transcribed rhythmic pattern from the video.
- **S12:** [Native Instruments: songwriting](https://www.native-instruments.com/blogs/blog/songwriting-guide). Repetition, recognizable melodic contour and controlled development; harmonic function and rhythmic phrasing support the hook.
- **S13:** [Traxamillion interview, AllHipHop](https://allhiphop.com/features/traxamillion-super-hyphy/). First-person discussion of upbeat club intent and workstation-based production. It does not prescribe a particular Roman-numeral cycle or establish MIDI note densities.
- **S14:** [P-Lo interview, KQED](https://www.kqed.org/arts/13811392/behind-the-beats-p-lo). First-person context for post-hyphy Bay production and the role of bass-heavy party arrangements. The broad scene contains multiple styles; a generic Bay preset cannot certify all of them.
- **S15:** [Kai Narezo: flamenco chord construction](https://flamencoexplained.com/education/the-complete-guide-to-flamenco-guitar-chords/). Describes the functional distinction between Phrygian and a flamenco collection with both thirds, pedal/open-string colors, and contextual tonic tension. A fixed equal-tempered scale mode cannot silently become that larger collection.
- **S16:** [Flamenco Explained: terminology](https://flamencoexplained.com/flamenco-guitar-glossary/). Separates sequential arpeggio, strum and thumb-led bass techniques; Farruca provides a specific minor-key 4/4 context. These ideas inform the existing dark nylon-guitar hybrid; they do not make it a complete model of Latin music or every flamenco palo.

#### Evidence-led implementation proposals

| Existing model | Harmonic and phrase decisions | Melody / counter / bass / articulation | Distinction and measured checks |
|---|---|---|---|
| Melodic Rap | Functional minor/major loops with repeated two-bar cells and a small later turn; tonic or related-root anchors, not a new chord on every melodic event. S2–S4, S12. | A singable short contour with repeated pitch/rhythm identity; quieter late answers and a bass that supports rather than doubles every attack. | More sustained hook development and balanced register than Trap's small ostinato; test recurrent cells, structural chord tones, quiet gap answers and bounded phrase changes. |
| Trap | Strong tonic/pedal persistence, restrained root changes, prepared approach/return; variations may change gates, pickups and endings while the hook survives. S1–S3. | Short two/four-bar minor or modal ostinato, occasional repeated-note/triplet pickup; sparse accompaniment and root-centered low bass. Straight grid is a default, not mandatory global swing. | Fewer foreground/harmonic events than Pop, clearer repeated motif than a random walk. Compare actual onsets, sustained rests and strong-note/chord agreement. No drum MIDI is introduced. |
| R&B | More seventh/ninth voicings, shared tones and economical voice movement, with cadence/predominant or related-root alternatives. S7–S8. | Expressive medium-register phrases, longer notes mixed with pickups; restrained answers that account for sustained lead gates; bass roots/approaches maintain function. | Richer voicings and less static phrase behavior than Lo-fi, with room for vocals. Measure basic thirds/sevenths, nearest voice displacement and gap-compatible counter durations. Borrowing respects Strict Scale. |
| Drill | Dark sustained harmonic anchors with intermittent tension/return, retaining a short recognizable melodic cell. S5–S6. | Sparse high/mid piano/bell-like phrases and offbeat low bass attacks; occasional late register contrast, not constant scalar motion. Monophonic receiver glide may interpret overlapping pitches. | Give bass and lead different attack grammars from Trap; documented UK-influenced groove is only one interpretation. Do not claim a universal UK/Brooklyn/Chicago model or invent note-bend events. |
| Bay Area | Economical tonic/related-root vamps and occasional turns, leaving the bass/hook pocket exposed. S13–S14 plus the independently measured West Coast bass/lead examples. | Short syncopated stabs, repeated compact hooks, root/octave/fifth bass replies and purposeful silences. | More percussive/funk-shaped pocket than the new dark EBK piano; fewer held extended chords than Classic G-funk. Interview-derived design choices are engineering inferences; actual reference metrics remain separately labeled. |
| Dark Latin Guitar | Minor/modal guitar accompaniment with descending functional motion, bass anchors and phrase-ending cadences; compatible dominant colors only when the selected formula permits them. S15–S16 and S8. | Sequential chord-tone arpeggios, thumb-like bass/melody priority, measured staggered strums and a quieter answer in the gaps. | A dark nylon-style hybrid in 4/4, not a catch-all Latin, salsa, reggaeton or flamenco engine. Check directional arpeggio continuity, guitar register and controlled strum span; preserve user-selected modes. |
| Pop | Clear functional tonic/predominant/dominant-related movement with phrase-level repetition and recognizable arrival; no reliance on three fixed root cycles. S11–S12 and S4. | A compact singable hook, stepwise contour with occasional prepared leap, repeated two-bar phrasing and a later ending change; bass supports chord changes and counter arrives between lead gestures. | More balanced clear hook/cadence and regular support than Trap or Ambient. Audit phrase recurrence, purposeful final arrival and the ratio of development to exact repetition. A topline-friendly MIDI sketch is not a complete song arrangement. |
| Lo-fi | Fewer, longer extended chords with common-tone continuity; a small jazz-related loop is sufficient. S9–S10 and S8. | Understated repeated phrases, low-density gap answers, soft coherent accents and bounded relaxed microtiming; optional bass roots with gentle approaches. | Less active than Jazz/R&B, with longer harmonic breathing space; no fake claim that random timing or vinyl noise establishes the genre. Audit gates/rests, voicing continuity, counter overlap and activity at matched complexity. |

#### Quality evaluation contract

1. Freeze twenty varied plus twenty controlled examples per old model before changes; hold key, tempo, feel and complexity constant for the controlled comparison.
2. Compare the refined outputs using role-level events, not only the flattened sheet. Report harmony, rhythmic onsets, structural intervals, voicing movement, phrase recurrence, rests, activity and register.
3. Apply scale/range/MIDI ownership checks as technical validity, not genre authenticity. A low dissonance count also does not establish good music.
4. Treat reference-feature bands as bounded diagnostic screens; do not turn twenty examples or a few tutorials into a percentage of globally authentic/usable music.
5. Export representative baseline and refined MIDI. Render matched instrument/context examples for producer listening, then record actual feedback. No completed listening verdict is asserted here.

The original names and IDs remain stable. Sound design, percussion, vocals, arrangement and cultural context materially affect recognition; this audit focuses on the pitched MIDI the generator actually controls. Those boundaries must remain visible in the final results.

<a id="document-ghost-note-artwork-md"></a>

## GHOST-NOTE-ARTWORK.md

### Ghost Note artwork

An original illustration was generated for **Ghost Note** using the built-in image generation tool on November 2, 2026. The imagegen skill was used in its default built-in mode; no external reference image, existing character, stock library or fallback API script was used.

- Project asset: `assets/ghost-note-art.png`
- User deliverable: `Ghost-Note-Artwork.png`
- Dimensions: 1254 × 1254 pixels
- Format: 32-bit RGBA PNG; the four corner alpha values are zero.
- Bytes: 1,261,338
- SHA-256: `023f40d48e96e6550abf39abad65e20e0c2d4b38ac9f9f55310b91853f27ec28`

The complete generated image was visually inspected. It shows an ivory manuscript-paper ghost with black musical ribbons and restrained copper edges, without brand lettering or a borrowed character. The plugin displays it as a compact header emblem. The project copy preserves the generated alpha and pixels; no image editor was used. This provenance records the creation workflow and does not establish trademark exclusivity.

#### Final generation prompt

Use case: stylized-concept. Asset type: original signature artwork for the music software Ghost Note, both a compact plugin header emblem and a shareable square illustration. Create one premium, enigmatic ghost figure sculpted from folded ivory music manuscript paper, with black flowing musical ribbon forms wrapping its lower silhouette and restrained burnished copper edges. The ghost is sophisticated, mysterious and charismatic, with a bold memorable silhouette that still reads as a small 48-pixel header portrait; hollow dark face aperture, no cartoon face, no cute mascot. Etched graphite and warm ivory material, precise editorial concept art with subtle dimensional studio lighting, finely rendered but uncluttered. Center the complete figure in a square composition with generous transparent margin. The background must be genuinely transparent, with no ground plane, scenery, backdrop, cast shadow, glow haze or checkerboard baked into the artwork. No text, words, brand lettering, logos, watermarks, UI or borrowed characters. A few tiny manuscript marks may be abstract and non-legible; no real song notation. Preserve a clear ivory silhouette against a dark graphite plugin interface.

<a id="document-west-coast-reference-comparison-md"></a>

## WEST-COAST-REFERENCE-COMPARISON.md

### Actual West Coast reference feature comparison

> Frozen engine-source audit, 16 November 2026. Engine.cpp SHA-256: 995DD679A5B1D0904A023818394214A6032DE049E137DADDF5CC4103A2FED991. The factory catalog includes the style-12 weak-general-fallback quarantine. These measurements verify the recorded source snapshot, not final binary/installer/FL Studio behavior or producer listening.


Read all **20 local reference MIDI files again**, all **60 original 0.4 generated complete MIDI scores**, and **60 additional controlled eight-bar scores** with retained part identities. All source SHA-256 hashes remain unchanged. No listening was performed.

Values are **minimum / median / maximum across files**, in host beats. Source files have separately observed roles; the original sixty exports flatten all enabled parts into one piano sheet and have no recoverable original role labels. Their whole-score statistics are therefore not compared as if they were melody-only references. The additional role-preserving samples use A natural minor, 120 BPM, normal feel, complexity 0.5 and the same twenty seeds in all three models.

| Model / known role | Sources | Source attacks /4beats | Generated role attacks /4beats | Source median gate | Generated role median gate | Source pitch span | Generated role pitch span |
|---|---:|---|---|---|---|---|---|
| EBK / Chords | 1 | 5.00 / 5.00 / 5.00 | 1.50 / 1.75 / 1.88 | 0.48 / 0.48 / 0.48 | 0.25 / 0.25 / 0.50 | 19.00 / 19.00 / 19.00 | 7.00 / 9.00 / 14.00 |
| EBK / Melody | 1 | 4.00 / 4.00 / 4.00 | 2.00 / 2.75 / 3.50 | 1.31 / 1.31 / 1.31 | 0.23 / 0.44 / 0.47 | 7.00 / 7.00 / 7.00 | 3.00 / 7.00 / 12.00 |
| Modern LA / Chords | 4 | 1.25 / 2.75 / 4.50 | 0.75 / 1.75 / 4.00 | 0.25 / 3.11 / 5.86 | 0.25 / 3.59 / 7.09 | 8.00 / 19.50 / 29.00 | 9.00 / 10.00 / 12.00 |
| Classic G-Funk / Chords | 4 | 0.62 / 1.12 / 1.75 | 0.50 / 0.62 / 0.62 | 1.99 / 5.23 / 7.98 | 7.78 / 7.78 / 7.81 | 17.00 / 19.00 / 24.00 | 10.00 / 12.00 / 14.00 |
| Broader West Coast / Chords | 1 | 2.00 / 2.00 / 2.00 | No same-model comparison | 3.73 / 3.73 / 3.73 | — | 34.00 / 34.00 / 34.00 | — |
| Classic G-Funk / Melody | 4 | 3.00 / 4.62 / 5.00 | 3.00 / 3.00 / 3.00 | 0.24 / 0.45 / 0.56 | 0.44 / 0.44 / 0.44 | 12.00 / 14.50 / 24.00 | 8.00 / 12.00 / 16.00 |
| Classic G-Funk / Bass | 5 | 3.75 / 5.25 / 6.25 | 5.00 / 5.12 / 5.12 | 0.25 / 0.30 / 0.54 | 0.35 / 0.35 / 0.35 | 5.00 / 8.00 / 10.00 | 8.00 / 10.00 / 10.00 |

The JSON includes step/repeated-note contour ratios, onset syncopation, velocity, register, motif recurrence and counts outside each observed band. These are **drift screens**, not success percentages. A one-file EBK role band is one observed composition, not an authentic genre limit. Independent bass and lead references are not claimed as paired stems; there are no measured counter-melody pairs. The broader Oracle harmony is retained separately because its Phrygian color and provenance do not establish EBK identity.

| Original combined-score model | Actual exports | Clustered attacks /4beats | Median gate | Pitch span |
|---|---:|---|---|---|
| EBK | 20 | 1.62 / 4.62 / 7.62 | 0.44 / 0.47 / 1.00 | 34.00 / 43.00 / 48.00 |
| Classic G-Funk | 20 | 2.75 / 5.00 / 6.38 | 0.60 / 0.91 / 1.81 | 44.00 / 50.50 / 62.00 |
| Modern LA | 20 | 2.50 / 5.12 / 6.25 | 0.37 / 0.54 / 1.65 | 38.00 / 46.00 / 54.00 |

Genre/quality conclusion: these measurements support different role/gate/density targets and expose departures; they do not establish that any generated file sounds authentic or musically good. Listen to matched before/after examples with suitable piano/EP/synth/bass sounds, assess the complete arrangement, then judge melody/bass/harmony stems independently. Source sequences and private paths must not enter the distributable plugin or public report.

<a id="document-validation-build-ghost-note-1-0-0-txt"></a>

## validation/build-ghost-note-1.0.0.txt

```text
Sanitized Ghost Note 1.0.0 metadata-corrected verification record — 16 November 2026
VST3 SHA-256: 3a8d83a6417f7f6b4975af5ffd3ad52bc56ae7279bbdf55c32c88f918f144365
Private workspace paths redacted. Original raw log retained privately.

-- Configuring juceaide
-- Building juceaide
-- Exporting juceaide
-- Testing juceaide
-- Finished setting up juceaide
-- Configuring done (3.1s)
-- Generating done (0.8s)
-- Build files have been written to: [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished
-- Configuring done (0.2s)
-- Generating done (0.2s)
-- Build files have been written to: [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished/vst3_helpers/MidiComposer
[0/2] Re-checking globbed directories...
[1/5] Generating MidiComposer_artefacts/JuceLibraryCode/MidiComposer_resources.rc
[2/5] Building RC object CMakeFiles\MidiComposer_rc_lib.dir\MidiComposer_artefacts\JuceLibraryCode\MidiComposer_resources.rc.res
[3/5] Building VST3 manifest helper for MidiComposer
-- Configuring done (0.2s)
-- Generating done (0.3s)
-- Build files have been written to: [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished/vst3_helpers/MidiComposer
ninja: no work to do.
[4/5] Linking CXX shared module "MidiComposer_artefacts\Release\VST3\Ghost Note.vst3\Contents\x86_64-win\Ghost Note.vst3"
removing moduleinfo.json
creating [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished/MidiComposer_artefacts/Release/VST3/Ghost Note.vst3/Contents/Resources/moduleinfo.json
[0/2] Re-checking globbed directories...
[0/2] Running tests...
Test project [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished
    Start 1: engine_acceptance
1/3 Test #1: engine_acceptance ................   Passed    3.19 sec
    Start 2: processor_acceptance
2/3 Test #2: processor_acceptance .............   Passed    2.83 sec
    Start 3: ui_acceptance
3/3 Test #3: ui_acceptance ....................   Passed    5.43 sec

100% tests passed out of 3

Total Test time (real) =  11.56 sec
Build and acceptance tests completed: [private workspace]\files-pasted-by-the-user-act\work\MidiComposer\build-polished
```

<a id="document-validation-build-ghost-note-1-1-0-txt"></a>

## validation/build-ghost-note-1.1.0.txt

```text
Sanitized transcript for Ghost Note 1.1.0; local source prefix replaced with <source>.

-- Configuring juceaide
-- Building juceaide
-- Exporting juceaide
-- Testing juceaide
-- Finished setting up juceaide
-- Configuring done (3.6s)
-- Generating done (0.5s)
-- Build files have been written to: <source>/build-polished
-- Configuring done (0.1s)
-- Generating done (0.1s)
-- Build files have been written to: <source>/build-polished/vst3_helpers/MidiComposer
[0/2] Re-checking globbed directories...
[1/7] Generating MidiComposer_artefacts/JuceLibraryCode/MidiComposer_resources.rc
[2/5] Building VST3 manifest helper for MidiComposer
-- Configuring done (0.1s)
-- Generating done (0.2s)
-- Build files have been written to: <source>/build-polished/vst3_helpers/MidiComposer
ninja: no work to do.
[3/5] Building CXX object CMakeFiles\ui_tests.dir\tests\UiTests.cpp.obj
[4/5] Linking CXX executable ui_tests_artefacts\Release\ui_tests.exe
[0/2] Re-checking globbed directories...
[0/2] Running tests...
Test project <source>/build-polished
    Start 1: engine_acceptance
1/4 Test #1: engine_acceptance ................   Passed    2.81 sec
    Start 2: scale_advisor_acceptance
2/4 Test #2: scale_advisor_acceptance .........   Passed    0.39 sec
    Start 3: processor_acceptance
3/4 Test #3: processor_acceptance .............   Passed    2.46 sec
    Start 4: ui_acceptance
4/4 Test #4: ui_acceptance ....................   Passed    8.38 sec

100% tests passed out of 4

Total Test time (real) =  14.73 sec
Build and acceptance tests completed: <source>\build-polished
```

<a id="document-validation-ctest-ghost-note-1-0-0-txt"></a>

## validation/ctest-ghost-note-1.0.0.txt

```text
Sanitized Ghost Note 1.0.0 metadata-corrected verification record — 16 November 2026
VST3 SHA-256: 3a8d83a6417f7f6b4975af5ffd3ad52bc56ae7279bbdf55c32c88f918f144365
Private workspace paths redacted. Original raw log retained privately.

Start testing: Nov 16 14:21 Pacific Standard Time
----------------------------------------------------------
1/3 Testing: engine_acceptance
1/3 Test: engine_acceptance
Command: "[private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished/engine_tests.exe"
Directory: [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished
"engine_acceptance" start time: Nov 16 14:21 Pacific Standard Time
Output:
----------------------------------------------------------
Learned chord-spacing contrast: 33/384 arrangements selected a different compatible voicing; roots and progression stayed unchanged.
West Coast grammar EBK - Dark NorCal Piano: 63 degree sequences, 5 harmonic rhythms, 952 melodies / 1000 fixed-key seeds.
West Coast grammar LA - Modern West Coast: 63 degree sequences, 5 harmonic rhythms, 1000 melodies / 1000 fixed-key seeds.
West Coast grammar Classic G-Funk: 130 degree sequences, 2 harmonic rhythms, 930 melodies / 1000 fixed-key seeds.
West Coast control contrasts /48: darkness harmony 10, register 40, tension 48.
PASS: 4461313 music-engine and MIDI assertions.
<end of output>
Test time =   3.19 sec
----------------------------------------------------------
Test Passed.
"engine_acceptance" end time: Nov 16 14:21 Pacific Standard Time
"engine_acceptance" time elapsed: 00:00:03
----------------------------------------------------------

2/3 Testing: processor_acceptance
2/3 Test: processor_acceptance
Command: "[private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished/processor_tests_artefacts/Release/processor_tests.exe"
Directory: [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished
"processor_acceptance" start time: Nov 16 14:21 Pacific Standard Time
Output:
----------------------------------------------------------
PASS: 5721 processor integration assertions.
<end of output>
Test time =   2.83 sec
----------------------------------------------------------
Test Passed.
"processor_acceptance" end time: Nov 16 14:21 Pacific Standard Time
"processor_acceptance" time elapsed: 00:00:02
----------------------------------------------------------

3/3 Testing: ui_acceptance
3/3 Test: ui_acceptance
Command: "[private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished/ui_tests_artefacts/Release/ui_tests.exe"
Directory: [private workspace]/files-pasted-by-the-user-act/work/MidiComposer/build-polished
"ui_acceptance" start time: Nov 16 14:21 Pacific Standard Time
Output:
----------------------------------------------------------
PASS: 1452 UI label/layout assertions. Actual offscreen renders: [private workspace]\files-pasted-by-the-user-act\work\MidiComposer\build-polished\ui-review
<end of output>
Test time =   5.43 sec
----------------------------------------------------------
Test Passed.
"ui_acceptance" end time: Nov 16 14:21 Pacific Standard Time
"ui_acceptance" time elapsed: 00:00:05
----------------------------------------------------------

End testing: Nov 16 14:21 Pacific Standard Time
```

<a id="document-validation-ctest-ghost-note-1-1-0-txt"></a>

## validation/ctest-ghost-note-1.1.0.txt

```text
Sanitized transcript for Ghost Note 1.1.0; local source prefix replaced with <source>.

Start testing: Nov 18 07:25 Pacific Standard Time
----------------------------------------------------------
1/4 Testing: engine_acceptance
1/4 Test: engine_acceptance
Command: "<source>/build-polished/engine_tests.exe"
Directory: <source>/build-polished
"engine_acceptance" start time: Nov 18 07:25 Pacific Standard Time
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
Test time =   2.81 sec
----------------------------------------------------------
Test Passed.
"engine_acceptance" end time: Nov 18 07:25 Pacific Standard Time
"engine_acceptance" time elapsed: 00:00:02
----------------------------------------------------------

2/4 Testing: scale_advisor_acceptance
2/4 Test: scale_advisor_acceptance
Command: "<source>/build-polished/scale_advisor_tests.exe"
Directory: <source>/build-polished
"scale_advisor_acceptance" start time: Nov 18 07:25 Pacific Standard Time
Output:
----------------------------------------------------------
Advice matrix: 1026 pairs; 752 unrated, 73 experimental, 4 bounded local MIDI; all 12 roots invariant.
PASS: 198071 scale-advisor and actual-generation assertions.
<end of output>
Test time =   0.39 sec
----------------------------------------------------------
Test Passed.
"scale_advisor_acceptance" end time: Nov 18 07:25 Pacific Standard Time
"scale_advisor_acceptance" time elapsed: 00:00:00
----------------------------------------------------------

3/4 Testing: processor_acceptance
3/4 Test: processor_acceptance
Command: "<source>/build-polished/processor_tests_artefacts/Release/processor_tests.exe"
Directory: <source>/build-polished
"processor_acceptance" start time: Nov 18 07:25 Pacific Standard Time
Output:
----------------------------------------------------------
PASS: 5690 processor integration assertions.
<end of output>
Test time =   2.46 sec
----------------------------------------------------------
Test Passed.
"processor_acceptance" end time: Nov 18 07:25 Pacific Standard Time
"processor_acceptance" time elapsed: 00:00:02
----------------------------------------------------------

4/4 Testing: ui_acceptance
4/4 Test: ui_acceptance
Command: "<source>/build-polished/ui_tests_artefacts/Release/ui_tests.exe"
Directory: <source>/build-polished
"ui_acceptance" start time: Nov 18 07:25 Pacific Standard Time
Output:
----------------------------------------------------------
Legacy scale presets: all 38 IDs; exact pitches/velocities/part settings; maximum JSON timing drift 4.44089e-16 host beats.
PASS: 9154 UI label/layout assertions. Actual offscreen renders: <source>\build-polished\ui-review
<end of output>
Test time =   8.38 sec
----------------------------------------------------------
Test Passed.
"ui_acceptance" end time: Nov 18 07:25 Pacific Standard Time
"ui_acceptance" time elapsed: 00:00:08
----------------------------------------------------------

End testing: Nov 18 07:25 Pacific Standard Time
```

<a id="document-validation-pluginval-ghost-note-1-0-0-txt"></a>

## validation/pluginval-ghost-note-1.0.0.txt

```text
Sanitized Ghost Note 1.0.0 metadata-corrected verification record — 16 November 2026
VST3 SHA-256: 3a8d83a6417f7f6b4975af5ffd3ad52bc56ae7279bbdf55c32c88f918f144365
Private workspace paths redacted. Original raw log retained privately.

Started validating: [private workspace]\files-pasted-by-the-user-act\work\MidiComposer\build-polished\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3
Random seed: 0x2bf21
Validation started
Strictness level: 5
-----------------------------------------------------------------
Starting tests in: pluginval / Scan for plugins located in: [private workspace]\files-pasted-by-the-user-act\work\MidiComposer\build-polished\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3...
Num plugins found: 1

Testing plugin: VST3-Ghost Note-cce4111d-fad46c05
TwonOnDaBeat: Ghost Note v1.0.0
Completed tests in pluginval / Scan for plugins located in: [private workspace]\files-pasted-by-the-user-act\work\MidiComposer\build-polished\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3
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

<a id="document-validation-pluginval-ghost-note-1-1-0-txt"></a>

## validation/pluginval-ghost-note-1.1.0.txt

```text
Sanitized transcript for Ghost Note 1.1.0; local source prefix replaced with <source>.

Started validating: <source>\build-polished\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3
Random seed: 0x2bf21
Validation started
Strictness level: 5
-----------------------------------------------------------------
Starting tests in: pluginval / Scan for plugins located in: <source>\build-polished\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3...
Num plugins found: 1

Testing plugin: VST3-Ghost Note-cce4111d-fad46c05
TwonOnDaBeat: Ghost Note v1.1.0
Completed tests in pluginval / Scan for plugins located in: <source>\build-polished\MidiComposer_artefacts\Release\VST3\Ghost Note.vst3
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

