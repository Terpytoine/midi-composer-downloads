# UI validation

Windows x64 Release VST3-only development build, 1 November 2026. The final recorded CTest run after the musical-variety update passed **3/3 suites**: **97,770 engine assertions**, **2,554 processor integration assertions**, and **857 UI label/layout assertions**. The total recorded suite time was 1.96 seconds.

## Reported defect and correction

The reported dropdown corruption was reproduced by the UI regression test. The first run failed 32 checks because UTF-8 fractions, multiplication signs and separators entered JUCE through narrow ASCII string conversion. An explicit MSVC `/utf-8` setting alone did not resolve that conversion. The corrected source uses explicit UTF-8 conversion at those text boundaries, including dynamic Auto labels and history/favorite separators.

The final test checks the actual ComboBox strings against Unicode code points assembled independently of source-file encoding. It verifies readable Half-Time, Normal and Double-Time labels; U+00BD (one half), U+00BC (one quarter), U+00D7 (multiplication), U+2153 (one third), and U+2159 (one sixth); and the absence of replacement characters and the observed misdecoded sequences. The default selection is **Auto half-time at 177 BPM**, with a separate **half-beat editing grid**. All dropdown items are enumerated recursively, including the inspector inside its viewport.

## Actual rendering and layout checks

The test constructs the real processor and editor, without placing a window on the desktop. `Component::createComponentSnapshot` renders the implemented editor and its actual notes, controls, artwork and candidate state. These images are component renders, not design mockups or FL Studio screenshots.

| Render | Verified scope |
| --- | --- |
| `editor_1000x720.png` | Compact default size. |
| `editor_920x620.png` | Minimum supported size. |
| `editor_1280x850.png` | Enlarged editor size. |
| `editor_1000x720_scale150.png` | Default editor drawing rasterized at 150%, producing a 1500 x 1080 image. |
| `editor_candidate_1000x720.png` | Real generated candidate with active candidate controls. |
| `dropdown-render.png` | Beat Scale, Note Grid and Style items drawn with the editor's actual LookAndFeel and actual menu text. |

At all three logical sizes, the test checks that primary controls fit within the editor, that key/scale/style/loop/beat-scale/seed/generate controls do not overlap, and that the candidate controls and grid do not overlap. It also checks useful piano-roll dimensions. Visual review of the resulting files confirmed clean timing symbols and all three dropdown columns. The popup render checks visible pixel contrast after finishing the graphics context; each sample is clipped to its own popup bounds.

`label-inventory.json` records item text, selected values, Unicode code points and component bounds for each tested size. The test source is `tests/UiTests.cpp`; CTest registers it as `ui_acceptance`. The final raw CTest log is retained with private build validation material.

## Reproducing the renders

Build the project with tests enabled and run the resulting `ui_tests.exe`, optionally with `--output` followed by an absolute review-folder path. With no output argument, it writes an `ui-review` folder beneath its current working directory. The original verified files were generated in `build-polished/ui-review`.

## Scope limits

This pass verifies actual text values, component geometry and rendered appearance under the tested conditions. It does not establish full manual piano-roll usability, keyboard or screen-reader coverage, native popup interaction in FL Studio, or per-monitor Windows DPI transitions. The 150% image is an offscreen raster-scaling check, not a claim that a complete physical-monitor scaling matrix was tested. FL Studio loading, MIDI dragging, multitrack import, live routing and host-project reopening remain separate unperformed host checks, as described in `TESTING.md`.

No desktop input or computer-use automation was used for this validation.
