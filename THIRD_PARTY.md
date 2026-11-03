# Dependencies, licensing and sound origins

## Product, library patterns and preview sounds

Ghost Note by TwonOnDaBeat contains project-specific procedural music generation, MIDI writing, scheduling, interface and state code. It operates offline without an AI-model service.

The library-informed profile contains bounded aggregate statistics derived from accepted pitched material in the owner's collection. No original library MIDI files, full source phrases, recordings, samples or commercial preset banks are embedded or redistributed. Review lists and original source files remain separate. **LIBRARY-METHOD.md** describes classification, duplicate handling, weak genre hints and the limits of those statistics. Aggregate guidance and repeat checks do not guarantee that a phrase is globally unique.

The eight preview voices use original oscillator/envelope formulas: soft piano-like additive decay, electric-piano-like FM, nylon-like harmonic pluck, short muted pluck, inharmonic FM bell, bright pluck, slow sine pad and sine sub bass. Their names describe synthesized approximations, not realistic multisampled acoustic instruments. Exported MIDI contains no preview audio; receiving instruments determine final tone and glide.

Project-specific source remains private and no open-source license is granted to it by the binary download. Third-party notices have their own terms. **TwonOnDaBeat** is the product/publisher credit requested by the owner; this document does not certify brand-name availability.

## JUCE

The framework is **JUCE 8.0.16-security**, pinned commit `ea77444750de45e036e0279bb0291144bf8e3688`, from the [official JUCE repository](https://github.com/juce-framework/JUCE). Its exact bundled license is included as JUCE-LICENSE.md. Closed-source distribution requires the applicable JUCE license and continuing eligibility under the [official JUCE 8 terms](https://juce.com/legal/juce-8-licence/).

During this development session, the owner confirmed: **“I use or qualify for JUCE Starter (within its revenue/funding limit).”** This is owner-provided confirmation, not an independent licensing audit, license purchase or certification. The owner remains responsible for continuing eligibility, any required contributor seats and compliance. The version pin supports reproducibility; it does not guarantee absence of dependency defects.

## VST3 and installer

The exact VST3 SDK bundled with the pinned JUCE tree uses the MIT license, retained as VST3-SDK-LICENSE.txt. [Steinberg's VST SDK information](https://www.steinberg.net/developers/vstsdk/) describes its licensing. Steinberg marks/logos have separate usage rules; this build adds no Steinberg logo.

The offline EXE installer is built using NSIS 3.12. Its notice accompanies the installer. Build tools and compiler packages are development dependencies and are excluded from application downloads. Windows system libraries and compiler runtimes retain their own terms.

## Other notices and scale facts

Applicable JUCE module notices are retained in the package's `third-party-licenses` folder, including zlib, libpng, libjpeg, HarfBuzz and SheenBidi. Build options disable ASIO, browser integration, curl and optional FLAC/Ogg/MP3 decoding. Recheck the compiled dependency inventory before distribution.

The scale catalog records numeric pitch-class formulas audited from installed FL Studio reference scores, plus standard Chromatic. No proprietary FSC score file, Image-Line logo or vendor interface artwork is bundled. Named scale traditions can have multiple variants; these formulas follow the audited installation. Cymatics and Unison tools served as workflow references; their code, interface assets and sound libraries are not included.

## Original visual artwork

The new manuscript-paper ghost artwork was generated specifically for this project with the built-in image generation tool and no external reference. See ARTWORK.md and GHOST-NOTE-ARTWORK.md for the saved asset, final prompt and provenance. Generated artwork and naming checks do not establish exclusive trademark rights.
