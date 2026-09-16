# ML Size Recommendation Engine

An AI-powered clothing size recommendation system that uses **Supervised Machine Learning** and a **Random Forest Classifier** to recommend the most suitable clothing size based on customer and product attributes.

> **Project Type:** Academic / Machine Learning Portfolio Project
> **Domain:** Fashion E-Commerce / Retail Analytics
> **Model:** Random Forest Classifier
> **Dataset:** Synthetic — 2,500 records

---

## Overview

Choosing the correct clothing size is one of the major challenges in online fashion shopping. Customers cannot physically try products before purchasing, while sizing can vary across brands, categories, and fit preferences.

This project demonstrates how machine learning can be used to build a **personalized clothing size recommendation engine**.

The system analyzes customer characteristics, previous purchasing behavior, product information, and fit preferences to predict one of six standard clothing sizes:

**XS, S, M, L, XL, XXL**

The project implements an end-to-end machine learning workflow, including:

* Synthetic data generation
* Exploratory Data Analysis (EDA)
* Data preprocessing
* Categorical feature encoding
* Train-test splitting
* Random Forest model training
* Model evaluation
* Confusion matrix analysis
* Feature importance analysis
* Reusable prediction function
* Interactive size recommendation demo

---

## Business Problem

Online fashion retailers face several challenges caused by incorrect size selection:

### High Return Rates

Customers may return products because the selected size does not fit, increasing reverse-logistics and processing costs.

### Customer Dissatisfaction

An incorrect size can negatively affect the shopping experience and customer perception.

### Lost Sales

Uncertainty about sizing can cause customers to abandon purchases.

### Operational & Environmental Impact

Additional deliveries, returns, packaging, and transportation increase operational requirements and environmental impact.

### Proposed Solution

A machine-learning-based recommendation engine can use customer and product information to provide a personalized size recommendation before checkout.

---

## Project Objective

The primary objective is to build a classification model capable of predicting the most appropriate clothing size based on available customer and product attributes.

### Target Variable

`Recommended_Size`

Possible classes:

```text
XS
S
M
L
XL
XXL
```

---

## Dataset

The project uses a **synthetically generated dataset containing 2,500 records**.

The synthetic data was intentionally created to simulate realistic customer and product characteristics without using private customer information.

### Features

| Feature              | Description                        | Type        |
| -------------------- | ---------------------------------- | ----------- |
| `Customer_ID`        | Unique customer identifier         | ID          |
| `Age`                | Customer age                       | Numerical   |
| `Gender`             | Customer gender                    | Categorical |
| `Height_cm`          | Customer height in centimeters     | Numerical   |
| `Weight_kg`          | Customer weight in kilograms       | Numerical   |
| `Previous_Size`      | Previously purchased clothing size | Categorical |
| `Brand`              | Product brand category             | Categorical |
| `Category`           | Clothing category                  | Categorical |
| `Fit_Preference`     | Preferred clothing fit             | Categorical |
| `Previous_Purchases` | Number of previous purchases       | Numerical   |
| `Previous_Returns`   | Number of previous returns         | Numerical   |
| `Recommended_Size`   | Predicted clothing size            | Target      |

---

## Machine Learning Approach

This is formulated as a **Supervised Machine Learning Classification problem**.

### Pipeline

```text
Synthetic Customer & Product Data
              ↓
       Data Exploration
              ↓
    Data Preprocessing
              ↓
     Feature Encoding
              ↓
       Train/Test Split
              ↓
   Random Forest Classifier
              ↓
       Model Evaluation
              ↓
    Feature Importance
              ↓
 Personalized Size Prediction
```

---

## Model

### Random Forest Classifier

The project uses a **Random Forest Classifier** for predicting the recommended clothing size.

Random Forest is an ensemble learning algorithm that combines multiple decision trees to produce a classification result.

It is suitable for this project because the dataset contains a mixture of:

* Numerical features
* Categorical features
* Customer attributes
* Product attributes
* Behavioral information

The model also provides **feature importance**, allowing the project to examine which variables contribute most to the predictions.

---

## Data Preprocessing

The dataset contains both numerical and categorical variables.

The preprocessing workflow includes:

### Numerical Features

Numerical variables such as:

```text
Age
Height_cm
Weight_kg
Previous_Purchases
Previous_Returns
```

are processed for model training.

### Categorical Features

Categorical variables such as:

```text
Gender
Previous_Size
Brand
Category
Fit_Preference
```

are encoded into machine-readable representations.

The project uses Scikit-learn preprocessing and pipeline components to organize the transformation process.

---

## Exploratory Data Analysis

EDA is performed to understand the structure and characteristics of the dataset.

The analysis includes:

* Dataset dimensions
* Data types
* Missing-value analysis
* Duplicate-value analysis
* Descriptive statistics
* Recommended-size distribution
* Height distribution
* Weight distribution
* Categorical feature distributions
* Relationships between important variables

Visualizations are used to identify patterns in the synthetic customer data.

---

## Model Evaluation

The trained model is evaluated using multiple classification metrics:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-Score**
* **Classification Report**
* **Confusion Matrix**

The notebook reports an accuracy in the approximate **62–65% range** for the demonstrated model. Because the dataset is synthetically generated, this result should **not be interpreted as real-world performance**.

A confusion matrix is also used to understand classification errors, including confusion between neighboring size categories.

---

## Feature Importance

Feature importance analysis is used to understand which variables have the greatest influence on the model's predictions.

The notebook identifies factors such as:

* `Previous_Size`
* `Weight_kg`
* `Height_cm`

as important contributors to size prediction.

These insights demonstrate how machine learning can provide not only predictions but also useful business information for personalization and product-sizing strategies.

---

## Interactive Demo

