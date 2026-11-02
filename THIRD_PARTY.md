# Dependencies, licensing and sound origins

## Application and sounds

Project-specific music generation, MIDI writing, scheduling, UI, state management and eight preview synthesis algorithms were created for this project. No artist recording, existing song MIDI, sample pack or commercial preset library is embedded. All preview sounds use original oscillator/envelope formulas: soft piano-like additive decay, electric-piano-like FM, nylon-like harmonic pluck, short muted pluck, inharmonic FM bell, bright pluck, slow sine pad and sine sub bass. Names describe approximations; they are not claims of realistic multisampled acoustic instruments. The generator is procedural, with no AI-model integration.

No public license is granted to project-specific source by the private development package. The owner should choose the final proprietary license/EULA and legal identity before public distribution. Third-party licenses remain separate.

## JUCE

Pinned framework: **JUCE 8.0.16-security**, commit `ea77444750de45e036e0279bb0291144bf8e3688`. The exact framework license is retained with the package. Source: [official JUCE repository](https://github.com/juce-framework/JUCE).

JUCE licensing was checked against the [current official JUCE 8 EULA](https://juce.com/legal/juce-8-licence/) during this development session. It offers Starter, Indie, Pro and Educational tiers; commercial eligibility depends on the owner's revenue/funding and required contributor seats. Starter currently has a $20,000 annual revenue/funding limit; Indie $300,000; Pro no limit. Educational is restricted to qualifying educational/research use. Do not infer the owner qualifies for a particular tier. Before closed-source public distribution, the owner must establish the applicable license, seats and distribution rights under those terms, or obtain an appropriate alternative license. The session does not purchase, assign or certify the owner's JUCE license.

On 1 November 2026, the owner confirmed: **“I use or qualify for JUCE Starter (within its revenue/funding limit).”** This is an owner-provided confirmation for the planned closed-source release, not an independent audit, license purchase or certification by the development agent. The owner remains responsible for continuing eligibility, applicable contributor seats, and compliance with the official terms.

The version pin is a reproducibility measure, not a guarantee that dependencies have no security defects. Review upstream security updates before release.

## VST3

The exact VST3 SDK bundled in the pinned JUCE tree uses the MIT license; its license text must accompany distribution. [Steinberg's current VST SDK page](https://www.steinberg.net/developers/vstsdk/) states VST technology is available under MIT and does not require disclosure of product source. Steinberg trademarks and optional logos have separate usage rules; this build does not add a Steinberg logo.

## Other framework notices

JUCE includes third-party code and notices in its modules. The binary package retains applicable notice files in its third-party-licenses folder. Build options disable ASIO, web browser integration, curl, FLAC, Ogg/Vorbis and MP3 decoding. Review the compiled dependency inventory and all applicable notices before public release.

Windows system libraries and compiler runtimes have their own applicable terms. Portable build tools are development dependencies; they are not part of the runtime sound palette and should not be uploaded with public application downloads. See BUILD.md for exact tools and provenance.

## Original visual artwork

The ink-and-copper sonic-sculpture artwork was generated specifically for this project with the built-in image_gen tool and embedded as an application resource. No external reference image, stock-photo license or artist asset was used. See ARTWORK.md for the full final prompt and saved source-asset path. Do not claim that generated artwork has been trademark cleared or that a final product brand has been selected.
