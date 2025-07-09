# Cancer-Identification-Streamlit-App---Using-Logistic-Regression-Model
An interactive application that can assist medical professionals in a cytology lab in making a cancer diagnosis. Should not be used as a substitute for a professional diagnosis. Coded in Python using Visual Studio.

Used pandas, scikit-learn, plotly, numpy and --upgrade setuptools, packages to complete.

Cancer dataset pulled from Kaggle Breast Cancer Wisconsin (Diagnostic) Data Set
Website states the dataset is used to identify the probability of whether a person's cancer is benign or malignant.

##Data folder contains the Dataset

##Model folder is python code in Visual Studio that used the model from my previous project https://github.com/LTWright/Cancer-Identification-Logistic-Regression. The process was shortened to the model only (no Eploratory Data Analysis EDA). The end purpose was to create the model and the scaler pickle files that would be used to create and interactive streamlit app.

##App folder is the main effort in this excercise. The code is using the model.pkl and scaler.pkl in the model folder to create an interactive streamlit app.
The steps in creating the app are coded in containers in the python file. However they are as follows:

1. Get Clean Data:
Data os loaded directly into the app, this is acceptable as their dataset is small. Should it have been larger we would have stripped the needed values from the data (ie max, min mean values for each value in the sidebar (slider)

3. Add Sidebar:
Creates the sidebar with sliders for each of the 30 variables. Each individual value slider takes into acount min, max, mean to assist the lab techs. 

5. Get Scaled Values
The values are then scaled from their actual to a representaion of the actual from 0 to 1. This was necessary for plotting many variables onto a single radar chart.

6. Get Radar Chart:
Although there are 30 variables, there are only 10 categories. Each category has a mean, se and worst plot as shown in the legend of the streamlit app. The 30 variables directly corellate to the 10 categories which enabled the use of a radar chart. The radar chart has min/max values of 0 to 1 making use of the scaled values from the last step.

8. Add Predictions:
This portion loads our .pkl model and scaler files into the app. This is our cancer probability model. We use this model to create a probability that the cancer values entered current/live app slider values are benign or malignant. 

10. Define main:
This step performs the formatting of the streamlit apps main page, it inludes the Sidebar in step 2 above with its sliders. It designates the sizes of our two columns with a 4 to 1 ratio. Lastly we add the radar chart created in step 4 as column 1 and predictions using the Predictions created in step 5 to output the probability that a cancer is 0 benign or 1 malignant. The lab technician may actively slide values in which they have personal concern to the left or right and make a more precise determination of whether a cancer is benign or malignant. 


#Running the Application

You must have a streamlit account. From your python application type "streamlit run"app.py file location" and a working app will load in your browser. You will be prompted for your streamlit password and then the app will run.

#Web Based Cloup App

With no modification the code may be loaded onto streamlit cloud and you are hosting a medical cancer identification app usable from anywhere. Only requires a GITHUB account to log into and a package requirements file. Both easy and free to acheive.
