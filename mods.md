# Modfile Documentation (.lua)

## Mods
<details>
<summary>Mods Documentation and Getting Started</summary>

Mods for a chart are stored in a .lua file! This file is executed at gameplay.
There are two kinds of mod initialization calls, "Mod" and "Ease".

For basic chart mods, first we need to call the container object which stores all of our chart mods.
To call this object's method, we use `xdrv.Mod` or `xdrv.Set`.
The arguments it takes are:
- The mod name
- The value to set the mod to
- Whether to set the mod at a specific beat or time in seconds ('beat' or 'time')
- The beat or time in seconds

Putting this together, we get:
<br>
`xdrv.Mod("speed", 1, "time", 8);`
<br>
OR
<br>
`xdrv.Set("speed", 1, "time", 8);`
<br>
Which sets the mod "speed", to a value of 1, at exactly 8 seconds into the chart.

For eased mods, we need to call `xdrv.Ease`.
The arguments it takes are:
- The mod name
- The starting value
- The ending value
- Whether to set the mod at a specific beat or time in seconds (`'beat'` or `'time'`)
- The beat or time in seconds to start easing our mod
- Whether to set the duration as length or as its ending point, in beat or time in seconds as determined by the fourth parameter (`'end'` or `'len'`)
- The end point of our ease as a beat or time in seconds, or length in beats or time in seconds
- The type of ease to use

The final method call will look like this:
<br>
`xdrv.Ease("speed", 0, 1, "beat", 4, "len", 8, "linear");`
<br>

Which means to ease the "speed" modifier value from 0 to 1, starting at beat 4, for a length of 8 beats with the linear ease type.
</details>

<details>
<summary>Note Mods</summary>
As of 1.4.1, specific notes can have their own mods given to them, called note mods.

To set a note mod, provide the Note Data object or note ID as the first argument in a `xdrv.Set` or `xdrv.Ease` function call.

Example:
- `xdrv.Set(note, "scale_x", 2, "beat", 8);`

To get a Note Data object, you must obtain one via one of these functions:

`xdrv.GetNoteData()`
- Returns every Note Data object in the chart.

`xdrv.GetNoteDataInBeatRange(float startBeat, float endBeat)`
- Returns every Note Data object in the chart within a range of two beats. Does not include the note on the end beat. (Inclusive)

`xdrv.GetNoteDataInTimeRange(float startTime, float endTime)`
- Returns every Note Data object in the chart within a range of two timestamps.

`xdrv.GetNoteDataInDisplayBeatRange(float startDisplayBeat, float endDisplayBeat)`
- Returns every Note Data object in the chart within a range of two display beats.

`xdrv.GetNoteDataOfType(int noteType)`
- Returns every Note Data object in the chart of a specific Note Type in integer form.

`xdrv.GetNoteDataOfTypeInBeatRange(int noteType, float startBeat, float endBeat)`
- Returns every Note Data object in the chart of a specific Note Type in integer form within a range of two beats.

`xdrv.GetNoteDataOfTypeInTimeRange(int noteType, float startTime, float endTime)`
- Returns every Note Data object in the chart of a specific Note Type in integer form within a range of two timestamps.

`xdrv.GetNoteDataOfTypeInDisplayBeatRange(int noteType, float startDisplayBeat, float endDisplayBeat)`
- Returns every Note Data object in the chart of a specific Note Type in integer form within a range of two display beats.

`xdrv.GetNoteDataOfType(string noteTypeString)`
- Returns every Note Data object in the chart of a specific Note Type in string form.

`xdrv.GetNoteDataOfTypeInBeatRange(string noteTypeString, float startBeat, float endBeat)`
- Returns every Note Data object in the chart of a specific Note Type in string form within a range of two beats.

`xdrv.GetNoteDataOfTypeInTimeRange(string noteTypeString, float startTime, float endTime)`
- Returns every Note Data object in the chart of a specific Note Type in string form within a range of two timestamps.

`xdrv.GetNoteDataOfTypeInDisplayBeatRange(string noteTypeString, float startDisplayBeat, float endDisplayBeat)`
- Returns every Note Data object in the chart of a specific Note Type in string form within a range of two display beats.

Each Note Data object has different values which can be used however you like, but cannot be modified.

