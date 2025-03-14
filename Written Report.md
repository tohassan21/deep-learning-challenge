Overview of the analysis:

The purpose of this analysis is to assist the nonprofit foundation Alphabet Soup by creating a tool to help them select the applicants for funding with the best chance of success in their ventures. By using our knowledge of machine learning and neural networks, we'll use the features in the dataset provided in this URL to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

Provided URL = "https://static.bc-edx.com/data/dl-1-2/m21/lms/starter/charity_data.csv"

Results:

Data Preprocessing

What variable(s) are the target(s) for your model?
- The target variable for our model is the IS_SUCCESSFUL column/feature.

What variable(s) are the features for your model?
- APPLICATION_TYPE
- AFFILIATION
- CLASSIFICATION
- USE_CASE
- ORGANIZATION
- STATUS
- INCOME_AMT
- SPECIAL_CONSIDERATIONS
- ASK_AMT_Binned
    - This variable/feature was created by taking the original ASK_AMT column and splitting it into 3 bins.

What variable(s) should be removed from the input data because they are neither targets nor features?
- EIN
- NAME
- ASK_AMT
    - This variable is dropped when creating the get_dummies dataframe because the information from this column is already not in the ASK_AMT_Binned column.

Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?
- 3 layers (first hidden layer, second hidden layer, output)
- First Hidden Layer
    - 80 neurons (less than double the number of inputs), relu activation function, 46 inputs (all of the columns in the dummies dataframe except the IS_SUCCESSFUL column because that is the target)
- Second Hidden Layer
    - 30 neurons (not too few, but still significantly less than the first layer), relu activation function
- Output Layer
    - 1 neuron, sigmoid activation function

Were you able to achieve the target model performance?
- No, I was not able to achieve the target model performance of at least 75% model accuracy.

What steps did you take in your attempts to increase model performance?
- The first step I took to attempt to increase model performance was to bin the ASK_AMT column into 3 categories during the preprocessing stage. I thought this would help because prior to that the ASK_AMT column had 8747 unique values and converting them using the Standard Scaler was not helping.
- The second step I took to attempt to increase model performance was to add a Third Hidden Layer with 15 neurons and the relu activation function.
- The third step I took to attemp to increase model performance was to decrease the epochs from 100 to 75.

Summary:
The overall results of all three of my deep learning models in attempt to increase accuracy was a 73% model accuracy score. 
If I had to recommend an additional model, it would be one that combines the changes I made in all three models (the ASK_AMT_Binned column, the Third Hidden Layer, and changing the number of epochs). I would also recommend exploring a different Optimizer like Keras Tuner because it automatically searches for the best parameters for the model.