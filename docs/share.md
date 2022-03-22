# Step 5: Share

## Guidelines from the assignment

 * __Guiding questions__
  * Were you able to answer the business questions?
  * What story does your data tell?
  * How do your findings relate to your original question?
  * Who is your audience? What is the best way to communicate with them?
  * Can data visualization help you share your findings?
  * Is your presentation accessible to your audience?
 * __Key tasks__
  1. Determine the best way to share your findings.
  2. Create effective data visualizations.
  3. Present your findings.
  4. Ensure your work is accessible.
 * __Deliverable__
  * Supporting visualizations and key findings


## A reminder of the problem I am trying to solve.

Bellabeat is an established company focused on health smart products for women. The problem that I am trying to solve is the main trends in smart device usage found in Bellabeat's competitor's data that can be applied to Bellabeat customers to influence their marketing strategy.

## A list of the key trends I found in the data

 * From the fitabase dataset:
  * There are some days where people are more active and/or burn more calories on average.
  * There is a negative correlation between `TotalMinutesAsleep` and `SendentaryMinutes`.
  * The data is not very significant, but most of the participants have more of their daily steps every day around 12:00 and 19:00.
  * Very active people make the most steps on Saturdays, while sedentary people make the least on Sundays.
  * Although calories and steps are in general correlated, active (and highly active) people have many days with a low-calorie count.
 * From the apple dataset:
  * There are significant differences in running activities between males/females.
  * There is a difference between males/females for the calories expended in the different activities.
  * There is a clear difference in the resting heart rate between men/women in all the activities.
  * These differences are more substantial in people below 35; these discrepancies are insignificant when looking only at participants above 35 years old.
 * From the fitbitGrades dataset:
  * For healthy or average participants, the GPA increases with the number of steps; the trend is more significant in females.

## Story found in data

 * It is not very significant, but tracker device consumers are more active on Tuesdays and Saturdays, while they are less active on Sundays.
 * Tracker device consumers burn on average fewer calories on Sundays.
 * Consumers are more active (more steps, more intensity, burn more calories) every day between 8:00 and 19:00. Being Wednesday at 17:00 and Saturday at 13:00, the two times where consumers are more active than usual on average.
 * There are no significant differences in sleep patterns between days of the week; on average, Sunday is the day when consumers spend more time awake.

  * Besides the consumer behavior, I found interesting trends in data between men/women that the marketing department can exploit to sell our products:
    * The number of calories burned by men and women are different when doing similar activities.
    * The resting rate between men/women is different.
    * These differences are more robust in people below 35 years old.
    * Number of steps is correlated with GPA; this relation is more substantial in women.

## Story to tell

 * Bellabeat has two products that track activities, sleep, and stress. The stakeholders want to gain insights into how the consumers are using these products.
 * The Fitbit data analyzed is not significant, but minor trends can be found: the day of the week when people are more active/burn more calories and therefore are more prong to use the Bellabeat products.
 * There are no significant differences in tracker activity per time of the day; however, two distinguished times when customers are more active are: Wed 17:00 and Saturday 13:00.
 * Customers, on average, spend more time awake on Sunday than any other day.
 * Major differences in calorie burn and heart rate are found using apple watch data between women/men. The marketing department can target this to emphasize these differences when targeting women's products.
 * There is mild evidence that minutes of being active can improve intellectual activities; this relation is more substantial for female consumers.

## DataViz and critical findings

 * I created 3 Tableau Viz, one for each dataset. (I could do it in one, but I also want to have more viz in Tableau public):
 * [Fitabase dataset](https://public.tableau.com/views/GoogleCapstoneProject-Bellabeat/Story1?:language=en-US&:display_count=n&:origin=viz_share_link)
 * [AppleFitbit dataset](https://public.tableau.com/app/profile/alejandro.espinosa3643/viz/GoogleCapstoneProject-BellavistaApplewatchdata/Dashboard1)
   * [FitbitsAndGrades dataset](https://public.tableau.com/app/profile/alejandro.espinosa3643/viz/GoogleDataAnalyticsCapstoneProjectBellabeat-Fitbitandgrades/Dashboard1)
