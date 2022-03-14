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

Bellabeat is an established company focused in health smart products for women. The problem that I am trying to solve is what are the main trends in smart device usage, find in Bellabeat's competitors data, that can be applied to Bellabeat customers to influence their marketing strategy.

## A list of the key trends I found in the data

 * From the fitabase dataset:
  * There are some days where on average people are more active and/or burn more calories.
  * There is a negative correlation between `TotalMinutesAsleep` and `SendentaryMinutes`.
  * The data is not very significant but overall it seems that most of the participants have more of their daily steps every day around 12:00 and 19:00.
 * From the apple dataset:
  * There are mayor differences in running activities between male/females.
  * There is a difference between male/female for the calories expended in the different activities.
  * There is a clear difference in the resting heart rate between men/women in all the activities.
  * These differences are stronger in people below 35. Looking only at participants above 35 years old, these discrepancies are not significant.
 * From the fitbitGrades dataset:
  * For healthy or average participants, the GPA increases with the number of steps. The trend is more significant in females.

## Story found in data

 * It is not very significant but tracker device consumers are more active on Tuesday and ...., while they are less active on Sundays.
 * Tracker device consumers burn on average less calories on Sundays and ...
 * Consumers are more active (more steps, more intensity, burn more calories) every day between 8:00 and 19:00. Being Wednesday at 17:00 and Saturday at 13:00, the two times where on average consumers are more active than usual.
 * There are no major differences in sleep patterns between days of the week. On average, sunday is the day when consumers spend more time awake.

  * Besides the consumer behavior, I found interesting trends in data between man/woman that can be exploit by the marketing department to sell our products:
    * The amount of calories burn by man and women is different when doing similar activities.
    * The resting rate between man/woman is different.
    * These differences are stronger in people below 35 years old.
    * Number of steps is correlated with GPA, this relation is more strong in women.

## Story to tell

 * Bellabeat has two products that track activities, sleep and stress. The stakeholders want to gain insights in how the consumers are using these products.
 * The fitbit data analyzed is not significant, but major trends can be found: like the day of the week when people are more active/burn more calories and therefore are more prong to use the Bellabeat products.
 * There are no major differences in tracker activity per time of the day, however two distinguished times when customers are more active are: Wed 17:00 and Saturday 13:00.
 * Customers on average spend more time awake on Sunday than any other day.
 * Major differences on calories burn and heart rate are found using apple watch data between women/men. This can be target by the marketing department to emphasize this differences when targeting women products.
 * There is a mild evidence that minutes being active can improve intellectual activities, this relation is stronger for female consumers.

## DataViz and key findings

 * I started with the main consumer findings in this [Tableau viz](https://public.tableau.com/views/GoogleCapstoneProject-Bellabeat/Story1?:language=en-US&:display_count=n&:origin=viz_share_link)