`ID`
- The integer ID of the note. Note IDs start at 0, and end on the last note of the chart.

`NoteType`
- The integer representation of the note's type. More notes on Note Type below.

`NoteTypeString`
- The string representation of the note's type. More notes on Note Type below.

`Beat`
- The beat of the note.

`Time`
- The time of the note.

`DisplayBeat`
- The display beat of the note, which is the "position" of the note when factoring in `#SCROLL` timing segments.

`BeatLength`
- If the note is a `HoldHead`, `GearLeftHead`, `GearRightHead`, `DriftLeftHead`, or `DriftRightHead`, this is how long the note is active for in beats.

`TimeLength`
- If the note is a `HoldHead`, `GearLeftHead`, `GearRightHead`, `DriftLeftHead`, or `DriftRightHead`, this is how long the note is active for in seconds.

`DisplayBeatLength`
- If the note is a `HoldHead`, `GearLeftHead`, `GearRightHead`, `DriftLeftHead`, or `DriftRightHead`, this is how long the note is active for in display beats.

`Ticks`
- A table of all Hold/Gear ticks in seconds.

`Ignore`
- If the note is a fake, or cannot be hit. `HoldTail`, `GearLeftTail`, `GearRightTail`, `DriftLeftTail`, and `DriftRightTail` notes are always ignored.

`Column`
- The column the note belongs to. Note Columns are 0-5, Gear Columns are 6-7, Drift Column is 8.

`Overlap`
- If this note overlaps with a gear. 

</details>

<details>
<summary>Note Types</summary>

`Invalid` (Type: 0)
- Unused, except if something goes wrong.

`Tap` (Type: 1)
- Tap notes.

`HoldHead` (Type: 2)
- Hold heads. Contains information about how long the hold lasts.

`HoldTail` (Type: 3)
- Hold tails. Always fake/ignored. Essentially a placeholder note with no texture, and should not be used unless you know what you're doing.

`GearLeftHead` (Type: 4)
- Left gear heads. Contains information about how long the gear lasts.

`GearRightHead` (Type: 5)
- Right gear heads. Contains information about how long the gear lasts.

`GearLeftTail` (Type: 6)
- Left gear tails. Always fake/ignored, but has a texture.

`GearRightTail` (Type: 7)
- Right gear tails. Always fake/ignored, but has a texture.

`DriftLeftHead` (Type: 8)
- Left drift heads. Contains information about how long the drift lasts.

`DriftRightHead` (Type: 9)
- Right drift heads. Contains information about how long the drift lasts.

`DriftTail` (Type: 10)
- Unused.

`DriftLeftTail` (Type: 11)
- Left drift tails. Always fake/ignored.

`DriftRightTail` (Type: 12)
- Right drift heads. Always fake/ignored.

`Mine` (Type: 13)
- Mine notes. If pressed, they count as a BREAK, otherwise count as an X-LIMIT. Contains the same information as your standard Tap note.

</details>

<details>
<summary>List of All Chart Mods</summary>

"speed" (Column specific variants: "speedX" where X is 1-9, Aliases: "noteX_speed" where X is 1-9, "gearleft_speed", "gearright_speed", "drift_speed")
- Changes the scroll speed multiplier independent of actual scroll speed.

"brake" (Column specific variants: "brakeX" where X is 1-9, Aliases: "brakeX_speed" where X is 1-9, "gearleft_brake", "gearright_brake", "drift_brake")
- Slows down notes as they get closer to the judge line.

"accel" (Column specific variants: "accelX" where X is 1-9, Aliases: "accelX_speed" where X is 1-9, "gearleft_accel", "gearright_accel", "drift_accel")
- Speeds up notes as they start approaching the judge line.

"camera_position_x" (Alias: "camera_move_x")
- Move the camera along the X axis.

"camera_position_y" (Alias: "camera_move_y")
- Move the camera along the Y axis.

"camera_position_z" (Alias: "camera_move_z")       
- Move the camera along the Z axis.

"camera_rotation_x" (Alias: "camera_rotate_x")       
- Rotate the camera around the X axis.

"camera_rotation_y" (Alias: "camera_rotate_y")       
- Rotate the camera around the Y axis.

"camera_rotation_z" (Alias: "camera_rotate_z")       
- Rotate the camera around the Z axis.

"camera_fov" (Alias: "camera_field_of_view")
- Change the camera's field of view. Only applies to perspective (default) camera. Default: 100, Minimum: 1, Maximum: 179

"camera_size" (Alias: "camera_orthographic_size")
- Change the camera's size. Only applies to orthographic camera. Default: 5, if set to 0, this will be set to 0.01 to avoid errors.

"note_move_x" (Column specific variant: "noteX_move_x" where X is 1-6)
- Move all notes along the X axis.

"note_move_y" (Column specific variant: "noteX_move_y" where X is 1-6)
- Move all notes along the Y axis.

"note_move_z" (Column specific variant: "noteX_move_z" where X is 1-6)
- Move all notes along the Z axis.

"note_rotate_x" (Column specific variant: "noteX_rotate_x" where X is 1-6)
- Rotate the notes around the X axis.

"note_rotate_y" (Column specific variant: "noteX_rotate_y" where X is 1-6)
- Rotate the notes around the Y axis.

"note_rotate_z" (Column specific variant: "noteX_rotate_z" where X is 1-6)
- Rotate the notes around the Z axis.

"note_scale_x" (Column specific variant: "noteX_scale_x" where X is 1-6)
- Changes the scale of the notes along the X axis.

"note_scale_y" (Column specific variant: "noteX_scale_y" where X is 1-6)
- Changes the scale of the notes along the Y axis.

"note_scale_z" (Column specific variant: "noteX_scale_z" where X is 1-6)
- Changes the scale of the notes along the Z axis.

"gear_move_x" (Column specific variants: "gearleft_move_x" and "gearright_move_x")
- Move both gears along the X axis.

"gear_move_y" (Column specific variants: "gearleft_move_y" and "gearright_move_y")
- Move both gears along the Y axis.

"gear_move_z" (Column specific variants: "gearleft_move_z" and "gearright_move_z")
- Move both gears along the Z axis.

"gear_rotate_x" (Column specific variants: "gearleft_rotate_x" and "gearright_rotate_x")
- Rotate both gears around the X axis.

"gear_rotate_y" (Column specific variants: "gearleft_rotate_y" and "gearright_rotate_y")
- Rotate both gears around the Y axis.

"gear_rotate_z" (Column specific variants: "gearleft_rotate_z" and "gearright_rotate_z")
- Rotate both gears around the Z axis.

"gear_scale_x" (Column specific variants: "gearleft_scale_x" and "gearright_scale_x")
- Changes the scale of the gears along the X axis.

"gear_scale_y" (Column specific variants: "gearleft_scale_y" and "gearright_scale_y")
- Changes the scale of the gears along the Y axis.

"gear_scale_z" (Column specific variants: "gearleft_scale_z" and "gearright_scale_z")
- Changes the scale of the gears along the Z axis.

"drift_move_x" (Column specific variants: "driftleft_move_x" and "driftright_move_x")
- Move drift notes along the X axis.

"drift_move_y" (Column specific variants: "driftleft_move_y" and "driftright_move_y")
- Move drift notes along the Y axis.

"drift_move_z" (Column specific variants: "driftleft_move_z" and "driftright_move_z")
- Move drift notes along the Z axis.

"drift_rotate_x" (Column specific variants: "driftleft_rotate_x" and "driftright_rotate_x")
- Rotate drift notes around the X axis.

"drift_rotate_y" (Column specific variants: "driftleft_rotate_y" and "driftright_rotate_y")
- Rotate drift notes around the Y axis.

"drift_rotate_z" (Column specific variants: "driftleft_rotate_z" and "driftright_rotate_z")
- Rotate drift notes around the Z axis.

"drift_scale_x" (Column specific variants: "driftleft_scale_x" and "driftright_scale_x")
- Changes the scale of the drift notes along the X axis.

"drift_scale_y" (Column specific variants: "driftleft_scale_y" and "driftright_scale_y")
- Changes the scale of the drift notes along the Y axis.

"drift_scale_z" (Column specific variants: "driftleft_scale_z" and "driftright_scale_z")
- Changes the scale of the drift notes along the Z axis.

