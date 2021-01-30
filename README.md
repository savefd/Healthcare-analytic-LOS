# Healthcare analytic II LOS
Patient length of stay prediction using RandomForest and CatBoost

1. Kittapat Ratanaphupha
2. Napong Leelasithorn

<b>Source: Healthcare Analytic II via Kaggle </b>
| Column  | Description |
| --------| :----------:|
| case_id | - |
|Hospital_code| -|
|Hospital_type_code|-|
|City_Code_Hospital|City code of the hospital|
|Hospital_region_code|Region Code of the hospital|
|Available Extra Rooms in Hospital|-|
|Department|Department overlooking the case|
|Ward_Type|-|
|Ward_Facility_Code|-|
|Bed Grade	|Condition of Bed in the Ward|
|patientid	|Unique Patient Id|
|City_Code_Patient	|City Code for the patient|
|Type of Admission	|Admission Type registered by the Hospital|
|Severity of Illness	|Severity of the illness recorded at the time o...|
|Visitors with Patient|	Number of Visitors with the patient|
|Age|	Age of the patient|
|Admission_Deposit	|Deposit at the Admission Time|
|Stay	|Stay Days by the patient|

  
<h2>Overall Process</h2>

<h3>1. Data Cleansing </h3>
Drop Null bedgrade and City_Code_Patient
Handle each column Fragmentation
<h3>2. Exploratory Data Analysis </h3>
We found that there is a relationship between stay and age.
The Length of Stay and Visitor with patient are interrelated, but it can be collected after the treatment. (cannot use to predict LOS)
Hospital_Code can explain all the other variable that included "Hospital" Ex. City_Code_Hospital, Hospital_region_code.
Age column is distributed as Normal and Admission_deposit column is right-skewed.
<h3>3. Feature Engineering </h3>

Ordinal or Label encoder
1. Stay
2. Age
3. Severity of Illness

Get_dummie
1. Hospital_code
2. Department
3. Ward_Type
4. Ward_Facility_Code
5. City_Code_Patient
6. Type of Admission

Drop
1. Hospital_type_code
2. City_Code_Hospital
3. Hospital_region_code
4. patientid

Do nothing
1. Available Extra Room
2. Bed Grade
3. Visitors with Patient
4. Admission_Deposit

<h3>4. Data Modeling </h3>

RandomForestClassifier
1. 80 columns (with dummies)
2. HyperParameter Tuning with GirdSearchCV

CatBoostClassifier
1. 13 columns
2. Tuning: Depth, iterations, learning rate

### 5. Evaluation
![alt text](https://github.com/savefd/Healthcare-analytic-LOS/blob/main/Picture1.png)
![alt text](https://github.com/savefd/Healthcare-analytic-LOS/blob/main/image.png)



