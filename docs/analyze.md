# Step 4: Analyze

## Guidelines from the assigment

 * __Guiding questions__
  * How should you organize your data to perform analysis on it?
  * Has your data been properly formatted?
  * What surprises did you discover in the data?
  * What trends or relationships did you find in the data?
  * How will these insights help answer your business questions?
 * __Key tasks__
  1. Aggregate your data so it’s useful and accessible.
  2. Organize and format your data.
  3. Perform calculations.
  4. Identify trends and relationships.
 * __Deliverable__
  * A summary of your analysis


## Fitabase

After the cleaning process, I started analyzing the data. The data analyzed is limited and not a good representation of our target customers. However, we can try to identify overall trends that can be extrapolate to our case.
I started with the daily activity, and this are my findings:
  * There is a clear correlation between `TotalSteps` and the different distances (`TotalDistance`, `TrackerDistance`, `LoggedActivitiesDistance`, `VeryActiveDistance`, `ModeratelyActiveDistance`, `LightActiveDistance`) which is not surprising.
  * There is no clear correlation between `TotalSteps` or `TotalDistance` and `Calories`.
  * Then, I looked at the quantities based on the day of the week, this is what I found:
    * It is not statistically significant because of the dataset, but there is a trend on `TotalSteps` and `TotalDistance` to be lower on Sundays and Mondays. After further analysis, it looks like it is just because the data has 3 Sundays and Mondays, and 4 of the other days. After weighting the quantities properly, the trend disappear.
    * After normalizing all the quantities to the proper day, there is no clear trend in any quantity based on the day of the week. Perhaps the only noticeable, but not statistically significant, difference is in the `SedentaryActiveDistance`, where it seems that Monday and Thursdays have higher values.
  * Then, I looked at the `sleepDay` dataset. There are only 15 participants with data. No clear trend in the data is found.
  * Then I looked at correlations between the daily activity and sleep. I merged `dailyActivity` and `sleepDay` tables. After removing `Nan` values I ended up with similar number of participants as the `sleepDay` (as excepted). I found:
    * There is a negative correlation between `TotalMinutesAsleep` and `SendentaryMinutes`.
    * There is a mildly negative correlation between `FairlyActiveMinutes` and `TotalMinutesAsleep`.
  * Then I looked into the hourly dataset. I found:
    * The data is not very significant but overall it seems that most of the participants have more of their daily steps every day around 12:00 and 19:00.
    * The patterns are similar for weekdays and slightly different for weekends. Participants are more active at 13:00 on Saturdays, and less active than usual after 19:00 on Sundays.
    * Similar patterns from the daily steps is found in calories and intensity.
  * I analyze the `minuteSleep` dataset. No major pattern found. 
