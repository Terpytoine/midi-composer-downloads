# Ghost Note interface validation

The redesigned interface is the actual JUCE editor for **Ghost Note by TwonOnDaBeat**, v0.2.0-dev. The final extended-scale editor passed its automated checks on 3 November 2026.

Final UI suite: **1,406 passed**. Complete CTest result: **3/3 suites passed in 8.03 seconds**. Earlier v0.1 renders and assertion counts do not verify this redesigned artifact.

## Implemented layout

The main row contains Genre, Key, Scale, Tempo, Complexity and **Print**. Four continuous output rows show Melody, Chords, Countermelody and Bass with actual MIDI miniatures, lock/mute/solo, drag and individual export. A full-width selected-part piano roll carries aligned chords and A/B Keep/Discard controls. Detailed sound, channel, velocity and generation controls open in an Advanced drawer.

The default size is **920 × 650**, minimum **880 × 600**, and the corner can be dragged larger. The header uses original ghost artwork and the exact **GHOST NOTE / by TwonOnDaBeat** credit. Timing displays distinguish Auto/½×/1×/2× musical feel from the separate half-beat editing grid.

## Actual component renders

The test constructs the real processor/editor and uses JUCE `Component::createComponentSnapshot` to render real notes, controls, artwork and candidates without placing a desktop window. These are implemented component renders, not mockups or FL Studio screenshots.

| Render | Scope |
|---|---|
| `editor_920x650.png` | Compact default. |
| `editor_880x600.png` | Minimum supported layout. |
| `editor_1280x850.png` | Enlarged layout. |
| `editor_920x650_scale150.png` | Offscreen 150% raster sample. |
| `editor_candidate_920x650.png` | Actual generated candidate. |
| `editor_advanced_920x650.png` | Advanced drawer open. |
| `dropdown-render.png` | Actual LookAndFeel and dropdown item strings. |

Final visual review: actual default, minimum and Advanced renders were inspected and found readable, clean and within bounds. Test inventories record actual item labels, selections, Unicode code points and component bounds. The suite checks primary-control geometry and useful note-editing dimensions, plus Print/reprint recovery, four populated parts, Complexity, Discard and drawer behavior. The suite enumerated all 38 scale options and checked the selected-state/scale text behavior.

## Text and scope

The prior garbled dropdown issue was traced to UTF-8 text passing through an ASCII conversion. Source compilation and text boundaries now explicitly use UTF-8. Checks compare actual half/quarter/triplet and multiplication symbols against independent Unicode code points and reject observed replacement/misdecoded sequences.

These checks do not establish a complete manual editing session, screen-reader coverage, native popup interaction in FL Studio or per-monitor DPI transitions. The 150% render is not a physical-monitor scaling matrix. FL Studio loading, drag/import, live routing and project reopening remain separate host checks. Reproduce the component renders with `ui_tests.exe --output` and a writable absolute review directory.


