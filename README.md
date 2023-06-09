# Education Inequality
DATA 3320 Class Project

1. Desciption: This project utilizes two data sets. The main data set is the EdGap data set from [EdGap.org](https://www.edgap.org/#5/37.875/-96.987). This data set from 2016 includes the average ACT or SAT scores and its socioeconomic characteristics of the school district. The secondary data set includes the basic information about each school from the [National Center for Education Statistics](https://nces.ed.gov/ccd/pubschuniv.asp).

2. Data: 

  a. EdGap: data: All socioeconomic data (household income, unemployment, adult educational attainment, and family structure) are from the Census Bureau's American Community Survey. [EdGap.org](https://www.edgap.org/#5/37.875/-96.987) report that ACT and SAT score data is from each state's department of education or some other public data release.

  b. School Information Data: The school information data is from the [National Center for Education Statistics](https://nces.ed.gov/ccd/pubschuniv.asp). This data set consists of basic identifying information about schools and can be assumed to be of reasonably high quality. This data set can be access [here](https://www.dropbox.com/s/lkl5nvcdmwyoban/ccd_sch_029_1617_w_1a_11212017.csv?dl=0).

 3. Data Preparation:  This is the process of identifying missing values and imputing datas, thus create a clean version of the dataset. The first step of this process is to convert some data types into tyoes that is easy to work with and/or to match the data type of two datasets. SInce the goal of this project is to answer the question of whether socioeconomics factors affect academic performance, the dataset is made to focus on the prediction'average_act'; thus this process performs the imputation of data on other attributes in the dataset. By using the Multivariate Imputation By Chained Equations algorithm, a method by which we fill in the missing values in a dataset by using information from other columns and making the best guess possible for each one, this process fill in the NaN in the other attributes in the dataset. To prepare for analysis, this process also splits the dataset into a testing and a training set. It export two cleaned datasets, a training set and a testing set.
 
 4. Analysis: This the process to answer the sub problem to make a conclusion to the main problem. I first want to examine the relatinships amng all variables. To do this, I made a correlation plot to determine which variable has the most significant relationship with 'average_act'. As a result, 'percent_lunch' is the most deterministic varaible at predicting the average ACT score. However, to make this decision more robust, the best subset is tested and select through a 'best subset selection' algorthm. This process loop through all variables and make combination of them. Then each subset is fit and tested to return the r squared, AIC, BIC values. With these values, I was able to determine that the subset of percent_college, percent_lunch, percent_married, rate_unemployment is the most significant at predicting the ACT score.
 
    To enhance the prediction of ACT score, I introduced a new variable to the dataset. I added region based on the location of the school to answer the question that "does the region of the school affect the outcome of the ACT score?" After I examine the R squared value between the model with 'region' and the model without 'region', I came to a conclusion that 'region' does not have a strong aspesct on determining the ACT scores. 

 5. Conclusion: 
- Percent Lunch and other variables are more significant at predicting the average ACT score.
- The added attribute 'region' is not a strong deciding factor to determine ACT scores.
- This results is not optimal because there are a few missing factors that hinder the performance of the models. The dataset is missing a few important predictors. For example, there are limited data from some states as well as missing the information that some states might or might not require SAT/ACT scores.
