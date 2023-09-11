### Unlock File Documentation

```
--[[

Available methods in the "xdrv" object include:

int xdrv.GetSongCount();
int xdrv.GetChartCount();
long xdrv.GetCurrentTimestamp();
bool xdrv.SetUnlockCondition(string text);

All of these functions will execute relating to the chart you are making this unlock condition for:

bool xdrv.HasClearedThisChart();
int xdrv.GetBestMedal();
int xdrv.GetBestWings();

bool xdrv.HasMinimumScore(int score);
bool xdrv.HasMaximumScore(int score);
bool xdrv.HasScoreInRange(int minScore, int maxScore);

bool xdrv.HasMinimumEXScore(int exScore);
bool xdrv.HasMaximumEXScore(int exScore);
bool xdrv.HasEXScoreInRange(int minExScore, int maxExScore);

bool xdrv.HasMinimumClearTime(float timeSeconds);
bool xdrv.HasMaximumClearTime(float timeSeconds);
bool xdrv.HasClearTimeInRange(float minClearTime, float maxClearTime);

All of these functions will execute relating to the chart you are looking up:
 - Note 1: Difficulty means 0 = BEGINNER, 1 = NORMAL, 2 = HYPER, 3 = EXTREME.
 - Note 2: The song name is NOT case sensitive.
 - Note 3: If multiple charts are a match, it will check both of them. (If at least one is met, the condition succeeds.)

bool xdrv.HasClearedChartByNameAndDifficulty(string songName, int difficulty);
bool xdrv.HasClearedChartByNameAndDifficultyResourcesOnly(string songName, int difficulty); - May get replaced. Filters any songs in additional song folders out.
bool xdrv.HasClearedChartByNameAndDifficultyAdditionalSongsOnly(string songName, int difficulty); - May get replaced. Filters any songs in resources (the base game) out.

bool xdrv.HasMinimumScoreByNameAndDifficulty(string songName, int difficulty, int score);
bool xdrv.HasMaximumScoreByNameAndDifficulty(string songName, int difficulty, int score);
bool xdrv.HasScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minScore, int maxScore);

bool xdrv.HasMinimumEXScoreByNameAndDifficulty(string songName, int difficulty, int exScore);
bool xdrv.HasMaximumEXScoreByNameAndDifficulty(string songName, int difficulty, int exScore);
bool xdrv.HasEXScoreInRangeByNameAndDifficulty(string songName, int difficulty, int minExScore, int maxExScore);

bool xdrv.HasMinimumClearTimeByNameAndDifficulty(string songName, int difficulty, float time);
bool xdrv.HasMaximumClearTimeByNameAndDifficulty(string songName, int difficulty, float time);
bool xdrv.HasClearTimeInRangeByNameAndDifficulty(string songName, int difficulty, float minTimeSeconds, float maxTimeSeconds);

bool xdrv.IsChartUnlockedByNameAndDifficulty(string songName, int difficulty);

]]--

-- To set the text for an unlock condition:
xdrv.SetUnlockCondition("My unlock condition text.");

-- returning "true" will unlock the chart.
-- returning "false" will lock the chart.
-- for example:

return true; -- this line will unlock the chart.
```