The notebook includes an interactive prediction interface built using **ipywidgets**.

Users can provide values for:

```text
Age
Gender
Height
Weight
Previous Size
Brand
Category
Fit Preference
Previous Purchases
Previous Returns
```

The system then returns:

```text
Recommended Size
Confidence
```

This demonstrates how the trained model could eventually be connected to a customer-facing shopping interface.

---

## Example Use Case

A customer provides their information while viewing a clothing product:

```text
Age: 30
Gender: Female
Height: 165 cm
Weight: 60 kg
Previous Size: M
Brand: Brand_A
Category: T-Shirt
Fit Preference: Regular
Previous Purchases: 15
Previous Returns: 1
```

The model processes these inputs and generates a predicted clothing size along with its prediction confidence.

---

## Tech Stack

### Programming Language

* Python

### Data Processing

* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn

### Interactive Interface

* ipywidgets

### Development Environment

* Jupyter Notebook
* Google Colab

---

## Project Structure

```text
ml-size-recommendation-engine/
│
├── Myntra_AI_and_ML_model.ipynb
├── README.md
│
└── assets/
    └── project_visuals/
```

> The repository structure can be expanded later if the notebook is converted into a production-style application.

A future production-oriented structure could look like:

```text
ml-size-recommendation-engine/
│
├── data/
├── notebooks/
├── src/
│   ├── preprocessing.py
│   ├── train.py
│   └── predict.py
│
├── models/
├── tests/
├── requirements.txt
├── README.md
└── .gitignore
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/ml-size-recommendation-engine.git
cd ml-size-recommendation-engine
```

Install the required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn ipywidgets
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
Myntra_AI_and_ML_model.ipynb
```

Alternatively, the notebook can be executed directly in **Google Colab**.

---

## How to Run

1. Open the notebook.
2. Run the library imports.
3. Generate the synthetic dataset.
4. Perform exploratory data analysis.
5. Execute the preprocessing pipeline.
6. Train the Random Forest classifier.
7. Evaluate the model.
8. Review feature importance.
9. Use the prediction function.
10. Run the interactive recommendation demo.

---

## Business Value

A real-world implementation of a size recommendation engine could potentially support fashion e-commerce businesses by:

* Improving personalized shopping experiences
* Helping customers make more informed size selections
* Reducing size-related returns
* Supporting customer retention
* Providing sizing-related analytics
* Improving product and inventory planning

These are **potential business applications**, not measured outcomes of this academic implementation.

---

## Limitations

### Synthetic Dataset

The model is trained on synthetic data and therefore does not represent the complexity of real customer behavior.

### Simplified Sizing Logic

The synthetic target variable is generated using simplified relationships involving customer and product attributes. It is not based on an actual brand sizing chart.

### Limited Size Range

The model predicts only:

```text
XS – XXL
```

It does not support custom sizing or specialized size ranges.

### Brand Variability

Real-world clothing sizes can vary significantly between brands and individual products. The current dataset does not fully capture this complexity.

### No Continuous Feedback Loop

The current system does not continuously learn from customer feedback such as:

```text
"Did the recommended size fit?"
```

A production system would require ongoing feedback and model monitoring.

### Dataset Scale

The project contains 2,500 synthetic records. Production e-commerce systems would typically operate on substantially larger datasets and require more advanced data engineering infrastructure.

---

## Future Improvements

Potential future development includes:

### 1. Real Customer Measurements

Add detailed measurements such as:

* Chest
* Waist
* Hip
* Shoulder
* Inseam

### 2. Product-Level Attributes

Incorporate:

* Fabric type
* Stretch level
* Garment measurements
* Product-specific size charts
* Cut and silhouette
* Fit type

### 3. Advanced Models

Experiment with additional algorithms such as:

* Gradient Boosting
* XGBoost
* LightGBM
* Neural Networks

and compare their performance using consistent evaluation methodology.

### 4. Feedback-Based Learning

Create a feedback loop where customers can indicate whether the recommended size fitted correctly.

### 5. Production API

Deploy the trained model through an API using a framework such as:

```text
FastAPI
```

### 6. Customer-Facing Application

Integrate the recommendation engine into an e-commerce interface where customers receive size recommendations directly on product pages.

### 7. Model Monitoring

A production implementation should include:

* Model performance monitoring
* Data drift detection
* Prediction monitoring
* Periodic retraining
* Feedback analysis

---

## Privacy & Data Disclaimer

**This repository is an academic machine learning project.**

The dataset used in the notebook is **entirely synthetic** and was generated for demonstration purposes. It does not contain actual private customer data from Myntra or any other company.

The use of "Myntra" in the original academic notebook refers to the project scenario/business context and does not indicate that this system is an official Myntra product or that the project uses proprietary Myntra data.

---

## Key Learning Outcomes

This project demonstrates practical understanding of:

* Supervised Machine Learning
* Classification
* Synthetic data generation
* Exploratory Data Analysis
* Feature preprocessing
* Categorical encoding
* Train-test splitting
* Random Forest Classification
* Classification metrics
* Confusion matrix interpretation
* Feature importance
* Model-based prediction
* Interactive ML demonstrations
* Business application of AI

---

## Project Status

**Status:** Completed — Academic Prototype

The current implementation demonstrates the complete ML workflow from synthetic data generation to interactive size prediction.

---

## Author

**[Aman]**

BBA Fintech & AI
Chitkara University, Punjab, India

### Areas of Interest

`Artificial Intelligence` · `Machine Learning` · `FinTech` · `Business Analytics` · `Data Science`

---

## Disclaimer

This project is created for **educational and portfolio purposes**. Model performance on synthetic data should not be considered representative of performance on real-world fashion e-commerce data.
