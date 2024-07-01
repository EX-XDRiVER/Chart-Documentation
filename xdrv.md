## EX-XDRiVER Chart Format (.xdrv)

### Chart Metadata

```
// Chart Metadata starts at the top of the .xdrv file.
// Single-Line comments are allowed.

// MUSIC_TITLE, is the song key that you'll be using. Similar to a unique identifier per group/folder.
MUSIC_TITLE=Song Title

// ALTERNATE_TITLE, is the chart specific title that the chart will override the existing MUSIC_TITLE as its name ingame when selected.
// However, any methods that attempt to get the song (via unlocks or other cache related code) will still refer to MUSIC_TITLE.
ALTERNATE_TITLE=Chart Specific Song Title

// MUSIC_ARTIST, is the song's artist or musician name.
MUSIC_ARTIST=Song Artist

// MUSIC_AUDIO, is the file path to the audio file.
MUSIC_AUDIO=audio.ogg

// MUSIC_PREVIEW_START, is the time in seconds of when you should start your music preview in the song wheel.
MUSIC_PREVIEW_START=0

// MUSIC_PREVIEW_LENGTH, is the length of time in seconds of the song preview in the song wheel.
// It will start fading out approximately 2 seconds before the end of the preview.
MUSIC_PREVIEW_LENGTH=10

// MUSIC_VOLUME, is a value between 0 and 1 that determines how loud the song is ingame. Generally, keep this at 1.
MUSIC_VOLUME=1

// MUSIC_OFFSET, is a value in seconds of how offset the song starts compared to the notes.
MUSIC_OFFSET=0


// JACKET_IMAGE, is a filepath to the chart's album art / jacket.
JACKET_IMAGE=jacket.jpg

// JACKET_ILLUSTRATOR, is the name(s) or username(s) of the person who made the album art / jacket for the chart.
JACKET_ILLUSTRATOR=My Jacket Illustrator


// CHART_AUTHOR, is the name(s) or username(s) of the person who made this chart.
CHART_AUTHOR=Me

// CHART_TAGS, is an array of 4 floats, currently unused by the game.
CHART_TAGS=0,0,0,0

// CHART_BOSS, is a boolean, currently unused by the game. May be used in the future for harder lifebars or special content.
CHART_BOSS=FALSE

// CHART_DIFFICULTY, is a string which determines what difficulty slot this chart uses. Can be 'BEGINNER', 'NORMAL', 'HYPER', or 'EXTREME'.
CHART_DIFFICULTY=EXTREME

// CHART_LEVEL, is an integer value between 1 and 15 that determines the level of the chart.
CHART_LEVEL=15

// CHART_UNLOCK, is a file path to an unlock .lua file. More documentation about unlock files in unlocks.md.
CHART_UNLOCK=EXTREME_UNLOCK.lua

// CHART_DISPLAY_BPM, is an integer, and the BPM that shows up in the song wheel. 
CHART_DISPLAY_BPM=120

// CHART_BPM, is a float, and the real starting BPM of the song.
CHART_BPM=120


// FLASH_TRACK, is a boolean that determines if the chart is a flash track. It will use only 1 energy in arcade mode.
// Currently, custom charts are not available in arcade mode.
// Setting this to TRUE will add an icon to the chart in song select.
FLASH_TRACK=FALSE

// KEYBOARD_ONLY, is a boolean that determines if the chart is designed without controllers in mind.
// Setting this to TRUE will add an icon to the chart in song select.
KEYBOARD_ONLY=FALSE

// ORIGINAL, is a boolean that determines if the chart uses original music from EX-XDRiVER.
// Setting this to TRUE will add an icon to the chart in song select.
ORIGINAL=FALSE


// MODFILE_PATH, is a file path to the modfile .lua. More documentation about modfiles in mods.md.
MODFILE_PATH=EXTREME_MODS.lua

// RPC_HIDDEN, is a boolean that determines if the song title and artist name should be hidden on Discord Rich Presence.
// For example, "My Cool Song Title" will become "??????????????????".
RPC_HIDDEN=FALSE

// DISABLE_LEADERBOARD_UPLOADING, is a boolean that disables leaderboards if enabled. This is used for songs like Metronome.
// Currently, custom charts don't have leaderboards, so this is unused.
DISABLE_LEADERBOARD_UPLOADING=FALSE

// STAGE_BACKGROUND, is a string that loads a stage within the game as its background.
// 'default' will fall back to the Tunnel background.
// Alternatively, you can use 'BackgroundTunnel', and 'BackgroundCity' for this field.
STAGE_BACKGROUND=default
```

