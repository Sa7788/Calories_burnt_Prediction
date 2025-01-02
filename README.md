# Calories Burned Prediction WebApp


## Short Description

This project is a Streamlit web application that predicts the number of calories burned during exercise based on user input parameters such as age, gender, BMI, duration of exercise, heart rate, and body temperature. It utilizes a trained Random Forest Regressor model to make these predictions and provides visual comparisons and helpful tips to the user.

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Explanation](#project-explanation)
- [How to Run Locally](#how-to-run-locally)
- [How to Use Streamlit](#how-to-use-streamlit)
- [Data Sources](#data-sources)
- [Model Training](#model-training)
- [Model Evaluation](#model-evaluation)
- [Tips for Improvement](#tips-for-improvement)
- [Contributing](#contributing)


## Features

- *Interactive User Input:* Uses Streamlit's interactive widgets to collect user data for predictions.
- *Calorie Prediction:* Predicts the number of calories burned based on provided parameters.
- *Similar Results:* Displays similar historical data from the dataset based on the prediction.
- *Personalized Comparisons:* Compares user's input parameters with the data of other people in the dataset.
- *Visualizations:* Uses Plotly to display distributions of Age and BMI within the dataset.
- *Model Evaluation:* Provides Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² Score for model evaluation.
- *Improvement Tips:* Offers personalized advice based on the user's input data.

## Technologies Used

- *Python:* Programming language.
- *Streamlit:* Framework for building interactive web applications with Python.
- *Pandas:* Data manipulation and analysis.
- *NumPy:* Numerical computing library.
- *Scikit-learn:* Machine learning library.
- *Plotly:* Interactive data visualization library.

## Project Explanation

This project uses a dataset containing information on exercise and calorie burning to train a machine-learning model. The trained model allows a user to input personal information and workout details through a web interface to predict the number of calories they might burn. The project provides visual comparisons of the user's input with the dataset and offers insights into how they compare with others, along with personalized advice for improving their calorie-burning potential.

## How to Run Locally

1.  *Clone the Repository:*
    bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    

2.  *Install Required Libraries:*
    bash
    pip install -r requirements.txt
    
    
    (If you do not have a requirements.txt file you can create it manually by running pip freeze > requirements.txt once you have the environment with all packages you want to install)

3.  *Run the Streamlit App:*
    bash
    streamlit run Calories_burnt_Prediction.py
    

    This command will open the app in your browser (usually at http://localhost:8501).

## How to Use Streamlit

Streamlit is a Python framework that makes building web apps with ease. Here's how it's used in this project:

- *streamlit as st:* This imports the Streamlit library and assigns it the alias st, making it easier to use in code.
- *st.set_page_config(...):* Configures the layout of the Streamlit app.
- *st.write(...):* Displays text, markdown, data, and other elements on the app.
- *st.sidebar:* Creates a sidebar for interactive widgets.
- *st.slider(...) and st.radio(...):* Creates interactive input widgets such as sliders and radio buttons for user inputs.
- *st.header(...):* Adds section headers.
- *st.spinner(...):* Displays a loading spinner while tasks are executing.
- *@st.cache_data and @st.cache_resource:* Caches the results of function calls. @st.cache_data is used for caching data loading functions while @st.cache_resource is used to cache resources such as machine learning models.
- *st.plotly_chart(...):* Displays interactive plots created by Plotly.
- *st.columns(...):* Creates columns for better layout and organization of elements on the page.
-  *st.write(f"..."):* used to render dynamic variables in string.

Streamlit automatically renders the web interface based on these commands. It's designed to let you write Python code that directly translates to interactive elements on a web page without the need for traditional web development knowledge such as HTML, CSS or Javascript.

## Data Sources

- The project uses two CSV files: calories.csv and exercise.csv.
- These are merged to create a combined dataset for model training.
- The data includes features like user demographics, exercise details, and calories burned.

## Model Training

- A Random Forest Regressor model is used for prediction.
- The data is preprocessed and split into training and test sets.
- The model is trained on the training data using scikit-learn, with parameters such as the number of trees and max_depth specified.
    - n_estimators=1000: This specifies that the Random Forest will use 1000 decision trees. More trees may lead to better performance but also longer training time.
    - max_features=3: This limits the number of features to be considered by a single decision tree split. It increases the diversity of the trees.
    - max_depth=6: This limits the maximum depth of each individual decision tree. This avoids overfitting while adding some complexity.

## Model Evaluation

- The model's performance is evaluated on the test set.
- Metrics like MAE (Mean Absolute Error), MSE (Mean Squared Error), RMSE (Root Mean Squared Error), and R² Score are calculated and displayed.
    - *MAE:* Average absolute difference between the actual and predicted values, in this case, kilocalories.
    - *MSE:* Average squared difference between the actual and predicted values, giving higher weight to larger errors.
    - *RMSE:* The square root of the MSE; useful because it's in the same units as the original data (kilocalories)
    - *R² Score:* Measures the proportion of variance in the dependent variable that is predictable from the independent variables, useful for judging the models accuracy.

## Tips for Improvement

The application also provides basic tips for improvement of calories burned, based on the parameters entered by the user:
- If BMI is low (less than 25), advises to increase it by building muscle.
- If the duration is short (less than 30 minutes), advises to increase exercise duration.
- If the body temperature is low (less than 38 degrees Celsius), advises to increase exercise intensity to raise the body temperature.

## Contributing

Contributions are always welcome! If you have suggestions, improvements, or bug fixes, feel free to open an issue or submit a pull request.
