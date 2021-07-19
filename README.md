# Alphabet Soup Neural Network Charity Analyisis


## Project Overview of the Analysis
#### The goal of this project was to build a machine learning neural network model that would be capable of predicting whether charities would be successful if given funds by Alphabet Soup, a funding source.
Using a dataset provided by Alphabet Soup with more than 34,000 organizations that received funding by their organization over the years, a binary classifier was created that would be able to predict success.  The dataset was preprocessed for input into the neural network model and then scaled, split into training and test data components, and then plugged into that model.  

#### Resources
- Data Source: <br>
`Resources/charity_data.csv`

- Software:  Jupyter Notebook
- Languages:  Pandas, Python
- Libraries:  `tensorflow`  `scikit-learn` `sci-kit learn`

  
## Results of the Analysis
* Data Preprocessing
    * The variable that was considered the target for the model was the "IS_SUCCESSFUL" column in the dataset.  In the original dataset this column was filled with "1's" and "0's" based on whether the applicant used the funds successfully.  Because determining the success of the applicants was the desired outcome of the model, this was the chosen target value.
    * Of the original 12 columns in the DataFrame, "EIN" and "NAME" were dropped because they had no specific value to the model.  The features of the model were the remaining columns.
* Compiling, Training, and Evaluating the Model
    * In the original model, two input layers and one output layer were chosen.  The first input layer had 80 neurons with a "Relu" activation function, the second input layer had 30 neurons also with a "Relu" activation function, and the output layer had 1 neuron with a "Sigmoid" activation function.  The "Relu" function was used because there were no negative values in the dataset and it is the most widely used activation function and according to the website <a target="_blank" href= "https://towardsdatascience.com/activation-functions-neural-networks-1cbd9f8d91d6">Toward Data Science</a>, "it is used in almost all the convolutional neural networks or deep learning".  The "Sigmoid" activation function was used for the output layer because it is ideally used for binary output between 0 and 1.
    * In the first attempt at optimizing the model I conducted the same steps as in the orignal model and also "binned" the "ASK_AMT" column so that there would be 10 "Ask amount groups" instead of all the unique values that were contained in the original dataset.
    * In the second attempt at optimizing the model, I also modified the deep learning model by adding hidden layers and increasing the number of neurons.  I once again used the "Relu" activation function for all the hidden layers except the output layer which I also kept as "Sigmoid".
    * In the third and final attempt at optimizing the model, I tuned the hyperparameters of teh model with the Kerastuner library.

Unfortunately, none of the additional attempts that were made to optimize the model achieved the target accuracy of **75%**.  

How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take to try and increase model performance?

## Summary

