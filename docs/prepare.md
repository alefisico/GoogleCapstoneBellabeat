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

This dataset is organized in many different csv files, splitted according to the activity registed in the gadget.

Without looking into details of the dataset, I see already some possible sources of bias. First, the dataset is not current and therefore the findings of this project can be outdated. Although it is original and cited, it is indicated that the data was taken from responders of a survey without specifying genre or location. The data can be comprehensive for the 30 individuals surveyed but cannot extrapolate to an entire population.

For Bellabeat, who is interested in women's health, this dataset can be limited and biased. Therefore the findings of this project should clearly specify this.

I identified other cited and reliable open datasets that might be helpful:  
  * [A dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/ZS2Z2J) for 46 participants using apple watch and fitbit charge [2].
  * [A dataset](https://figshare.com/articles/dataset/Dataset_Fitbits_field-tests_and_grades_The_effects_of_a_healthy_and_physically_active_lifestyle_on_the_academic_performance_of_first_year_college_students_/7218497) of first year college students using fitbit to study the effects in academic performance [3].


## References

[1] Furberg, R., Brinton, J., Keating, M., & Ortiz, A. (2016). Crowd-sourced Fitbit datasets 03.12.2016-05.12.2016 [Data set]. Zenodo. https://doi.org/10.5281/zenodo.53894
[2] Fuller, Daniel, 2020, "Replication Data for: Using machine learning methods to predict physical activity types with Apple Watch and Fitbit data using indirect calorimetry as the criterion.", https://doi.org/10.7910/DVN/ZS2Z2J, Harvard Dataverse, V1
[3] Broaddus, Allie; Jaquis, Brandon; Jones, Colt; Jost, Scarlet; Lang, Andrew; Li, Ailin; et al. (2018): Dataset: Fitbits, field-tests, and grades. The effects of a healthy and physically active lifestyle on the academic performance of first year college students.. figshare. Dataset. https://doi.org/10.6084/m9.figshare.7218497.v1