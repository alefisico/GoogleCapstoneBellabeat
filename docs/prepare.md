# Step 2: Prepare
<!--
Ensuring ethical data analysis practices
Addressing issues of bias and credibility
Accessing databases and importing data
Writing simple queries
Organizing and protecting data
Connecting with the data community (optional)

ROCC stands for Reliability, Originality, Comprehensiveness, Current, Cited.
-->

## Guidelines from the assigment

 * __Guiding questions__
  * Where is your data stored?
  * How is the data organized? Is it in long or wide format?
  * Are there issues with bias or credibility in this data? Does your data ROCCC?
  * How are you addressing licensing, privacy, security, and accessibility?
  * How did you verify the data’s integrity?
  * How does it help you answer your question?
  * Are there any problems with the data?
 * __Key tasks__
  1. Download data and store it appropriately.
  2. Identify how it’s organized.
  3. Sort and filter the data.
  4. Determine the credibility of the data.
 * __Deliverable__
  * A description of all data sources used


## Fitbit Fitness Tracker data

This dataset is [located in Kaggle](https://www.kaggle.com/arashnic/fitbit). It seems like a well documented and widely used dataset posted [here](https://zenodo.org/record/53894#.YMoUpnVKiP9) [1]. Even though the dataset is in Kaggle, the metadata is not great. Looking more into the discussion section, I found a better description of the dataset and variables in [this pdf](https://www.fitabase.com/media/1930/fitabasedatadictionary102320.pdf) (thanks to Laimis).

This dataset is organized in many different csv files, split according to the activity register in the gadget.

Without looking into details of the dataset, I see already some possible sources of bias. First, the dataset is not current and therefore the findings of this project can be outdated. Although it is original and cited, it is indicated that the data was taken from respondent of a survey without specifying genre or location. The data can be comprehensive for the 30 individuals surveyed but cannot extrapolate to an entire population.

For Bellabeat, who is interested in women's health, this dataset can be limited and biased. Therefore the findings of this project should clearly specify this.

### Fitabase dataset

The original dataset is located in the [Zenodo repository](https://zenodo.org/record/53894#.YMoUpnVKiP9).
Because I want to exploit all the tools that I know, I want to have various copies of the dataset.
I will upload the csv files into a google spreadsheet, a Bigquery dataset and I will use the Kaggle dataset for the R and Python studies.
Additionally, I will store a copy of the csv files in my local computer as a backup.

The Fitabase dataset contains the following files:
 * `dailyActivity_merged.csv`
 * `heartrate_seconds_merged.csv`
 * `hourlyCalories_merged.csv`
 * `hourlyIntensities_merged.csv`
 * `hourlySteps_merged.csv`
 * `minuteCaloriesNarrow_merged.csv`
 * `minuteIntensitiesNarrow_merged.csv`
 * `minuteMETsNarrow_merged.csv`
 * `minuteSleep_merged.csv`
 * `minuteStepsNarrow_merged.csv`
 * `weightLogInfo_merged.csv`


## Other data sources

I identified other cited and reliable open datasets that might be helpful:  
  * [A dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/ZS2Z2J) for 46 participants using apple watch and fitbit charge [2]. I will call this dataset __AppleFitbitData__. This dataset contains the following files:
    * `aw_fb_data.csv`
    * `data_for_weka_aw.csv`
    * `data_for_weka_fb.csv`

  I found the preprint related to the dataset [here](https://assets.researchsquare.com/files/rs-17022/v1/d5923374-d56c-4fe7-a036-949ecf41917e.pdf?c=1631831698). It is useful to understand the data. After looking at that paper, I understand that each row corresponds to one minute of recorded activity. Participants where asked to do 6 different tasks in a space of 65 minutes. In the files I can find 49 participants (23 men and 26 women), which is different from what the website's dataset indicated.

  * [A dataset](https://figshare.com/articles/dataset/Dataset_Fitbits_field-tests_and_grades_The_effects_of_a_healthy_and_physically_active_lifestyle_on_the_academic_performance_of_first_year_college_students_/7218497) of first year college students using fitbit to study the effects in academic performance in Fall 2017 [3]. I will call this dataset __FitbitsAndGradesData__. This dataset can be helpful because contains data split into gender.


## References

[1] Furberg, R., Brinton, J., Keating, M., & Ortiz, A. (2016). Crowd-sourced Fitbit datasets 03.12.2016-05.12.2016 [Data set]. Zenodo. https://doi.org/10.5281/zenodo.53894

[2] Fuller, Daniel, 2020, "Replication Data for: Using machine learning methods to predict physical activity types with Apple Watch and Fitbit data using indirect calorimetry as the criterion.", https://doi.org/10.7910/DVN/ZS2Z2J, Harvard Dataverse, V1

[3] Broaddus, Allie; Jaquis, Brandon; Jones, Colt; Jost, Scarlet; Lang, Andrew; Li, Ailin; et al. (2018): Dataset: Fitbits, field-tests, and grades. The effects of a healthy and physically active lifestyle on the academic performance of first year college students.. figshare. Dataset. https://doi.org/10.6084/m9.figshare.7218497.v1
