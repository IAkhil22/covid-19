# covid-19 dataset
Predicting whether a person with covid-19 disesase will survive from it?

The dataset contains 20 columns

    sex: female or male
    age: of the patient.
    classification: covid test findings. Values 1-3 mean that the patient was diagnosed with covid in different
    degrees. 4 or higher means that the patient is not a carrier of covid or that the test is inconclusive.
    patient type: hospitalized or not hospitalized.
    pneumonia: whether the patient already have air sacs inflammation or not.
    pregnancy: whether the patient is pregnant or not.
    diabetes: whether the patient has diabetes or not.
    copd: Indicates whether the patient has Chronic obstructive pulmonary disease or not.
    asthma: whether the patient has asthma or not.
    inmsupr: whether the patient is immunosuppressed or not.
    hypertension: whether the patient has hypertension or not.
    cardiovascular: whether the patient has heart or blood vessels related disease.
    renal chronic: whether the patient has chronic renal disease or not.
    other disease: whether the patient has other disease or not.
    obesity: whether the patient is obese or not.
    tobacco: whether the patient is a tobacco user.
    usmr: Indicates whether the patient treated medical units of the first, second or third level.
    medical unit: type of institution of the National Health System that provided the care.
    intubed: whether the patient was connected to the ventilator.
    icu: Indicates whether the patient had been admitted to an Intensive Care Unit.
    death: indicates whether the patient died or recovered.


Objective:
Create a model to predict whether a patient will die bases no symptoms


Findings on Missing Data:
The datas[readme.txt](https://github.com/IAkhil22/covid-19/files/10334366/readme.txt)
et has a description that all values like 97, 98, 99 are missing values.
Only 3 columns contain records with value = 97. They are PREGNANT, ICU, INTUBED.

All men have value = 97 for pregnant feature. It means that men can't be pregnant. As I understand value = 99 for this column is really missing value when doctors didn't have enough information about pregnancy or they had some misleading analysis results they put 99 for this feature.

We can see that columns ICU and INTUBED are connected with PATIENT_TYPE column and we can see that patients who have value = 1 for PATIENT_TYPE column have value = 97 for both ICU and INTUBED columns. It means that patients who had home treatment didn't have a chance to get ICU and to be intubed as well. Value = 99 for these two columns looks like really missing value.

All other columns have only one number for missing value. PNEUMONIA column has value = 99 all others have value = 98. I considered them as missing values and droped observations containing them.

You can download this dataset from kaggle with the link below:
https://www.kaggle.com/datasets/meirnizri/covid19-dataset
