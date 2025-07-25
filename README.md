
# Student Performance Prediction

This end-to-end data science project predicts a student's math score based on several demographic and academic factors. It includes data ingestion, feature engineering, model training, and a web application for real-time predictions.

-----

## Features 

  * **Web Interface**: A user-friendly web application built with Flask to get predictions.
  * **Real-time Prediction**: Users can input student attributes and receive an instant prediction of their math score.
  * **Modular Pipeline**: The project is structured with a modular machine learning pipeline for easy maintenance and scalability.
  * **Reproducibility**: The entire workflow, from data preprocessing to model training, is encapsulated for consistent results.

-----

## Tech Stack 

  * **Backend**: Flask
  * **Machine Learning**: Scikit-learn, Pandas, NumPy
  * **Deployment**: Git/GitHub (for version control)
  * **Programming Language**: Python

-----

##  Project Structure 

```
student-performance-prediction/
├── artifacts/
│   ├── preprocessor.pkl
│   └── model.pkl
├── notebooks/
│   └── EDA_and_Model_Training.ipynb
├── src/
│   ├── components/
│   │   ├── __init__.py
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   ├── pipeline/
│   │   ├── __init__.py
│   │   └── prediction_pipeline.py
│   ├── __init__.py
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
├── templates/
│   ├── index.html
│   └── home.html
├── app.py
├── requirements.txt
└── setup.py
```

-----

##  Setup and Installation 

Follow these steps to set up and run the project on your local machine.

#### **1. Prerequisites**

  * Python 3.8 or higher
  * Git

#### **2. Clone the Repository**

Open your terminal and clone the GitHub repository.

```bash
git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name
```

#### **3. Create a Virtual Environment**

It's recommended to create a virtual environment to manage dependencies.

```bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

#### **4. Install Dependencies**

Install all the required packages from the `requirements.txt` file.

```bash
pip install -r requirements.txt
```

#### **5. Run the Application**

Start the Flask web server.

```bash
python app.py
```

Open your web browser and navigate to **`http://127.0.0.1:8000`**.

-----

##  Usage 

1.  Navigate to the application URL in your browser.
2.  Fill in the form with the student's details:
      * Gender
      * Race/Ethnicity
      * Parental Level of Education
      * Lunch Type
      * Test Preparation Course status
      * Reading Score
      * Writing Score
3.  Click the **"Predict your Maths Score"** button.
4.  The application will display the predicted math score on the same page.

-----

## Machine Learning Pipeline

The project follows a standard machine learning workflow:

  * **Data Ingestion**: Data is read from its source (e.g., a CSV file).
  * **Data Transformation**: Categorical features are converted to numerical format, and all features are scaled using a standard preprocessor (`StandardScaler`). The preprocessor object is saved for later use.
  * **Model Training**: Several regression models are trained on the processed data. The best-performing model (based on R-squared score) is selected and saved as a pickle file (`model.pkl`).
  * **Prediction Pipeline**: The final web application uses the saved preprocessor and model to make predictions on new data provided by the user through the web form.