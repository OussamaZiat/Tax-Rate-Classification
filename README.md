# Classification by Tax Rate
This repository contains the code and resources for a project aimed at predicting the tax rate class based on the name of an item and its price.

### Objective of the Project
The objective of this project is to develop a model that can accurately predict the tax rate class of an item. The prediction is based on the name of the item and its price.

### Summary
Using receipts collected by the startup KillBills, we have trained a model that can predict the tax rate class. The model achieved the following performance metrics:

- Accuracy score: ``0.89``
- Overall Precision: ``0.89``
- Overall Recall: ``0.88``
- Average AUC: ``0.98``

The tax rate classes are defined as follows:

- ``Low Tax Rate``: Tax Rate between **0%** and **6%**
- ``Medium Tax Rate``: Tax Rate from **6%** up to **12%**
- ``High Tax Rate``: Tax Rate over **12%**
- ``No tax``: Tax Rate of **0%**

We have provided a function, predict_tax_rate_class(itemName, amount), which can be used to predict the tax rate class given the name of an item and its price. Here are some examples of its usage:

- predict_tax_rate_class(itemName="cigarette", amount=10) ==> ``'High Tax Rate'``
- predict_tax_rate_class(itemName="vin", amount=10) ==> ``'High Tax Rate'``
- predict_tax_rate_class(itemName="baguette artisanal", amount=1.5) ==> ``'Low Tax Rate'``
- predict_tax_rate_class(itemName="bière", amount=1.5) ==> ``'High Tax Rate'``
- predict_tax_rate_class(itemName="billet cinéma", amount=8) ==> ``'Medium Tax Rate'``
- predict_tax_rate_class(itemName="kebab", amount=8) ==> ``'Medium Tax Rate'``
- predict_tax_rate_class(itemName="Champagne", amount=8) ==> ``'High Tax Rate'``
- predict_tax_rate_class(itemName="menu étudiant", amount=8) ==> ``'No Tax'``


The repository includes two files:

- ``extract.ipynb``: This notebook establishes a connection to a PostgreSQL database using the psycopg2 module. It retrieves all rows from the "items" table, converts the data into a pandas DataFrame, and displays it.
- ``model.ipynb``: This notebook contains the code for building the model used in the project. It outlines the plan for the file.
Please refer to the respective notebooks for more details on the data extraction process and model implementation.

#### **Running the Application**
##### **Data Extraction:**

- The initial step in the process is the construction of the `main_data.csv` file. This is achieved by executing the `extract.ipynb` notebook.

##### **Model Construction:**

- Upon successful completion of the data extraction, you then proceed to run the `model.ipynb` notebook.

**Remember** to ensure that all *prerequisites* are fulfilled before running these notebooks.
# PLAN


## Data Exploration: 

- `Handling Missing values:`
    - `Are the **date**, **parent**, **quantity** columns empty?`
    - `Is **updatedAt** column a duplicate of the **createdAt**?`
    - `Does the **taxDescription** column  duplicates the information presented in the **TaxRate** column ?`
    - `What is the percentage of missing values in the **description** column?`
    - `Deleting any rows that exhibit a missing **itemName** to preserve data integrity.`

- `Data extraction:`
    - `Converting The **id** and **storeId** from UUID format to integer format:`
    - `Construct a new **taxRateClass** column to house the previously defined Tax Rate Classes.`
    - `**createdAt** and **type** columns transformation:` 

- `Discovering pattrens:`
    - `Plots`
    - ` Scaling the **amount** column and resolving the **skewness** problem:` 


## Training and Evaluation: 

- `Prepare Data For training:`
    - `Select the attributs:`
    - `Calculate Word Counts using CountVectorizer:`
    - `Split Data into train Dataset, test Dataset:`

- `Model training and evaluation:`

    - `Support Vector Classifier:`
    - `Logistic Regression:`
    - `K-Nearest Neighbors:`
    - `Decision Tree Classifier`
    - `eXtreme Gradient Boosting:`
    - `Gradient Boosting Classifier:`
    - `Conclusion`


## OUR MODEL:


## THE FUNCTION:









