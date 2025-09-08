# Unlock File Documentation

## Self-Unlock Functions
All of these functions will execute relating to the chart you are making this unlock condition for.

`SetSelectToUnlock(bool state)`
- If this chart is locked, you can press the 'Select' button to unlock it. As long as `SetSelectToUnlock` is true, then it will be unlocked if selected, even if this file returns false.

`SetUnlockCondition(string text)`
- This will set the text of the locked chart in song select.

`SetHidden(bool hidden)`
- Setting hidden to true will hide the chart from song select instead of showing it as locked. If the chart is unlocked, it is not hidden.

`SetEXMeterExclusive(bool exclusive)`
- In Arcade Mode, this chart will be unlocked if the EX Meter is full.

`HasSeenThisChart()`
- Returns true if the player has played this chart in any way. Even if they quit out before finishing.

`HasSeenThisSong()`
- Returns true if the player has played any chart for this song. Even if they quit out before finishing.

`HasPlayedThisChart()`
- Returns true if the player has played this chart, and has play data for it.

`HasPlayedThisSong()`
- Returns true if the player has played any chart for this song, and has play data for any of the charts.

`HasClearedThisChart()`
- Returns true if the player has cleared this chart.

`HasClearedThisSong()`
- Returns true if the player has cleared any chart for this song.

`GetBestScore()`
- This will get the player's best score on the chart.

`GetBestEXScore()`
- This will get the player's best EX score on the chart.

`GetBestMedal()`
- This will get the player's best medal on the chart, and returns a numeric representation of the medal type.

`GetBestWings()`
- This will get the player's best wings on the chart, and returns a numeric representation of the wings type.

`GetGroup()`
- Gets the 'group' this folder is located in. This does NOT include the 'subgroup', only the parent folder.

`GetSubgroup()`
- Gets the 'subgroup' this folder is located in. If this chart is not in a subgroup, this returns `null`.

`GetSongGroup()` (alias: `GetFullGroup()`)
- Gets the current 'group', or folder name that this chart is located in. This includes subfolders.

`SongGroupExists(string group)`
- Returns `true` or `false` if a 'group' or folder name has songs.

`HasMinimumScore(int score)`
- Compare the player's scores on this chart to the specified score. If the player has a score above or equal to the specified score, this returns true.

`HasMaximumScore(int score)`
- Compare the player's scores on this chart to the specified score. If the player has a score below or equal to the specified score, this returns true.

`HasScoreInRange(int min, int max)`
- Compare the player's scores on this chart to the specified scores. If the player has a score between or equal to the minimum and maximum scores, this returns true.

`HasMinimumEXScore(int score)`
- Compare the player's scores on this chart to the specified score. If the player has an EX score above or equal to the specified EX score, this returns true.

`HasMaximumEXScore(int score)`
- Compare the player's scores on this chart to the specified score. If the player has an EX score below or equal to the specified EX score, this returns true.

`HasEXScoreInRange(int min, int max)`
- Compare the player's scores on this chart to the specified scores. If the player has an EX score between or equal to the minimum and maximum EX scores, this returns true.

`IsEXStageAvailable()`
- If the player is in arcade mode and has a full EX meter, this returns true. (Custom charts are not available in Arcade Mode.)

## External Unlock Conditions
All of these functions will execute relating to the chart you are looking up.
- You can find songs with this format: 'Resources/Neon Circuit/SPEED LIMIT'
- Or this format for customs: 'AdditionalSongs/My Folder/Song Name'
- Difficulties are numeric. 0 is BEGINNER, 3 is EXTREME.

`HasSeenSongByName(string songName)` (alias: `HasSeenChartByName(string songName)`)
- Returns true if the specified song on ANY difficulty has been played in any way. Even if the player quits out before finishing.

`HasSeenChartByNameAndDifficulty(string songName, int difficulty)`
- Returns true if the specified chart has been played in any way. Even if the player quits out before finishing.

`HasPlayedSongByName(string songName)` (alias: `HasPlayedChartByName(string songName)`)
- Returns true if the specified song on ANY difficulty has been played, and the player has play data for it.

`HasPlayedChartByNameAndDifficulty(string songName, int difficulty)`
- Returns true if the specified song on the specified difficulty has been played, and the player has play data for it.

`HasClearedSongByName(string songName)` (alias: `HasClearedChartByName(string songName)`)
- If the player has cleared the specified song on ANY difficulty, this returns true.

`HasClearedChartByNameAndDifficulty(string songName, int difficulty)`
- If the player has cleared the specified song and difficulty, this returns true.

`HasMinimumScoreByNameAndDifficulty(string songName, int difficulty, int score)`
- If the player has a score above or equal to the specified score on the specified song and difficulty, this returns true.

`HasMinimumScoreByName(string songName, int score)`
- If the player has a score above or equal to the specified score on the specified song on ANY difficulty, this returns true.

`HasMaximumScoreByNameAndDifficulty(string songName, int difficulty, int score)`
- If the player has a score below or equal to the specified score on the specified song and difficulty, this returns true.

`HasMaximumScoreByName(string songName, int score)`
- If the player has a score below or equal to the specified score on the specified song on ANY difficulty, this returns true.

`HasScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minScore, int maxScore)`
- If the player has a score between or equal to the specified minimum and maximum scores on the chart, this returns true.

`HasMinimumEXScoreByNameAndDifficulty(string songName, int difficulty, int score)`
- If the player has an EX score above or equal to the specified EX score on the specified chart, this returns true.

`HasMaximumEXScoreByNameAndDifficulty(string songName, int difficulty, int score)`
- If the player has an EX score below or equal to the specified EX score on the chart, this returns true.

`HasEXScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minScore, int maxScore)`
- If the player has a score between or equal to the specified minimum and maximum EX scores on the specified chart, this returns true.

`IsChartUnlockedByNameAndDifficulty(string songName, int difficulty)`
- Checks if the specified song and difficulty is unlocked. Circular dependencies / excessive chains of this function will give an error and return false.

`GetBestScoreByNameAndDifficulty(string songName, int difficulty)`
- Gets the best score the player has on the specified chart.

`GetBestEXScoreByNameAndDifficulty(string songName, int difficulty)`
- Gets the best EX score the player has on the specified chart.

`GetBestMedalByNameAndDifficulty(string songName, int difficulty)`
- Gets the best medal the player has on the specified chart as a numerical representation.

`GetBestWingsByNameAndDifficulty(string songName, int difficulty)`
- Gets the best wings the player has on the specified chart as a numerical representation.

## Chart Omittance
These functions apply to the chart this unlock file is for, and only apply to the song wheel. These settings do not show in gameplay.

`OmitTitle(bool omit, string optionalText)`
- Replaces the song title with '??????' relative to how many characters are in the song title. Optionally provide a string of text to replace the song title with.

`OmitSubtitle(bool omit, string optionalText)`
- Replaces the subtitle with '??????' relative to how many characters in the subtitle. Optionally, provide a string of text to replace the subtitle with.

`OmitCredit(bool omit, string optionalText)`
- Replaces the song credit field with '??????' relative to how many characters are in the song credit field. Optionally, provide a string of text to replace the song credit with.

`OmitArtist(bool omit, string optionalText)`
- Replaces the song artist field with '??????' relative to how many characters are in the song artist field. Optionally, provide a string of text to replace the song artist with.

`OmitIllustrator(bool omit, string optionalText)`
- Replaces the jacket illustrator field with '??????' relative to how many characters are in the jacket illustrator field. Optionally, provide a string of text to replace the jacket illustrator field with.

`OmitAuthor(bool omit, string optionalText)`
- Replaces the chart author field with '??????' relative to how many characters are in the chart author field. Optionally, provide a string of text to replace the chart author field with.

`OmitDifficulty(bool omit)`
- Replaces the chart difficulty with '?'.

`OmitDisplayBPM(bool omit)`
- Replaces the display BPM with '???'.

`OmitJacket(bool omit)`
- Replaces the chart jacket with the default.

`OmitChartIcons(bool omit)`
- Hides the chart icons.

`OmitMusicPreview(bool omit)`
- Does not play the music preview when selected in the song wheel.

`OmitRadarValues(bool omit)`
- Hides the radar values for this chart.

## Various Functions

`GetSongCount()`
- Gets the current song count. Includes custom songs.

`GetChartCount()`
- Gets the current chart count. Includes custom charts.

`GetCurrentTimestamp()`
- Gets the current unix timestamp.

`GetBeatenStaffGhostCount(bool autodriftOffOnly)`
- Gets the current player's beaten staff ghost count. Optionally provide a boolean to only count staff ghosts beaten with autodrift off.

`GetChartCountInGroupAndDifficulty(string group, int difficulty, (optional) bool includeSubfolders)`
- Gets the amount of charts in a folder, on a specific difficulty.

`GetChartCountInGroup(string group, (optional) bool includeSubfolders)`
- Gets the amount of charts in a folder.

`GetSongCountInGroup(string group, (optional) bool includeSubfolders)`
- Gets the amount of songs in a folder.

`GetClearedChartCountInGroupAndDifficulty(string group, int difficulty, (optional) bool includeSubfolders)`
- Gets the amount of cleared charts in a folder, on a specific difficulty.

`GetClearedChartCountInGroup(string group, (optional) bool includeSubfolders)`
- Gets the amount of cleared charts in a folder.

`GetClearedSongCountInGroup(string group, (optional) bool includeSubfolders)`
- Gets the amount of cleared songs in a folder.

`GetSteamID()`
- Gets the player's current Steam User ID.

`GetGamemode()`
- Gets the current gamemode.

`HasEXOnLevel(int difficulty)`
- Returns true if the player has an EX grade on any chart on the specified difficulty, only works on charts in the base game.

## Redirects

`RedirectChart(bool redirect, bool hideStats, string lookup, int difficulty)`
- Redirects this chart to another chart based on the lookup string and difficulty.
  - Does NOT display the play data of the redirected chart on this chart.
  - Providing 'true' for the 'hideStats' bool will scramble the best score, EX, and gauges on the UI.

`BlockRedirects(bool block)
- Prevents any chart from redirecting to this one.

## Example

To set the text for an unlock condition: `xdrv.SetUnlockCondition("My unlock condition text.");`

`return true;` will unlock the chart, and `return false;` will lock the chart.