"track_move_x" (Track specific variants: "trackleft_move_x" and "trackright_move_x")
- Move the tracks along the X axis.

"track_move_y" (Track specific variants: "trackleft_move_y" and "trackright_move_y")
- Move the tracks along the Y axis.

"track_move_z" (Track specific variants: "trackleft_move_z" and "trackright_move_z")
- Move the tracks along the Z axis.

"track_rotate_x" (Track specific variants: "trackleft_rotate_x" and "trackright_rotate_x")
- Rotate the tracks around the X axis.

"track_rotate_y" (Track specific variants: "trackleft_rotate_y" and "trackright_rotate_y")
- Rotate the tracks around the Y axis.

"track_rotate_z" (Track specific variants: "trackleft_rotate_z" and "trackright_rotate_z")
- Rotate the tracks around the Z axis.

"track_scale_x" (Track specific variants: "trackleft_scale_x" and "trackright_scale_x")
- Changes the scale of the tracks along the X axis.

"track_scale_y" (Track specific variants: "trackleft_scale_y" and "trackright_scale_y")
- Changes the scale of the tracks along the Y axis.

"track_scale_z" (Track specific variants: "trackleft_scale_z" and "trackright_scale_z")
- Changes the scale of the tracks along the Z axis.

"judgment_line_offset" (Track specific variants: "judgment_line_left_offset" and "judgment_line_right_offset")
- Moves the judgment line up or down the track.

