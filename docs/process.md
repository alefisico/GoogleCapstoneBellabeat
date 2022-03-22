# Step 3: Process

## Guidelines from the assignment

 * __Guiding questions__
  * What tools are you choosing and why?
  * Have you ensured your data’s integrity?
  * What steps have you taken to ensure that your data is clean?
  * How can you verify that your data is clean and ready to analyze?
  * Have you documented your cleaning process so you can review and share those results?
 * __Key tasks__
  1. Check the data for errors.
  2. Choose your tools.
  3. Transform the data so you can work with it effectively.
  4. Document the cleaning process.
 * __Deliverable__
  * Documentation of any cleaning or manipulation of data


## Fitabase

Because this dataset consists of many tables divided into different CSV files, I will initially use Bigquery to process it.
Additionally, some of the CSV files contain around million rows. Using Bigquery for this will help to process them more effectively. Here are the steps that I found while trying to clean the files:

  * After downloading the zip files, I create a new dataset in my personal BigQuery project called `Fitabase`.
  * I notice that some of the files, especially those with time in hours/minutes/seconds, have problems being included in the BigQuery dataset. For example, BigQuery has problems recognizing date time using the format AM/PM. To overcome this, I will upload such columns as `strings` instead of `datetime` types and then convert them to `datetime` in the query.
  * The source explains that the data corresponds to thirty individuals, while there are thirty-three `Id`s in the CSV files.
  * Information in `dailyCalories_merged.csv`, `dailyIntensities_merged.csv` and `dailySteps_merged.csv` is included in `dailyActivity_merged.csv`.
  * I'll start with the daily information:
    * Using the `dailyActivity`, I noticed that there is only four days information for `Id = 4057192912`, and I will remove that individual.
    * A more profound test of the data shows that not all the participants gave their information the 30 days of the month, and if I analyze everything, the results will be biased. I see two options:
      1. Remove all the participants' info if they have not provided information for more than 20 days (20 is based on the data).
      2. Use 1. and for the reminder information, use the number of days where all the information is given.

    I think the best option is 2. Therefore, I will only analyze data from `2016-04-12` to `2016-05-07`, and remove the id numbers `4057192912`, `3372868164`, `8253242879`, `2347167796`. These dates correspond to the minimum number of dates where all the participants have all the information with at least 20 days of data.
    * I checked for `nan` values in the tables. It seems that only `weightLogInfo_merged.csv` contains 65 rows with nan value. In that table, there are 67 rows in total, so I cannot use that feature for analysis.
    * I checked for duplicates. Tables `minuteSleep_merged.csv` and `sleepDay` contain duplicates.  
    * There are only 24 participants with sleep records in `sleepDay`.
    * Nine participants have records for less than 10 days in `sleepDay`. If I followed the same procedure as the daily activity, I ended up with 12 participants records.
    * Due to the lack of information, I will remove the participants with less than 10 days of sleep records, and for the rest, I will weight the results to remove any bias in the results. The `Id` of those participants is `2320127002`, `7007744171`, `1844505072`, `6775888955`, `8053475328`, `1644430081`, `1927972279`, `4558609924`, `4020332650`.
    * There are only 8 participants with `weightLogInfo` data. Out of the 8, only 2 have more than 5 days of information and therefore cannot make any significant results from this dataset.
    * MET means metabolic equivalent task.

  * Moving to the hourly information:
    * Similar problem than in the daily information. There are 4 participants with fewer data. I will keep similar requirements to the daily information (i.e., data from `2016-04-12` to `2016-05-07`, and id numbers `4057192912`, `3372868164`, `8253242879`, `2347167796`)

  * I will not analyze the minute information since I don't see how that can help the marketing department sell our products. However, there is the `minuteSleep` dataset with information about sleep patterns in the participants.
    * In principle, I must remove the same individuals as in the `sleepDay` dataset. However, here I want to see a different approach. More than focusing on individuals, I want to focus on sleep records. Looking at the number of minutes each individual recorded, I found 4 participants with very low.

## AppleFitbitData

I chose to analyze this dataset in R. I could do it in spreadsheets or python, but I want to use tools in R. This is what I found about this dataset:

  * The `aw_fb_data` dataset is the merge of the two other datasets (`data_for_weka_aw`, `data_for_weka_fb`).
  * Using `skim_without_charts`, there are no missing values; there are no duplicates either.
  * I started looking at some basic quantities in the overall dataset:
    * There are no surprising correlations between the variables in the dataset. Strong correlations between gender-height, gender-weight, height-weight, heart_rate-intensity_karvonen, heart_rate-norm_heart, distance-steps_times_distance, norm_heart-intensity_karvonen, entropy_heart-entropy_steps.
    * Since I plan to use this dataset to look into genre data, I focused on the correlation between variables and genre. This dataset shows no correlation between the genre any other variable, except height and weight.
  * This dataset, in principle, was meant to compare accuracy in tracking data from Fitbit vs. apple watch. However, based on the number of rows, there is a discrepancy between the data recorded.
    * Based on the number of minutes recorded by the devices per participant, if I want to use only the data where both devices recorded the exact quantities, the dataset reduces almost by half. (14 women, 13 men)
    * Based on the same metric, the records from the apple watch are more according to the dataset information (i.e. all the participants have more than 64 min of activity recorded)


## FitbitsAndGradesData

Because this dataset is small (581 rows and 11 columns), I process this dataset using [google sheets](https://docs.google.com/spreadsheets/d/1zigDuu3XxDAbuZac-vhzvmmE9q8ApM4BV5-ac1WcpEo/edit?usp=sharing). These are the steps for the cleaning process:
  * Import CSV file to a new spreadsheet. Call this sheet `Raw Data`, copy the data to a new sheet to continue the cleaning, and include protection for the data if anyone wants to modify the raw data.
  * In the new sheet, called `clean data`, I started filtering every column. I found:
    * Rows with the `Key` 446, 301, 448 contain less than 100 steps. Probably the individuals did not wear the device properly and I will remove those rows to avoid biasing the results.
    * There are many rows with very low or very high values of `Peak`, `Cardio`, or `FatBurn`, but the rest of the information in the columns looks ok. I will keep them and look into them later in the analysis part.
      * (While analyzing) these high values are biasing the results. I will remove: `Peak>100`, `Cardio>150`,
    * There are two rows (key == 532, 554) with `GPA` equals to 0. The rest of the information looks correct, but I will remove them to be safe.
    * After this, no duplicates were found.  
  * After looking at the paper from where the dataset came from, it is clear that the `gender==1` is female and `gender==0` is male.
  * Additionally, I create categorical variables for:
    * `GPA`: I use the mean and stddev to create the grades "A" (`GPA>3.9`), "B" (`3.2<GPA<3.9`), "C" (`2.5<GPA<3.2`), "D" (`2.5<GPA`).
    * `Life Score` (this one following the terminology of the paper): very healthy (<40), healthy (41–70), average (71–100), unhealthy (101–130), and very unhealthy (>131). Additionally, however there are 36 (16) participants with unhealthy (very healthy) conditions compared to the vast majority on average and healthy, therefore I will focus on those.
    * `Mode`: run (1), walk (0) for the cardio activity.
