![foto1](https://bkt-sa-east-1-cms-drupal.s3.sa-east-1.amazonaws.com/alta.com.br/assets/2021-03/primeiros%20sintomas%20da%20covid.JPG?8XPG_O6cw8X8RFeXiGBp1YuowBZITuy4)

# **COVID-19 - Machine Learning to assess diagnosis. Using Sírio-Libanês data available in Kaggle.** 

## **Knowing Sírio-Libanês hospital better**
Sociedade Beneficiente de Senhoras Sírio-Libanês is commited to philanthropy and science to deliver better health outcomes to those in need. One of Brazil's top hospitals, 
compromised with optimal medical care, the main departments that contributed with the necessary means to create this competition on Kaggle are, Institute Research and Education,
and the Architecture and Clinical-Radiological Data Intelligence Squad.


### **Context**

COVID-19 pandemic impact is devastating, overwhelming healthcare systems that were uncapable of dealing with the extreme demand of resources such as, ICU beds, professionals, 
personal protection equipment, medication, treatment protocols and more.
Brazil recorded first COVID-19 case on February 26 and reached community transmission on March 20.

### **Understanding the Problem**

Because of the extrenuous demand of medical resources that COVID-19 pandemic is causing in the hospitals, obtaining accurate prediction if a patient will need ICU care or not, 
can help healthcare systems prepare beforehand and avoid collapse (assuming necessary resources are available). In order to accomplish this, we'll be
using individual clinical data provided by Sírio-Libanês hospital.

![foto2](https://img.medscape.com/thumbnail_library/cdc_200313_flatten_the_curve_800x450.jpg)


### **Tasks requested by Sírio-Libanês hospital data inteligence team**


**Task 01**

Predict admission to the ICU of confirmed COVID-19 cases.
Based on the data available, is it feasible to predict which patients will need intensive care unit support?
The aim is to provide tertiary and quarternary hospitals with the most accurate answer, so ICU resources can be arranged or patient transfer can be scheduled.

**Task 02**

Predict NOT admission to the ICU of confirmed COVID-19 cases.
Based on the subsample of widely available data, is it feasible to predict which patients will need intensive care unit support?
The aim is to provide local and temporary hospitals a good enough answer, so frontline physicians can safely discharge and remotely follow up with these patients.

**Important:** The early identification of patients who will need intensive care is a key for an appropriate treatment, it can save lives, so identify 
those patients in the time window of 0 to 2hs after hospital admission is the optimal goal. We should be careful with repeated measures on individuals once 
these values are (positively) correlated.


## **The Data**

Data was obtained and grouped by the Sírio-Libanês data engineering team. This dataset contains anonymized data from Hospital Sírio-Libanês located in São Paulo and Brasilia.
All data were anonymized following the best international practices and recommendations. The data also has been cleaned and scaled by column according to Min Max Scaler 
to fit between -1 and 1.

**Label output**

ICU should be considered the target variable. 

**Window Concept**
Data engineering team included real life cenarios of time window of events and all the available data of each patient are divided by this concept. So all the patients 
data are aggregated by windows in chronological order, as we can se in the table bellow:

Window | Description
-------|---------------------------------
0-2 | From 0 to 2 hours of the admission
2-4	| From 2 to 4 hours of the admission
4-6	| From 4 to 6 hours of the admission
6-12	| From 6 to 12 hours of the admission
Above-12	| Above 12 hours from admission


**Data Information**

- Patient demographic information (03 columns)

- Patient previous grouped diseases (09 columns)

- Blood results (36 columns)

- Vital signs (06 columns)

In total there are 54 features, expanded when pertinent to the mean, median, max, min, diff and relative diff.

- diff = max - min

- relative diff = diff/median


**Missing data**

Problem: One of the major challenges of working with health care data is that the sampling rate varies across different type of measurements. For instance, vital signs are 
sampled more frequently (usually hourly) than blood labs (usually daily), because of this there are many missing data, but how we dealed with them is further explained in the
exploratory analysis.


## **Warning and Tips from the data inteligence team of the Sírio-Libanês hospital**

It is reasonable to assume that a patient who does not have a measurement recorded in a time window is clinically stable, potentially presenting vital 
signs and blood labs similar to neighboring windows. Therefore, one may fill the missing values using the next or previous entry. Attention to multicollinearity and zero 
variance issues in this data when choosing your algorithm.


![foto3](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F1591620%2Fb1bc424df771a4d2d3b3088606d083e6%2FTimeline%20Example%20Best.png?generation=1594740856017996&alt=media)

![foto4](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F1591620%2F77ca2b4635bc4dd7800e1c777fed9de1%2FTimeline%20Example%20No.png?generation=1594740873237462&alt=media)


**Warning:** All the analysis in the notebooks are made in Portuguese, I plan to translate everything to English in the near future.

To know more about the Kaggle competition access this link: https://www.kaggle.com/S%C3%ADrio-Libanes/covid19