"render_line_offset" (Track specific variants: "render_line_left_offset and "render_line_right_offset")
- Moves the 'render line' up or down the track. Notes will not render past this line.

"black_bar_top_position"   
- Move the top black bar down onto the screen. A value of 1 will completely cover the screen.

"black_bar_bottom_position"    
- Move the bottom black bar up onto the screen. A value of 1 will completely cover the screen.

"black_bar_left_position"   
- Move the left black bar right onto the screen. A value of 1 will completely cover the screen.

"black_bar_right_position"   
- Move the right black bar left onto the screen. A value of 1 will completely cover the screen.

"black_bar_top_rotation"   
- Rotate the top black bar in degrees from 0-360.

"black_bar_bottom_rotation"    
- Rotate the bottom black bar in degrees from 0-360.

"black_bar_left_rotation"   
- Rotate the left black bar in degrees from 0-360.

"black_bar_right_rotation"   
- Rotate the right black bar in degrees from 0-360.

"background_speed_additive" (Alias: "bg_speed_add")
- Manually add background scroll speed.

"background_speed_multiplier" (Alias: "bg_speed_mult")
- Manually multiply background scroll speed.

"lane_color_red" (Alias: "track_color_red")
- Change the track's red color channel. Default value is set to 0.075.

"lane_color_green" (Alias: "track_color_green")
- Change the track's green color channel. Default value is set to 0.075.

"lane_color_blue" (Alias: "track_color_blue")
- Change the track's blue color channel. Default value is set to 0.075.

"lane_color_alpha" (Alias: "track_color_alpha")
- Change the track's alpha color channel. Default value is set to 1.

"lane_left_color_red" (Alias: "track_left_color_red")
- Change the left track's red color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"lane_left_color_green" (Alias: "track_left_color_green")
- Change the left track's green color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"lane_left_color_blue" (Alias: "track_left_color_blue")
- Change the left track's blue color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"lane_left_color_alpha" (Alias: "track_left_color_alpha")
- Change the left track's alpha color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"lane_right_color_red" (Alias: "track_right_color_red")
- Change the right track's red color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"lane_right_color_green" (Alias: "track_right_color_green")
- Change the right track's green color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"lane_right_color_blue" (Alias: "track_right_color_blue")
- Change the right track's blue color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"lane_right_color_alpha" (Alias: "track_right_color_alpha")
- Change the right track's alpha color channel. This is added on top of the color mods for both tracks. Default value is set to 0.

"note_opacity" (Column specific variant: "noteX_opacity" where X is 1-6)
- Change the opacity of notes. Value ranges from 0 to 1.

"gear_opacity" (Track specific variants: "gearleft_opacity" and "gearright_opacity")
- Change the opacity of gears. Value ranges from 0 to 1.

"drift_opacity" (Track specific variants: "driftleft_opacity" and "driftright_opacity")
- Change the opacity of drift notes. Value ranges from 0 to 1.

"note_opacityX" (Where X is 1-9)
- A column specific variant of "note_opacity" for all notes including gears and drifts. Column 9 does not affect left/right drifts independently, but all drift notes.

</details>

<details>
<summary>List of all Note Mods</summary>

"speed"
- Changes the note's scroll speed multiplier independent of actual scroll speed.

"move_x"
- Moves the note along the X axis.

"move_y"
- Moves the note along the Y axis.

"move_z"
- Moves the note along the Z axis.

"rotate_x"
- Rotates the note along the X axis in euler angles.

"rotate_y"
- Rotates the note along the Y axis in euler angles.

"rotate_z"
- Rotates the note along the Z axis in euler angles.

"scale_x"
- Additively scales the note along the X axis. Default: 1

"scale_y"
- Additively scales the note along the Y axis. Default: 1

"scale_z"
- Additively scales the note along the Z axis. Default: 1

"brake"
- Slows down the note as it gets closer to the judge line.

"accel"
- Speeds up the note as it starts approaching the judge line.

"opacity"
- Changes how opaque the note is. Default: 1

</details>

<details>
<summary>List of All Ease Types</summary>

* Linear
* InQuad
* OutQuad
* InOutQuad
* InCubic
* OutCubic
* InOutCubic
* InQuart
* OutQuart
* InOutQuart
* InQuint
* OutQuint
* InOutQuint
* InSine
* OutSine
* InOutSine
* InExpo
* OutExpo
* InOutExpo
* InCirc
* OutCirc
* InOutCirc
* InElastic
* OutElastic
* InOutElastic
* InBack
* OutBack
* InOutBack
* InBounce
* OutBounce
* InOutBounce
* Bounce
* Tri
* Bell
* Pop
* Tap
* Pulse
* Spike
* Inverse
* Instant
* SmoothStep
* SmootherStep
* SmoothestStep

</details>

## Other Functions

### Loading Modfiles within Modfiles

<details>
<summary>Lua Loading Documentation</summary>

As of 1.4.1, you can now call `xdrv.Load` to load a modfile from a modfile! Helpful for collaborations.

Example:
- `xdrv.Load("other_modfile.lua");`

</details>

### Events in Lua

<details>
<summary>Lua Events Documentation</summary>

As of 1.2.0, you can call [Events](https://github.com/EX-XDRiVER/Chart-Documentation/tree/main/backgrounds) from lua files.

The syntax for RunEvent is `xdrv.RunEvent(string eventName, string beatOrTime, float timingValue, params object[] eventValues)`.

Example: `xdrv.RunEvent("SetUIAlphaCurrentSongGroup", "beat", 0, 1, 10);`

This will run the event for setting the alpha for the UI for song metadata and score information's at beat 0, to 1 over the course of 10 beats.

All events, and arguments (including optional ones) are supported.

Additionally, you can call this function with snake_case. Example: `xdrv.run_event`
</details>

### Player Options (Note Color)

<details>
<summary>Note Color Functions Documentation</summary>

As of 1.2.0, you can get the player's note color from a desired column.

`xdrv.GetPlayerNoteColor(int column)` will return a float array containing 4 floats, with red, green, blue, and alpha channels. The values are all ranging from 0 to 1. The provided column index needs to be from 0 to 7.

Additionally, you can get a specific color channel using `xdrv.GetPlayerNoteColorChannel(int column, int index)`, where index needs to be from 0 to 3.

You can also use `xdrv.GetPlayerNoteColorRed(int column)`, `xdrv.GetPlayerNoteColorGreen(int column)`, `xdrv.GetPlayerNoteColorBlue(int column)`, and `xdrv.GetPlayerNoteColorAlpha(int column)`.

Additionally, you can call these functions with snake_case. Example: `xdrv.get_player_note_color`
</details>

### Player Options (Scroll Speed)

<details>
<summary>Scroll Speed Functions Documentation</summary>

You can get a player's scroll speed using `xdrv.GetPlayerScrollSpeed()`. This will return the raw float value that the player has in options. This value has a minimum of 0.5 with no maximum.

Additionally, you can call this function with snake_case. Example: `xdrv.get_player_scroll_speed`
</details>