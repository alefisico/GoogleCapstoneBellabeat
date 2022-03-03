# Step 3: Process

## Guidelines from the assigment

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

Because this dataset consist of many tables divided in different cvs files I will use Bigquery to initially process it.
Additionally, some of the csv files contain around millon rows, using Bigquery for this will help to process them more effectively. Here are the steps that I found while trying to cleaning the files:

  * After download the zip files, I create a new dataset in my personal BigQuery project. This dataset is called `Fitabase`.
  * I notice that some of the files, specially the ones with time in hours/minutes/seconds, have problems to be included in the BigQuery dataset. It looks like BigQuery has problems recongnizing date time using the format AM/PM. As a way to overcome this, I will upload the such columns as `strings` instead of `datetime` types and then convert them to `datetime` in the query.
  * The source explains that the data corresponds to thirty individuals, while in the csv files there are thirty three `Id`s.
  * Information in `dailyCalories_merged.csv`, `dailyIntensities_merged.csv` and `dailySteps_merged.csv` is included in `dailyActivity_merged.csv`.
  * Using the `dailyActivity` I noticed that some there is only 4 days information for `Id = 4057192912`. I will remove that individual.
  * A deeper test of the data shows that not all the participants gave their information the 30 days of the month. If I analyze everything as it is, the results will be biased. I see two options:
    1. Remove all the participants info if they have not provide info more than 20 days (20 is based on the data).
    2. Use 1. and for the remind information, use the number of day where all the information is given.

  I think the best option is 2. and therefore I will only analyze data from `2016-04-12` to `2016-05-07`, and remove the id numbers `4057192912`, `3372868164`, `8253242879`, `2347167796`. These dates corresponds to the minimum number of dates where all the participants have all the information with at least 20 days of information.
  * I checked for `nan` values in the tables. It seems that only `weightLogInfo_merged.csv` contains 65 rows with nan value. In that table, there are 67 rows in total. Therfore, I cannot use that feature for analysis.
  * I checked for duplicates. Tables `minuteSleep_merged.csv` and `sleepDay` contain duplicates.  
  * MET means metabolic equivalent task.


## FitbitsAndGradesData

Because this dataset is small (581 rows and 11 columns) I process this dataset using [google sheets](https://docs.google.com/spreadsheets/d/1zigDuu3XxDAbuZac-vhzvmmE9q8ApM4BV5-ac1WcpEo/edit?usp=sharing). These are the steps for the cleaning process:
  * Import csv file to new spreadsheet. Call this sheet `Raw Data`, copy the data to a new sheet to continue the cleaning, and include a protection for the data in case anyone wants to modify the raw data.
  * In the new sheet, called `clean data`, I started filtering every column. I found:
    * Rows with the `Key` 446, 301, 448 contain less than 100 steps. Probably the individuals did not wear the device properly. I will remove those rows to avoid biasing the results.
    * There are many rows with very low or very high values of `Peak`, `Cardio` or `FatBurn`, but the rest of the information in the columns looks ok. I will keep them and look into it later in the analysis part.
    * There are two rows (key == 532, 554) with `GPA` equals to 0. The rest of the information looks correct, but I will remove them to be safe.
    * After this, no duplicates were found.  
