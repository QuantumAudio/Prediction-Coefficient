# Prediction-Coefficient
The categorical prediction coefficient installation paths can be found here. This is a prerelease. Currently, only pandas DataFrames are supported inputs. A future release will support more input data types. But for now, please convert your data into a pandas DataFrame to test out this new coefficient (syntax: df = pandas.DataFrame(data) [pandas documentation](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html)). 

It is currently available through conda and pip. 

For conda, use: conda install --channel "ForDataScience" prediction-coefficient

For pip, use: pip install prediction-coefficient

Usage:

from prediction_coefficient.categorical_prediction_coefficient import categorical_prediction_coefficient_matrix as prediction_matrix

prediction_matrix(df)

The weighted prediction coefficients can be returned using prediction_matrix(df, weighted = True)

Example:

import numpy as np

import pandas as pd

from prediction_coefficient.categorical_prediction_coefficient import categorical_prediction_coefficient_matrix as prediction_matrix


df1 = pd.DataFrame({'Input Variable' : np.random.choice(['Input Value 1'], size = 20, p = [1]), 'Outcome Variable' : np.random.choice(['Outcome Value 1', 'Outcome Value 2', 'Outcome Value 3'], size = 20, p = [0.15, 0.15, 0.7])})

df2 = pd.DataFrame({'Input Variable' : np.random.choice(['Input Value 2'], size = 30, p = [1]), 'Outcome Variable' : np.random.choice(['Outcome Value 1', 'Outcome Value 2', 'Outcome Value 3'], size = 30, p = [0.65, 0.2, 0.15])})

df3 = pd.DataFrame({'Input Variable' : np.random.choice(['Input Value 3'], size = 20, p = [1]), 'Outcome Variable' : np.random.choice(['Outcome Value 1', 'Outcome Value 2', 'Outcome Value 3'], size = 20, p = [0.15, 0.6, 0.25])})

df = pd.concat([df1, df2, df3], axis = 0).reset_index(drop = True)

prediction_matrix(df)

or 

prediction_matrix(df, weighted = True)



