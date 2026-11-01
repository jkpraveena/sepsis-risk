A Scalable Machine Learning Digital Twin Framework for Early Sepsis Risk Prediction

<p align="center">
  <strong>Early Sepsis Detection Using Multi-Hospital ICU Time-Series Data</strong>
</p>
<p align="center">
  Machine Learning | Healthcare AI | Time-Series Analysis | Predictive Analytics
</p>

⸻

Overview

Sepsis is a life-threatening medical condition caused by the body’s extreme response to infection. Early identification is critical, as delays in detection and treatment can significantly increase mortality risk.

This project develops a machine learning-based digital twin framework for early sepsis risk prediction, leveraging longitudinal Intensive Care Unit (ICU) patient data from multiple hospitals.

The framework analyzes patient vital signs, laboratory measurements, and clinical indicators to identify early physiological patterns associated with sepsis development.

Rather than relying on isolated measurements, the system models changes in patient conditions over time to support early risk assessment.

The primary objective is to investigate whether machine learning models can provide reliable early warning signals while maintaining generalization across different hospital environments.

Key Features

* Early Sepsis Prediction: Predicts sepsis risk up to 6 hours before the onset of sepsis.
* Longitudinal Patient Monitoring: Utilizes time-series ICU measurements to capture evolving patient conditions.
* Multi-Hospital Evaluation: Evaluates model generalization using data from different hospital cohorts.
* Machine Learning Models: Implements Logistic Regression, XGBoost, and LSTM-based approaches.
* Comparative Model Evaluation: Compares models using AUROC and the official PhysioNet challenge utility score.
* Scalable Architecture: Designed around a reusable data preprocessing, training, and evaluation pipeline.

Dataset

The project uses the PhysioNet/CinC Challenge 2019 Sepsis Dataset.

Dataset characteristics:

* Approximately 40,336 ICU patient records.
* Data collected from multiple hospital systems.
* Hourly physiological measurements and laboratory observations.
* Includes patient vital signs, demographic information, and clinical indicators.
* Contains sepsis onset annotations for supervised learning.

Clinical Features

The dataset includes measurements such as:

Category	Features
Vital Signs	Heart Rate, Respiration Rate
Blood Pressure	SBP, DBP, MAP
Temperature	Patient Body Temperature
Oxygenation	O2Sat
Laboratory Measurements	WBC, Lactate, Creatinine, Platelets
Clinical Indicators	Glucose, Bilirubin, Hct, Hgb
Demographics	Age, Gender

Dataset Source: PhysioNet/CinC Challenge 2019

Note: The dataset is not included in this repository. Access and download it through PhysioNet according to its data access requirements.

System Architecture

The framework follows a modular machine learning pipeline:

        ICU Patient Time-Series Data
                    |
                    v
          Data Preprocessing
                    |
                    v
       Missing Value Handling
                    |
                    v
       Feature Engineering
                    |
                    v
        Temporal Data Modeling
                    |
                    v
          Model Training
                    |
          +---------+---------+
          |         |         |
          v         v         v
          LR      XGBoost    LSTM
          |         |         |
          +---------+---------+
                    |
                    v
          Model Evaluation
                    |
                    v
        Cross-Hospital Testing
                    |
                    v
         Early Sepsis Risk
              Prediction

Methodology

1. Data Preprocessing

* Processed longitudinal ICU patient records.
* Handled missing clinical measurements.
* Prepared patient-level time-series observations.
* Performed feature engineering for predictive modeling.
* Prepared hospital-specific training and evaluation cohorts.

2. Temporal Feature Modeling

Clinical measurements are analyzed over time to capture changes in patient physiological conditions.

The framework uses historical patient observations to identify patterns that may indicate an increased risk of developing sepsis.

3. Machine Learning Models

Three different approaches were implemented and evaluated.

Model	Description
Logistic Regression	Baseline model for early sepsis risk prediction.
XGBoost	Primary predictive model for capturing nonlinear relationships in clinical data.
LSTM	Deep learning model for learning temporal dependencies in patient time-series observations.

4. Prediction Objective

The prediction task focuses on identifying patients at risk of developing sepsis approximately 6 hours before the recorded onset.

5. Cross-Hospital Evaluation

The framework evaluates model performance on a held-out hospital cohort to investigate its ability to generalize beyond the training environment.

This is particularly important in healthcare applications, where patient populations and clinical practices can vary between hospitals.

Experimental Results

The models were evaluated on the held-out Hospital B cohort.

Performance Comparison

Model	AUROC	Utility Score
Logistic Regression	0.6686	0.1041
XGBoost	0.7753	0.2628
LSTM	0.6916	0.0126

Key Findings

* XGBoost achieved the highest AUROC of 0.7753 among the evaluated models.
* XGBoost also achieved the highest utility score of 0.2628.
* Logistic Regression provided a baseline for comparison.
* LSTM demonstrated the potential of temporal modeling but did not outperform XGBoost in the current experiments.
* The results highlight the importance of evaluating predictive models across different hospital environments.

Best Performing Model: XGBoost

The experimental results suggest that gradient-boosted decision trees provide a strong baseline for early sepsis risk prediction using structured ICU time-series data.

Results represent the current experimental configuration and are not evidence of clinical validation.

Technology Stack

Category	Technologies
Programming Language	Python
Machine Learning	Scikit-learn, XGBoost
Deep Learning	TensorFlow / Keras
Data Processing	Pandas, NumPy
Visualization	Matplotlib, Seaborn
Dataset	PhysioNet/CinC Challenge 2019
Evaluation	AUROC, PhysioNet Utility Score

Getting Started

Prerequisites

* Python 3.9 or later
* pip
* Git
* Access to the PhysioNet/CinC Challenge 2019 dataset

1. Clone the Repository

git clone <YOUR_REPOSITORY_URL>
cd <YOUR_REPOSITORY_NAME>

2. Create a Virtual Environment

python -m venv venv

Activate the environment:

macOS / Linux

source venv/bin/activate

Windows

venv\Scripts\activate

3. Install Dependencies

pip install -r requirements.txt

4. Download the Dataset

Download the PhysioNet/CinC Challenge 2019 dataset and place it in the appropriate data directory as configured in the project.

5. Run the Project

Execute the preprocessing, training, and evaluation scripts according to the repository structure.

Refer to individual scripts and configuration files for execution details.

Project Objectives

The project explores the following research questions:

1. Can machine learning models identify sepsis risk several hours before clinical onset?
2. How effectively can temporal patient information improve early risk prediction?
3. How well do predictive models generalize across different hospital environments?
4. Which machine learning approach provides the best balance between predictive performance and clinical utility?

Future Enhancements

* Integrate real-time ICU data streams for continuous patient monitoring.
* Explore transformer-based architectures for temporal clinical modeling.
* Improve cross-hospital domain adaptation and generalization.
* Incorporate explainable AI techniques such as SHAP for clinical interpretability.
* Develop an interactive dashboard for patient risk visualization.
* Investigate calibration and threshold optimization for clinical risk stratification.

Research Significance

This project explores the application of machine learning and digital twin concepts in healthcare, focusing on early identification of sepsis through longitudinal patient data.

By combining temporal clinical information, predictive modeling, and cross-hospital evaluation, the framework aims to contribute to research on scalable and generalizable clinical early warning systems.

Disclaimer

This project is intended strictly for academic and research purposes.

It is not a clinically validated medical device and must not be used for actual diagnosis, treatment decisions, or patient care. Predictions require further clinical validation before any real-world application.

⸻

Building intelligent systems for real-world healthcare challenges.
