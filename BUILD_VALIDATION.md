# Ghost Note build and independent plugin validation

**Ghost Note by TwonOnDaBeat, v0.2.0-dev — Windows x64.** Final artifact validation completed on 3 November 2026. The results below refer to this v0.2 binary, rather than the earlier MIDI Composer v0.1 artifact.

## Reproducible configuration

- C++17, Release x64, static Microsoft C/C++ runtime.
- JUCE 8.0.16-security, pinned commit `ea77444750de45e036e0279bb0291144bf8e3688`.
- Microsoft MSVC 19.44.35229.0, tools 14.44.35207; Windows SDK 10.0.26100.0.
- CMake 4.4.5 and Ninja 1.13.2 in this development environment.
- Product: complete **Ghost Note by TwonOnDaBeat.vst3** bundle with generated module information. Publisher: **TwonOnDaBeat**.
- VST3 only; no standalone music application. The plugin is unsigned.
- Embedded assets include the original ghost artwork and a bounded statistical library profile. No original library MIDI or compiler tools are runtime dependencies.

MSVC explicitly compiles UTF-8 source. Non-ASCII JUCE labels use explicit UTF-8 conversion. Build instructions and pinned dependencies are in BUILD.md. Configuration is not itself a claim that a final binary passed.

## Final acceptance record

| Evidence | Final v0.2 result |
|---|---|
| Engine/MIDI assertions | 3,932,337 passed |
| Processor integration assertions | 3,354 passed |
| UI workflow/label/layout assertions | 1,406 passed |
| CTest total | 3/3 suites passed in 8.03 seconds |
| Final VST3 binary SHA-256 | d1861a10b020147da90e215918461428a27a4cd5c1e6096a4148c8bc9a631b9c |
| Product/publisher metadata inspection | VST3/PE product: Ghost Note by TwonOnDaBeat; vendor/company: TwonOnDaBeat; version: 0.2.0 |

These suites exercise actual engine, processor and editor code. They cover generation, scale membership, shared harmony, seed/profile replay, exact preservation, timing, MIDI output, malformed project rejection, candidates, editing and state. Simulated transport checks do not constitute an FL Studio host test. Assertion counts measure coverage volume rather than musical quality.

## Independent VST3 validation

Official Tracktion **pluginval v1.0.4** is the build-time validator. The verified downloaded archive SHA-256 was `c08e61ce3b96db41636f8ec7e76f4c7e2c13ebdac7fa1b5a1f52b4f32ec715ab`; the utility is excluded from application downloads.

Final strictness-5 outcome: **SUCCESS**, with GUI lifecycle tests enabled. The recorded run enabled editor creation/destruction, opening the editor while processing and editor automation lifecycle checks. Audio processing covered 44.1, 48 and 96 kHz with 64, 128, 256, 512 and 1024-sample blocks. The log records random seed 0x205d44f. The separate Steinberg validator was skipped because no validator path was configured. A separate Steinberg validator pass is not claimed. A pluginval automation entry does not imply that composition controls expose DAW-automatable parameters.

Private source retains `docs/validation/ctest-ghost-note-final.txt` and `docs/validation/pluginval-ghost-note-final.txt`. These raw records may contain local paths and are excluded from public assets. The hash above identifies the exact tested VST3 binary.

## Separate checks

Installer extraction/CRC and payload hashes are recorded in its own versioned verification report. Actual installation, uninstallation, FL Studio loading, MIDI drag/import, live routing, device listening and physical-monitor behavior are separate checks described in TESTING.md. Code signing, license eligibility, release permissions, publication and remote-backup verification are also separate release steps.


