# Step 4: Analyze

## Guidelines from the assignment

 * __Guiding questions__
  * How should you organize your data to perform analysis on it?
  * Has your data been properly formatted?
  * What surprises did you discover in the data?
  * What trends or relationships did you find in the data?
  * How will these insights help answer your business questions?
 * __Key tasks__
  1. Aggregate your data so it's useful and accessible.
  2. Organize and format your data.
  3. Perform calculations.
  4. Identify trends and relationships.
 * __Deliverable__
  * A summary of your analysis


## Fitabase

After the cleaning process, I started analyzing the data. The data analyzed is limited and not a good representation of our target customers. However, we can try to identify overall trends that can be extrapolated to our case.
I started with the daily activity, and these are my findings:
  * There is a clear correlation between `TotalSteps` and the different distances (`TotalDistance`, `TrackerDistance`, `LoggedActivitiesDistance`, `VeryActiveDistance`, `ModeratelyActiveDistance`, `LightActiveDistance`) which is not surprising.
  * There is no clear correlation between `TotalSteps` or `TotalDistance` and `Calories`.
  * Then, I looked at the quantities based on the day of the week, this is what I found:
    * It is not statistically significant because of the dataset, but there is a trend on `TotalSteps` and `TotalDistance` to be lower on Sundays and Mondays. After further analysis, it looks like it is because the data has 3 Sundays and Mondays and 4 of the other days. After weighting the quantities properly, the trend disappears.
    * After normalizing all the quantities to the good day, there is no clear trend in any quantity based on the day of the week. Perhaps the only noticeable, but not statistically significant, the difference is in the `SedentaryActiveDistance`, where it seems that Monday and Thursdays have higher values.
  * I try to categorize the information of the individuals based on their "active level". I use a definition of active level based on [this website](https://www.medicinenet.com/how_many_steps_a_day_is_considered_active/article.htm), where individuals are categorized into 5 different levels based on the number of daily steps:
     * `TotalSteps < 5000` is  'Sedentary'
     * `TotalSteps) < 7500` is 'Low Active'
     * `TotalSteps) < 10000` is 'Somewhat Active'
     * `TotalSteps) < 12500` is 'Active'
     * `TotalSteps) > 12500`, is 'Highly Active'
    The information is limited, but there are some interesting observations that we can point out to the stakeholders:
      * The number of minutes of activity does not linearly scale to the active level.
      * Same for distance.
      * Very active people make the most steps on Saturdays, while sedentary people make the least on Sundays.
      * Although calories and steps are in general correlated, active (and highly active) people have many days with a low-calorie count.  
  * Then, I looked at the `sleepDay` dataset, with only 15 participants with data, and no clear trend in the data is found.
  * Then, I looked at correlations between daily activity and sleep. I merged `dailyActivity` and `sleepDay` tables. After removing `Nan` values, I ended up with a similar number of participants as the `sleepDay` (as excepted). I found:
    * There is a negative correlation between `TotalMinutesAsleep` and `SendentaryMinutes`.
    * There is a mildly negative correlation between `FairlyActiveMinutes` and `TotalMinutesAsleep`.
  * Then, I looked into the hourly dataset. I found:
    * The data is not very significant, but overall, most of the participants have more of their daily steps every day around 12:00 and 19:00.
    * The patterns are similar for weekdays and slightly different for weekends; participants are more active at 13:00 on Saturdays and less active than usual after 19:00 on Sundays.
    * Similar patterns from the daily steps are found in calories and intensity.
  * I analyzed the `minuteSleep` dataset; no significant pattern was found.


## AppleFitbitData

After the cleaning and decided to use only the Apple Watch dataset. This is what I found:
 * There are 49 participants (26 women and 23 men).
 * The majority of the participants have less than 35 years old. The average weight-height for women is 160cm-60kg, and for men is 180cm-75kg.
 * After this, I looked into the different activities logged in the dataset: Lying, Sitting, Self-paced walk, Running 3 METs, Running 5 METs, Running 7 METs. These activities were compared between women and men; this is what I found:
  * Although there is a slight difference in the heart rate distributions for Lying, Sitting, and Self-paced walk, significant differences appear for the Running activities. This is an excellent result that needs further studies.
  * There is a difference between males/females for the calories expended in the different activities.
  * There is a clear difference in the resting heart rate between men/women in all the activities.
  * The intensity is also different between males/females following the trend seen for heart rate.
  * I tried to go deeper into these discrepancies:
    * Checking the correlation of variables per gender, there is no apparent difference.
    * I investigate the effect of age on those variables and see that the differences could appear for participants in different age ranges.
    * I concentrate on participants aged 15-35, and the discrepancies are still there; however, looking only at participants above 35 years old, these discrepancies are not significant.
  * From this quick test, and acknowledging the limitations of the dataset, I think I can use this discrepancy for the final presentation.


## FitbitsAndGradesData

After the cleaning, this is what I found:
 * Looking at the average of the quantities, there is no statistically significant difference in any of the features between genders.
 * Looking at the correlation between features, the data shows correlations:
    * between the heart-rate at minutes at peak and cardio,
    * at cardio and fat-burn,
    * (a little) between steps and fatburn,
    * (a little) negative between minutes active and steps,
    * negative correlation between minutes and mode,
    * gender and minutes active,
    * GPA and steps (surprising)
    * life score and minutes active.
  Going deep into the women data only, the previous correlations hold, having an increased correlation between cardio and peak, and fat-burn and peak. The negative correlation between minutes, GPA, and steps also significantly increased.
  * Then, I compared life score vs. GPA for steps, HR peak, HR cardio, HR fatburn, and I am not considering the unhealthy and very healthy Life Scores due to the lack of data. I found:
    * For healthy or average participants, the GPA increases with the number of steps; the trend is more significant in females.
    * For male participants, there is a clear pattern for avg minutes in the peak zone compared to healthy and average life scores; this trend is not there for females.
    * There is no trend for cardio and fat-burn zones concerning GPA or life scores.
