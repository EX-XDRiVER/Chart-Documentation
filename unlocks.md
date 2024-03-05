### Unlock File Documentation

```
--[[

- All of these functions will execute relating to the chart you are making this unlock condition for:

- This will set the text of the locked chart in song select.
void xdrv.SetUnlockCondition(string text);

- Setting hidden to true will hide the chart from song select instead of showing it as locked. If the chart is unlocked, it is not hidden.
void xdrv.SetHidden(bool hidden);

- In Arcade Mode, this chart will be unlocked if the EX Meter is full.
void xdrv.SetEXMeterExclusive(bool exclusive);

- If the player has cleared the chart, this returns true.
bool xdrv.HasClearedThisChart();

- This will get the player's best medal on the chart, and returns a numeric representation of the medal type.
int  xdrv.GetBestMedal();

- This will get the player's best wings on the chart.
int  xdrv.GetBestWings();

- Compare the player's scores on this chart to the specified score. If the player has a score above or equal to the specified score, this returns true.
bool xdrv.HasMinimumScore(int score);

- Compare the player's scores on this chart to the specified score. If the player has a score below or equal to the specified score, this returns true.
bool xdrv.HasMaximumScore(int score);

- Compare the player's scores on this chart to the specified scores. If the player has a score between or equal to the minimum and maximum scores, this returns true.
bool xdrv.HasScoreInRange(int min, int max);

- Compare the player's scores on this chart to the specified score. If the player has an EX score above or equal to the specified EX score, this returns true.
bool xdrv.HasMinimumEXScore(int score);

- Compare the player's scores on this chart to the specified score. If the player has an EX score below or equal to the specified EX score, this returns true.
bool xdrv.HasMaximumEXScore(int score);

- Compare the player's scores on this chart to the specified scores. If the player has an EX score between or equal to the minimum and maximum EX scores, this returns true.
bool xdrv.HasEXScoreInRange(int min, int max);

- Compare the player's times on this chart to the specified time. If the player has a time above or equal to the specified time in seconds, this returns true.
bool xdrv.HasMinimumClearTime(float time);

- Compare the player's times on this chart to the specified time. If the player has a time below or equal to the specified time in seconds, this returns true.
bool xdrv.HasMaximumClearTime(float time);

- Compare the player's times on this chart to the specified time. If the player has a time between or equal to the specified times in seconds, this returns true.
bool xdrv.HasClearTimeInRange(float min, float max);

- If the player is in arcade mode and has a full EX meter, this returns true. (Custom charts are not available in Arcade Mode.)
bool xdrv.IsEXStageAvailable();

- All of these functions will execute relating to the chart you are looking up:
 - Note 1: Difficulty means 0 = BEGINNER, 1 = NORMAL, 2 = HYPER, 3 = EXTREME.
 - Note 2: The song name must be formatted as such:
  - 'Resources/Neon Circuit/SPEED LIMIT'
   - ..will search only songs in the base game,
   - ..in the 'Neon Circuit' folder,
   - ..for a song named 'SPEED LIMIT'.

  - 'AdditionalSongs/My Folder/Song Name'
   - ..will search only additional songs,
   - ..in the 'My Folder' folder,
   - ..for a song named 'Song Name'.

- If the player has cleared the specified song on ANY difficulty, this returns true.
bool xdrv.HasClearedChartByName(string songName);

- If the player has cleared the specified song and difficulty, this returns true.
bool xdrv.HasClearedChartByNameAndDifficulty(string songName, int difficulty);

- If the player has a score above or equal to the specified score on the specified song and difficulty, this returns true.
bool xdrv.HasMinimumScoreByNameAndDifficulty(string songName, int difficulty, int score);

- If the player has a score below or equal to the specified score on the specified song and difficulty, this returns true.
bool xdrv.HasMaximumScoreByNameAndDifficulty(string songName, int difficulty, int score);

- If the player has a score between or equal to the specified minimum and maximum scores on the specified song and difficulty, this returns true.
bool xdrv.HasScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minScore, int maxScore);

- If the player has an EX score above or equal to the specified EX score on a specified song name and difficulty, this returns true.
bool xdrv.HasMinimumEXScoreByNameAndDifficulty(string songName, int difficulty, int score);

- If the player has an EX score below or equal to the specified EX score on a specified song name and difficulty, this returns true.
bool xdrv.HasMaximumEXScoreByNameAndDifficulty(string songName, int difficulty, int score);

- If the player has a score between or equal to the specified minimum and maximum EX scores on the specified song on the specified difficulty, this returns true.
bool xdrv.HasEXScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minScore, int maxScore);

- If the player has an EX score above or equal to the specified EX score on a specified song name and difficulty, this returns true.
bool xdrv.HasMinimumClearTimeByNameAndDifficulty(string songName, int difficulty, float time);

- If the player has an EX score below or equal to the specified EX score on a specified song name and difficulty, this returns true.
bool xdrv.HasMaximumClearTimeByNameAndDifficulty(string songName, int difficulty, float time);

- If the player has an EX score between or equal to the specified EX scores on a specified song name and difficulty, this returns true.
bool xdrv.HasClearTimeInRangeByNameAndDifficulty(string songName, int difficulty, float minTime, float maxTime);

- Checks if the specified song and difficulty is unlocked. Circular dependencies / excessive chains of this function will give an error and return false.
bool xdrv.IsChartUnlockedByNameAndDifficulty(string songName, int difficulty);

- Gets the best medal the player has on a specified song name and difficulty as a numerical representation.
int  xdrv.GetBestMedalByNameAndDifficulty(string songName, int difficulty);

- Gets the best wings the player has on a specified song name and difficulty as a numerical representation.
int  xdrv.GetBestWingsByNameAndDifficulty(string songName, int difficulty);

Other various functions include:

- Gets the current song count. Includes custom songs.
int  xdrv.GetSongCount();

- Gets the current chart count. Includes custom charts.
int  xdrv.GetChartCount();

- Gets the current unix timestamp.
long xdrv.GetCurrentTimestamp();

- Gets the current player's beaten staff ghost count. Optionally provide a boolean to only count staff ghosts beaten with autodrift off.
int  xdrv.GetBeatenStaffGhostCount(bool autodriftOffOnly)

]]--

-- To set the text for an unlock condition:
xdrv.SetUnlockCondition("My unlock condition text.");

-- returning "true" will unlock the chart.
-- returning "false" will lock the chart.
-- for example:

return true; -- this line will unlock the chart.
```
