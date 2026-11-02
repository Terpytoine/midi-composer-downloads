# Build and independent plugin validation

Development validation performed on Windows x64, 1 November 2026. These results cover the binaries built in this workspace; they do not certify every computer, audio device, or DAW.

## Actual build

- JUCE 8.0.16-security, exact commit `ea77444750de45e036e0279bb0291144bf8e3688`.
- Microsoft MSVC 19.44.35229.0, tools folder 14.44.35207; Windows SDK 10.0.26100.0.
- CMake 4.4.5, Ninja 1.13.2; Release x64, C++17, static Microsoft C/C++ runtime.
- Final product target: the complete `MIDI Composer Dev.vst3` bundle, including generated VST3 module information. The owner changed the scope to VST3 only; earlier standalone artifacts are excluded from delivery.
- The plugin is an unsigned development build. No certificate or signing key was present or used.
- PE dependency inspection found Windows system libraries only; no separate VC++ runtime DLL or LLVM runtime DLL is required by the plugin.
- The independent standard C++ engine also compiled and passed its tests with LLVM-MinGW clang 23.1.4. JUCE itself explicitly rejects MinGW; the delivered app and VST3 use MSVC.

## Automated acceptance checks actually run

The final musical-variety and recent-pattern-avoidance build in `build-polished` completed `ctest`: **3 of 3 suites passed**, total 1.96 seconds for the final recorded run. The suites reported:

| Suite | Result |
| --- | --- |
| Engine and MIDI assertions | 97,770 passed |
| Processor integration assertions | 2,554 passed |
| Interface label/layout assertions | 857 passed |

These include seeded generation, scale membership, shared harmony, chord-layer register behavior, exact lock preservation, partial and advanced regeneration, eight-host-bar timing, Type 1 MIDI structure and loop endings, candidate recovery, editing and undo, project serialization/restoration, malformed input rejection, simulated host transport, note timing/duration, stop/seek/loop behavior, and finite synthesized preview output. The tests exercise actual engine and processor code; the simulated host is not FL Studio.

The interface suite verifies exact Unicode code points, readable dropdown text, primary-control bounds and overlap at 920×620, 1000×720 and 1280×850, plus actual editor renders including a 150% raster sample. It caught and drove correction of the reported garbled text. `UI_VALIDATION.md` records this narrower rendering scope. Compiler flags explicitly select UTF-8; non-ASCII JUCE labels use explicit UTF-8 conversion.

Assertion counts show coverage volume, not a score for musical quality. Listening, usability, and actual host integration need their own assessment.

The final tests also cover musical variety and recent-pattern avoidance. For each of the six styles, at least 48 of 64 tested seeds produced different melody structures, while the same seed/settings remained reproducible. Processor checks generated 24 distinct successive melody ideas even when candidates were discarded, then eight more after saving and restoring the project. The policy retries New Idea up to 32 times against up to 64 recent pitch/onset fingerprints per role and arrangement. Its fingerprint rounds onsets to 1/12 beat and excludes velocity, sound, gain, note gate and tiny humanization changes. Default instances start with fresh seeds; explicitly requested seeds reproduce an idea. This is a bounded best-effort aid, not a guarantee of global originality or of different results under every constraint.

## Independent VST3 loading and lifecycle checks

Official Tracktion **pluginval v1.0.4** was downloaded as a build-time test utility. Its archive SHA-256 was `c08e61ce3b96db41636f8ec7e76f4c7e2c13ebdac7fa1b5a1f52b4f32ec715ab`. The utility is excluded from the application package.

pluginval strictness **5**, random seed **21473**, completed with **SUCCESS** on the final VST3. GUI checks were enabled in the final run. Its log explicitly includes:

- Editor creation and destruction.
- Opening the editor while processing.
- Editor automation lifecycle checks.
- Plugin state and audio processing at 44.1, 48, and 96 kHz, with 64, 128, 256, 512, and 1024 sample blocks.
- Bus discovery, enable/disable, and layout restoration.

The separate Steinberg validator step was **skipped** because no separate Steinberg validator executable was configured. No Steinberg-validator pass is claimed. No host-automatable musical parameters are currently exposed; a pluginval automation test entry is not a claim that those controls support DAW automation.

Private source includes raw logs in `docs/validation/`. Those logs contain local paths and are intentionally excluded from the public-download packaging recipe.

Final evidence files are `ctest-polished-final.txt` and `pluginval-freshness-final.txt`. The latter completed with SUCCESS after the musical-variety update. The final VST3 binary has SHA-256 `08f1d201ad024df77629a06e32b06318dae87cb7db0f2f579f89b75092e967ef`. The plugin was loaded from `build-polished`, after the artwork, text-conversion and recent-pattern fixes; earlier logs remain as development evidence only.

## Checks still separate

FL Studio scanning, MIDI drag-and-drop, multitrack import, live routing, audible device playback, display scaling, and user interaction are reported in `TESTING.md`. Passing pluginval does not establish those results. Public release permissions, repository protections, closed-source license eligibility, code signing, and release publication are separate release steps.
