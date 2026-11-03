# Install Ghost Note by TwonOnDaBeat

Run **Ghost-Note-VST3-Setup-0.2.0-dev-Windows.exe** to install the Windows x64 VST3. This EXE is the installer; the instrument runs inside FL Studio or another VST3 host.

1. Close any host using an existing Ghost Note instance before installing or updating it.
2. Open the EXE, approve the normal Windows administrator prompt, and follow the short wizard.
3. Open FL Studio and choose **Options → Manage plugins → Find installed plugins**.
4. Look for **Ghost Note by TwonOnDaBeat**. Its manufacturer is **TwonOnDaBeat**. Load it as an instrument.

The complete bundle is installed at:

`C:\Program Files\Common Files\VST3\Ghost Note by TwonOnDaBeat.vst3`

The installer uses the standard 64-bit VST3 location and leaves FL Studio's saved settings unchanged. FL Studio may need a rescan before the renamed instrument appears. If you previously loaded the temporary MIDI Composer Dev build, select the new Ghost Note entry for new sessions. This installer does not delete the earlier development bundle. See Image-Line's [plugin installation guide](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/basics_externalplugins.htm) for the host's scanning workflow.

Choose a genre, key and complexity, then press **Print**. Each print contains Melody, Chords, Countermelody and Bass. Drag a part's **Drag MIDI** handle into FL Studio or use its **Export** button. The receiving FL Studio instrument supplies the sound for exported MIDI.

Host sync follows FL Studio's tempo. At 180 BPM, **½×** provides a 90 BPM musical feel while the default MIDI loop still fills eight host bars / 32 beats / approximately 10.67 seconds. **1×** uses faster phrasing in the same host duration. **Auto** suggests a feel, and you can override it. The separate editing grid defaults to **½ beat**.

The documentation and uninstaller are installed in:

`C:\Program Files\Ghost Note by TwonOnDaBeat`

To remove it, close hosts using Ghost Note and choose **Ghost Note by TwonOnDaBeat VST3** in Windows **Settings → Apps → Installed apps → Uninstall**. The uninstaller removes only manifest-listed product files and empty product folders. Other plugins, FL Studio projects and your exported MIDI are outside its removal list.

The plugin operates offline. No standalone music app, library MIDI files, compiler tools or signing credentials are included in the installer. Only bounded statistical patterns derived from accepted library material are embedded; uncertain and percussion material are excluded from that profile. The source remains private.

This development build is **unsigned**. Verify its SHA-256 against the published checksum. Installer extraction and payload verification are documented separately from actual installation and FL Studio host checks; see the final validation reports for which checks were performed.