### Chart Body: Notes
```
// Note Lines are formatted like so:
// 000-000|00|0
// Notes on the left track are the first 3 numeric values.
// Notes on the right track are the second 3 numeric values.
// Gears are the 2 numeric values surrounded by pipe symbols.
// Drifts are indicated by the last numeric value.
//
// All kinds of notes can be in different states:
//
// For the main notes:
// - 0 is an empty space.
// - 1 is a tap note.
// - 2 is the start of a hold. Inbetween the hold 'head' and 'tail', there can only be 0s.
// - 4 is the hold tail, which ends an existing hold.
//
// For gears:
// - 0 is an empty space.
// - 1 is a gear head.
// - 2 is a gear tail.
//
// For drifts:
// - 0 is an empty space.
// - 1 is the start of a left drift.
// - 2 is the start of a right drift.
// - 3 is the end for both kinds of drifts.
//
// To indicate different quantizations of notes (4ths, 8ths, 12ths, 16ths, 24ths, 32nds, 48ths, 64ths, 96ths, 192nds),
// you must separate each beat by a "beat break".
// A beat break is simply two hyphens back to back, like so:
// --
// To tell the game where your chart metadata and chart body are separated, you need to place the first beat break between them.
// For example: Here is a portion of the chart body for Metronome.
//
// .. chart metadata goes here ..
--
000-000|00|0
--
000-000|00|0
--
000-000|00|0
--
000-000|00|0
--
100-000|00|0
--
000-001|00|0
--
100-000|00|0
--
000-001|00|0
--
// end of file
```

### Chart Body: Timing Segments

```
// During a chart, different 'timing segments' can show up in a chart.
// These timing segments are placed on the line before the note row you want to make them occur on.
// For example:
// #BPM=100
// 000-000|00|0
// This will set the chart's current BPM to 100 once it reaches the note row.

// Different timing segments include:
// #BPM
// - Used to indicate a BPM change during a chart to the specified BPM.
// #WARP
// - 'Warps' ahead by the amount of beats specified. Any notes within this region are automatically converted to fakes.
// #STOP
// - Stops the chart for a set amount of beats. (This is converted to seconds by taking the current BPM.)
// #STOP_SECONDS
// - Stops the chart for a set amount of time in seconds.
// #SCROLL
// - Changes the scroll speed of the chart. Affects note positions. Accepts negative values.
// #TIME_SIGNATURE
// - Changes the current time signature. For example, if your time signature is 4/4, you would use #TIME_SIGNATURE=4,4.
// #COMBO_TICKS
// - Sets how often you'll gain combo from holding down a hold or gear.
// - A value of '1' will make it occur once per beat. '2' will occur twice per beat, and so on.
// #COMBO
// - Unused. Used to be a combo multiplier, but is now non-functional.
// #LABEL
// - Labels for strings of text, purely cosmetic, but could be used for mods in the future.
// #FAKE
// - Sets the amount of beats starting at this timing segment to convert all notes within the region into fake notes.
// - Fake notes look identical and cannot be hit, and do not punish the player.
// #EVENT
// - Sends an event to the current stage.
// - Each stage has its own set of events which can control different stage elements, like background lighting.
// - For example, #EVENT=MyEventName,1.0,1,Variable3
// #CHECKPOINT
// - Used to split a chart into sections.
// - Checkpoint times are saved in the play data, and will be used to compare 'splits' during gameplay to show your current pace.
// - Each checkpoint has a name, defined by the chart tag. For example: '#CHECKPOINT=My Checkpoint Name'
// - In each chart, a checkpoint is generated at row 0 with the name 'Start Line'. The name of this checkpoint can be changed by manually defining the checkpoint at row 0.
```

### Example Chart File

```
// Here's an example of a complete .xdrv file.

MUSIC_TITLE=Example XDRV Chart
MUSIC_ARTIST=Song Artist
MUSIC_AUDIO=audio.ogg
MUSIC_PREVIEW_START=0
MUSIC_PREVIEW_LENGTH=10
MUSIC_VOLUME=1
MUSIC_OFFSET=0
JACKET_IMAGE=jacket.jpg
JACKET_ILLUSTRATOR=Jacket Illustrator
CHART_AUTHOR=Chart Author
CHART_TAGS=0,0,0,0
CHART_BOSS=FALSE
CHART_DIFFICULTY=BEGINNER
CHART_LEVEL=1
CHART_UNLOCK=BEGINNER_UNLOCK.lua
CHART_DISPLAY_BPM=120
CHART_BPM=120
MODFILE_PATH=BEGINNER_MODS.lua
RPC_HIDDEN=FALSE
STAGE_BACKGROUND=default
--
000-000|00|0
--
000-000|00|0
--
000-000|00|0
--
000-000|00|0
--
100-000|00|0
--
000-001|00|0
--
100-000|00|0
--
000-001|00|0
--
```
