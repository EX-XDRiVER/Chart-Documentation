### Unlock File Documentation

```
--[[

All of these functions will execute relating to the chart you are making this unlock condition for:

void xdrv.SetUnlockCondition(string text);
void xdrv.SetHidden(bool hidden);
void xdrv.SetEXMeterExclusive(bool exclusive);

bool xdrv.HasClearedThisChart();
int  xdrv.GetBestMedal();
int  xdrv.GetBestWings();
bool xdrv.HasMinimumScore(int score);
bool xdrv.HasMaximumScore(int score);
bool xdrv.HasScoreInRange(int min, int max);
bool xdrv.HasMinimumEXScore(int score);
bool xdrv.HasMaximumEXScore(int score);
bool xdrv.HasEXScoreInRange(int min, int max);
bool xdrv.HasMinimumClearTime(float time);
bool xdrv.HasMaximumClearTime(float time);
bool xdrv.HasClearTimeInRange(float min, float max);
bool xdrv.IsEXStageAvailable();

All of these functions will execute relating to the chart you are looking up:
 - Note 1: Difficulty means 0 = BEGINNER, 1 = NORMAL, 2 = HYPER, 3 = EXTREME.
 - Note 2: The song name must be formatted in one of two ways:
  - 1: 'Resources/' or 'AdditionalSongs/' will limit the search..
   - ..to only resources or additional songs.
   - ..Leaving this out will check both.
  - 2: 'Folder Name/' will search for a song in a specific folder.
  - 3: 'Song Name' will get the song by its name.

  - For example: 'AdditionalSongs/My Folder/Song Name'
   - ..will search only additional songs,
   - ..in the 'My Folder' folder,
   - ..for a song named 'Song Name'.

  - Alternatively: 'My Folder/Song Name'
   - ..will search both additional songs and resources,
   - ..in the 'My Folder' folder,
   - ..for a song named 'Song Name'.
 - Note 3: If multiple charts are a match, it will check both of them.
  - (If at least one is met, the condition succeeds.)

bool xdrv.HasClearedChartByName(string songName);
bool xdrv.HasClearedChartByNameAndDifficulty(string songName, int difficulty);
bool xdrv.HasMinimumScoreByNameAndDifficulty(string songName, int difficulty, int score);
bool xdrv.HasMaximumScoreByNameAndDifficulty(string songName, int difficulty, int score);
bool xdrv.HasScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minScore, int maxScore);
bool xdrv.HasMinimumEXScoreByNameAndDifficulty(string songName, int difficulty, int score);
bool xdrv.HasMaximumEXScoreByNameAndDifficulty(string songName, int difficulty, int score);
bool xdrv.HasEXScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minScore, int maxScore);
bool xdrv.HasMinimumClearTimeByNameAndDifficulty(string songName, int difficulty, float time);
bool xdrv.HasMaximumClearTimeByNameAndDifficulty(string songName, int difficulty, float time);
bool xdrv.HasClearTimeInRangeByNameAndDifficulty(string songName, int difficulty, float minTime, float maxTime);
bool xdrv.IsChartUnlockedByNameAndDifficulty(string songName, int difficulty);
 - Use the above function with caution. Circular dependencies WILL crash the game at the moment.
int  xdrv.GetBestMedalByNameAndDifficulty(string songName, int difficulty);
int  xdrv.GetBestWingsByNameAndDifficulty(string songName, int difficulty);

Other various functions include:

int  xdrv.GetSongCount();
int  xdrv.GetChartCount();
long xdrv.GetCurrentTimestamp();

]]--

-- To set the text for an unlock condition:
xdrv.SetUnlockCondition("My unlock condition text.");

-- returning "true" will unlock the chart.
-- returning "false" will lock the chart.
-- for example:

return true; -- this line will unlock the chart.
```
