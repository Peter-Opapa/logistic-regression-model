# Breast Cancer Prediction Web App

A web application for predicting breast cancer diagnosis (Malignant or Benign) using a logistic regression model trained on the Wisconsin Breast Cancer Dataset. Built with Flask and deployed on Render.

## Demo

Access the live app: [https://breastcancerprediction-sm7p.onrender.com](https://breastcancerprediction-sm7p.onrender.com)

## Features
- Predicts breast cancer diagnosis from 30 input features
- User-friendly web interface
- Model trained and evaluated using scikit-learn
- Secure and fast deployment with Render

## Project Structure
```
├── app.py                  # Flask application
├── requirements.txt        # Python dependencies
├── logistic_regression_model.pkl  # Trained model
├── templates/
│   └── index.html          # Web interface
├── data.csv                # Source dataset
├── Logistic Regression Model.ipynb # Model training notebook
├── render.yaml             # Render deployment config
```

## How It Works
1. User enters 30 features from a breast mass sample.
2. The app loads a pre-trained logistic regression model.
3. The model predicts if the sample is Malignant or Benign.
4. The result is displayed instantly on the web page.

## Setup & Local Development
1. Clone the repository:
   ```
   git clone https://github.com/Peter-Opapa/logistic-regression-model.git
   cd logistic-regression-model
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Run the app:
   ```
   python app.py
   ```
4. Open your browser at [http://127.0.0.1:5000](http://127.0.0.1:5000)

## Deployment
- The app is configured for Render using `render.yaml`.
- The start command uses Gunicorn for production reliability.
- All dependencies are listed in `requirements.txt`.

## Model Training
- See `Logistic Regression Model.ipynb` for data cleaning, preprocessing, model training, and evaluation steps.
- The trained model is saved as `logistic_regression_model.pkl`.

## Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## License
This project is licensed under the MIT License.

## Author
Peter Opapa
