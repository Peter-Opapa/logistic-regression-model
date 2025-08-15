
[![Deploy on Render](https://img.shields.io/badge/Deployed%20on-Render-46a2f1?logo=render)](https://breastcancerprediction-sm7p.onrender.com)
# Breast Cancer Prediction Logistic Regression Model

## Overview
This project provides a robust and user-friendly web application for predicting breast cancer diagnosis (Malignant or Benign) using a logistic regression model. The model is trained on the Wisconsin Breast Cancer Dataset and the app is built with Flask, styled for clarity, and deployed on Render for public access.

## Motivation
Early and accurate diagnosis of breast cancer is critical for effective treatment and patient outcomes. This project aims to provide a simple, accessible tool for clinicians, researchers, and students to predict cancer diagnosis using well-established machine learning techniques.

## Demo
**Live App:** [https://breastcancerprediction-sm7p.onrender.com](https://breastcancerprediction-sm7p.onrender.com)

## Dataset
- **Source:** [UCI Machine Learning Repository - Breast Cancer Wisconsin (Diagnostic) Data Set](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic))
- **Features:** 30 numeric features derived from digitized images of a breast mass (e.g., radius, texture, perimeter, area, smoothness, etc.)
- **Target:** Diagnosis (`M` = Malignant, `B` = Benign)

## Model Details
- **Algorithm:** Logistic Regression (scikit-learn)
- **Preprocessing:**
  - Dropped irrelevant columns (`id`, `Unnamed: 32`)
  - Converted diagnosis to binary (1 = Malignant, 0 = Benign)
  - Standardized features using `StandardScaler`
- **Training:**
  - 70% training, 30% test split
  - Evaluated with accuracy and classification report
- **Serialization:** Model saved as `logistic_regression_model.pkl` using `pickle`

## Features
- Predicts breast cancer diagnosis from 30 input features
- Intuitive and responsive web interface
- Fast, secure, and scalable deployment
- Easily extensible for other models or datasets

## Project Structure
```
├── app.py                          # Flask application
├── requirements.txt                # Python dependencies
├── logistic_regression_model.pkl   # Trained model
├── templates/
│   └── index.html                  # Web interface
├── data.csv                        # Source dataset
├── Logistic Regression Model.ipynb # Model training notebook
├── render.yaml                     # Render deployment config
├── README.md                       # Project documentation
```

## Usage Instructions

### Local Development
1. **Clone the repository:**
   ```bash
   git clone https://github.com/Peter-Opapa/logistic-regression-model.git
   cd logistic-regression-model
   ```
2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the app:**
   ```bash
   python app.py
   ```
4. **Access the app:** Open your browser at [http://127.0.0.1:5000](http://127.0.0.1:5000)

### Web Interface
- Enter all 30 required features in the form.
- Click "Predict" to receive an instant diagnosis (Malignant or Benign).

## Deployment Guide

### Render Setup
1. **Connect your GitHub repo to Render.**
2. **Ensure the following files are present:**
   - `app.py`
   - `requirements.txt` (must include `gunicorn` for production)
   - `logistic_regression_model.pkl`
   - `templates/index.html`
   - `render.yaml`
3. **Sample `render.yaml`:**
   ```yaml
   services:
     - type: web
       name: BreastCancerPrediction
       env: python
       plan: free
       buildCommand: pip install -r requirements.txt
       startCommand: gunicorn -w 2 -b 0.0.0.0:$PORT app:app
       envVars:
         - key: PYTHON_VERSION
           value: 3.10.13
   ```
4. **Push your changes to GitHub.**
5. **Deploy on Render:** The app will build and start automatically.

## Troubleshooting
- **Status 127 (command not found):** Ensure `gunicorn` is listed in `requirements.txt`.
- **Model not found:** Confirm `logistic_regression_model.pkl` is present in the root directory.
- **Missing dependencies:** Double-check all required packages in `requirements.txt`.
- **Form errors:** All 30 features must be filled before submitting.

## Model Training & Evaluation
- See `Logistic Regression Model.ipynb` for full details on data cleaning, feature engineering, model training, and evaluation.
- The notebook includes code for pickling the trained model for deployment.

## Acknowledgments
- UCI Machine Learning Repository for the dataset
- scikit-learn, Flask, and Render for powering the project

## Contributing
Contributions, issues, and feature requests are welcome! Please open an issue to discuss changes before submitting a pull request.

## License
This project is licensed under the MIT License.

## Author
**Peter Opapa**
