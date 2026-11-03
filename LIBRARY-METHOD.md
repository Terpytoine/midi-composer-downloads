# Library-informed composition

Ghost Note by TwonOnDaBeat uses an offline procedural engine with bounded statistical guidance from the owner's local MIDI collection. It does not contain an AI model, replay a source phrase, or require access to the original collection at runtime.

## What was analyzed

A recursive, read-only scan found **10,868 MIDI files**. The analysis accepted **2,111 unique pitched track/channel streams**: 193 melody, 64 bass and 1,854 chords. It excluded **649 percussion streams** and placed **6,586 uncertain streams** in a review list. There were 970 exact duplicate files, 141 further structural stream duplicates and 217 parser-review files. Duplicate material does not receive repeated statistical weight.

A mixed MIDI file is evaluated by track and channel. Only accepted pitched streams contribute to the profile; the file is never imported wholesale. Channel 10 identifies percussion. Program information, register, polyphony, simultaneous attacks, pitch variation, note lengths and rhythmic behavior provide additional evidence. Filenames can corroborate that evidence, but cannot establish an accepted role by themselves. Conflicting, sparse, mixed-role, malformed or percussion-like material remains in review. Tuned percussion instruments are not automatically rejected just because of their program name.

The analyzer passed **27 checks**, and its plugin-profile exporter passed **five separate checks**, including normalized histogram shape and chord-voicing gap extraction. All 10,868 original file hashes matched a readback after analysis. The detailed indexes, review manifests and reproducible analysis tools are retained privately with the source backup. No source MIDI files are redistributed.

## How the profile affects a new print

Accepted material supplies aggregate distributions of beat-position attacks, durations, relative melodic intervals, adjacent simultaneous chord-voice gaps and confidently estimated diatonic chord transitions. These influence new rhythmic placement, articulation, movement, compatible harmonic choices and restrained chord spacing. The profile contains no full note sequences or complete source phrases.

Each of the 24 genre profiles retains its own harmonic and rhythmic rules. Genre names inferred from source folders are **unverified hints**. A genre without enough matching observations can use general library phrasing with influence capped at 0.16; the interface distinguishes general patterns from genre-hinted patterns. These statistics do not establish that every source clip or generated idea has verified genre accuracy.

The chord-spacing prior uses a 13-bin histogram of adjacent gaps from accepted simultaneous source voicings, rather than borrowing a melodic-interval histogram. Voice leading, register bounds, compatible chord tones and the selected genre remain dominant. A controlled contrast test changed compatible voicings in 44 of 384 generated arrangements while roots and progression stayed identical. Phrase lengths, density and relationships between source parts were also measured, but not every measured feature is a separate generation model. Only five usable cross-role source pairs were available. Countermelody is therefore composed as an answer to the current melody and shared harmony, rather than being presented as a trained independent source role.

A print shares one key, harmonic timeline, loop duration and phrase structure across Melody, Chords, Countermelody and Bass. An immutable profile snapshot is saved with composition settings so a stored seed can reproduce the same idea even if the factory profile changes later.

## Variety and preservation

Print and New Idea make bounded attempts against recent pitch/rhythm fingerprints. Velocity, sound changes and tiny humanization offsets do not make the same musical structure count as a new idea. Recent suggestions, including discarded candidates, survive project save/restore. Explicit seed replay and locked motifs can intentionally repeat material. This is best effort, not a guarantee of global musical uniqueness.

The original library remains separate from the plugin. Reviewing uncertain files and changing the accepted profile are deliberate development actions; the plugin does not silently scan drives or import quarantined files.

