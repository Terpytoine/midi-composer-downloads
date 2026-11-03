# Ghost Note by TwonOnDaBeat

A compact, offline music printer for Windows and FL Studio. Choose Genre, Key, Scale, Tempo and Complexity, then press **Print** for connected Melody, Chords, Countermelody and Bass.

## Download

**[Download the Windows VST3 installer](https://github.com/Terpytoine/midi-composer-downloads/releases/download/v0.2.0-dev/Ghost-Note-VST3-Setup-0.2.0-dev-Windows.exe)**

The EXE installs the VST3 instrument. This is an **unsigned development prerelease** for Windows 10/11 x64; no standalone music app is included.

1. Close hosts using Ghost Note, run the installer and follow the short wizard.
2. In FL Studio, open **Options → Manage plugins → Find installed plugins**.
3. Look for **Ghost Note by TwonOnDaBeat**, manufacturer **TwonOnDaBeat**.

The installer uses the standard Common Files VST3 folder and leaves FL Studio's saved settings unchanged. A raw VST3 ZIP is also available. See [installation details](INSTALLER.md), [verification results](TESTING.md) and the release checksums.

![Ghost Note interface](Plugin-Preview.png)

## Print, audition, keep

Four coordinated parts arrive together. Compare your saved A idea with the new B print, then Keep or Discard. Print again to explore; the previous print remains in Ideas. Lock favorite parts, vary another part, edit notes, and drag or export each part's MIDI. **Advanced** reveals detailed controls without filling the main workspace.

The resizable window starts at **920 × 650**. There are **24 genre profiles**, all **12 roots**, and **38 scale options**: the 37 audited FL Studio reference formulas plus Chromatic. Strict Scale constrains generated and edited pitches.

At **180 BPM**, select **1×** for a 180 BPM feel or **½×** for a 90 BPM feel. Both still fill **eight host bars / 32 beats / 10.67 seconds**. Auto suggests a feel; manual choices override it. **Grid: ½ beat** controls editing snap separately.

The engine combines genre-specific musical rules with bounded aggregate library patterns. Source MIDI files and uncertain material are not distributed. See [how the library informs generation](LIBRARY-METHOD.md). Recent-pattern checks help avoid repeats, while explicit seeds can reproduce an idea. Variety is best effort, not a promise of global uniqueness.

## Source, sound and validation

Official source remains private and owner-controlled. Users can tweak plugin settings and generated MIDI without receiving permission to change official source or publish official updates. Distributed copies can still be modified; no security guarantee is implied.

The engine runs offline and has no AI-model service or account requirement. Eight original synthesized preview sounds provide audition audio; exported MIDI uses the instruments you choose in FL Studio. [Third-party notices and sound origins](THIRD_PARTY.md) accompany the download.

[TESTING.md](TESTING.md), [BUILD_VALIDATION.md](BUILD_VALIDATION.md), [UI_VALIDATION.md](UI_VALIDATION.md) and the separate installer record distinguish actual checks from remaining host tests. A component render or installer integrity check does not prove FL Studio routing or physical-device behavior.
