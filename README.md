# Classification_project_IVF

Predicting the chance of live birth for women undergoing IVF.

In Vitro Fertilization is an assisted reproductive technology commonly referred to as IVF. 

 > IVF is the process of fertilization by extracting eggs, retrieving a sperm sample, and then manually combining an egg and sperm in a laboratory dish. 
1% of births per year in the UK are a result of IVF treatment. The global IVF market size was valued at USD 14.2 billion in 2020 and is expected to grow at a compound annual growth rate (CAGR) of 6.5% from 2021 to 2028. 

![1](https://user-images.githubusercontent.com/100076753/156035343-5b80a8e3-e3c0-4be5-b8b1-75ede8cb6c14.jpg)


## Goal of the Project
The goal of this project is to create a classification model which can predict a successful live birth as a result of one or more IVF cycles. 

__Hypothesis:__ Patient’s medical history has a direct impact on the outcome of the IVF cycle.

## Data Source & Overview
The Human Fertilisation and Embryology Authority collects data and statistics about over 70,000 fertility treatments performed each year in the UK. 
By law, clinics have a duty to submit data on fertility treatments taking place and babies born as a result. To allow researchers to make good use of the data, an anonymised version of the Register is published.
Data used for this project is the latest available, it contains treatments from 2017  - 2018.

The original data can be accessed here: https://www.hfea.gov.uk/about-us/our-data/guide-to-the-anonymised-register/ .

## Cleaning & Processing
The original dataset used in this project included data on Donation & Storage of embryos. Here is a 6 step data cleaning process I followed:
1. Removing the irrelevant data
2. Removing duplicates. 
3. Renaming the columns with model-friendly names.
4. Handling missing data.
5. Filtering out data outliers
6. Creating the target variable.

## Feature Engineering

Feature engineering focused  on the IVF procedures which had at least 1 embryo transfer performed. The final features engineered into the core data set included:

- Patient’s age
- Partner’s age
- Number of previous pregnancies
- Number of previous live births
- Tubal disease
- Ovulatory disorder
- Male factor
- Endometriosis
- Unexplained infertility
- Stimulation used
- Sperm source
- Frozen cycle
- Egg source
- Embryos Transferred 
- Early outcome
- Live birth

## Exploratory Data Analysis

The EDA process highlighted some of the insights:

#### Table 1:

![download-5](https://user-images.githubusercontent.com/100076753/156035800-da8abb94-6c94-4d22-bb4b-9a32ad689f52.png)

Patients in the sample were likely to have had an unsuccessful pregnancy in the past.

#### Table 2:

![download-7](https://user-images.githubusercontent.com/100076753/156035906-9f0b2bff-d0f9-4a25-a6d2-3094562fb87a.png)

For 1 in 3 couples, a cause cannot be identified.
About one half of couples have male factor causes.

#### Table 3:


![download-2](https://user-images.githubusercontent.com/100076753/156035968-ffb03962-033c-4b23-9e9d-0a9fa59e0d61.png)

'None' & 'Miscarriage' have a slightly higher density around 6 than other outcomes. IFPS has the highest density between 1 and 2.


## Modelling
Predictions performed using machine learning algorithms including Logistic Regression, Support Vector Machine, Gradient Boosting, Decision Tree Classifier and K-nearest Neighbors Algorithm and optimized with GridSearch. 
Results 
Baseline: 57% of samples belong to the majority class 0, samples that did not result in a live birth.
The model generated by each algorithm is evaluated for precision and predictive accuracy. 

![download-6](https://user-images.githubusercontent.com/100076753/156035634-95980043-ab3f-465c-8860-26111607bf9c.png)

I am looking at precision because it determines the correctness of our model. We can afford to miss a number of successful treatments(so recall score is less important), as long as our model is correct when predicting treatments that will end up successful.

![download](https://user-images.githubusercontent.com/100076753/156035703-3282dc46-4db8-421b-bc20-3e9e51f5568f.png)


## Limitations
Limited data on causes of infertility: infertility may be caused by a range of abnormalities of the ovaries, uterus, fallopian tubes, and the endocrine system, among others. Only five features were available in the dataset in relation to causes of infertility.
No data on the lifestyle of the patients: the crucial role that modifiable lifestyle factors play in the development of infertility have generated a growing interest in this field of study, i.e. aging, psychological stress, nutrition, physical activity, caffeine, high scrotal temperature, hot water, mobile telephone use.
Limited computing resources: the necessary time for running the algorithm gets higher as we increase the size of the data. 

## Recommendations

Collecting and incorporating data on lifestyle (smoking/weight, etc.) and additional medical data.
Environmental factors: how would location data influence the modelling?
For individual clinics: collect data laboratory standards, air quality in the laboratory, and the experience of embryologists.

## Next steps
I would like to attempt using the full dataset for modelling.
I am very interested in comparing the data from private clinics and NHS, and performing modelling separately for each. 


