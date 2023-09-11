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

// CHART_TAGS, is an array of 4 floats, currently unused by the game. May be used in the future for 'radar values'.
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

// MODFILE_PATH, is a file path to the modfile .lua. More documentation about modfiles in mods.md.
MODFILE_PATH=EXTREME_MODS.lua

// RPC_HIDDEN, is a boolean that determines if the song title and artist name should be hidden on Discord Rich Presence.
// For example, "My Cool Song Title" will become "??????????????????".
RPC_HIDDEN=FALSE

// STAGE_BACKGROUND, is a string that loads a scene within the game as its background.
// Right now 'default' is accepted, which will fall back to 'Gameplay'. Be careful with this value.
// Leave this value blank if you don't know what you're doing!
STAGE_BACKGROUND=default
```
