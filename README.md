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
    * In the original model, two input layers and one output layer were chosen.  The first input layer had 80 neurons with a "Relu" activation function, the second input layer had 30 neurons also with a "Relu" activation function, and the output layer had 1 neuron with a "Sigmoid" activation function.  The "Relu" function was used because there were no negative values in the dataset and it is the most widely used activation function and according to the website <a href= "https://towardsdatascience.com/activation-functions-neural-networks-1cbd9f8d91d6" target="_blank">Toward Data Science</a>, "it is used in almost all the convolutional neural networks or deep learning".  The "Sigmoid" activation function was used for the output layer because it is ideally used for binary output between 0 and 1.

How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take to try and increase model performance?

![NaiveRandomOversampling](https://user-images.githubusercontent.com/77071776/124400906-8747ff80-dceb-11eb-8a03-f371db85f173.PNG)

* The balanced accuracy score of the SMOTE Oversampling is 62.67%
* The precision of the imbalanced classification report for the SMOTE Oversampling is 0.01 for the high-risk class and 1.00 for the low-risk class
* The recall of the imbalanced classification report for the SMOTE Oversampling is 0.61 for the high-risk class and 0.64 for the low-risk class

![SmoteOversampling](https://user-images.githubusercontent.com/77071776/124400916-97f87580-dceb-11eb-8188-c168a32650c1.PNG)

* The balanced accuracy score of the Cluster Centroids Undersampling is 52.93%
* The precision of the imbalanced classification report for the Cluster Centroids Undersampling is 0.01 for the high-risk class and 1.00 for the low-risk class
* The recall of the imbalanced classification report for the Cluster Centroids Undersampling is 0.61 for the high-risk class and 0.45 for the low-risk class

![ClusterCentroidsUndersampling](https://user-images.githubusercontent.com/77071776/124402077-5b307c80-dcf3-11eb-8ac6-d0e9ce45aaaf.PNG)

* The balanced accuracy score of the SMOTEENN (Over and Under) Sampling is 62.48%
* The precision of the imbalanced classification report for the SMOTEENN (Over and Under) Sampling is 0.01 for the high-risk class and 1.00 for the low-risk class
* The recall of the imbalanced classification report for the SMOTEENN (Over and Under) Sampling is 0.71 for the high-risk class and 0.54 for the low-risk class

![SMOTEENN](https://user-images.githubusercontent.com/77071776/124400926-b8283480-dceb-11eb-8890-1ff3949c8ccf.PNG)

* The balanced accuracy score of the Balanced Random Forest Classifier is 78.78%
* The precision of the imbalanced classification report for the Balanced Random Forest Classifier is 0.04 for the high-risk class and 1.00 for the low-risk class
* The recall of the imbalanced classification report for the Balanced Random Forest Classifier is 0.67 for the high-risk class and 0.91 for the low-risk class

![BalancedRandomForestClassifier](https://user-images.githubusercontent.com/77071776/124400947-dc841100-dceb-11eb-83e0-3decd43cd269.PNG)

* The balanced accuracy score of the Easy Ensemble Classifier is 92.54%
* The precision of the imbalanced classification report for the Easy Ensemble Classifier is 0.07 for the high-risk class and 1.00 for the low-risk class
* The recall of the imbalanced classification report for the Easy Ensemble Classifier is 0.91 for the high-risk class and 0.94 for the low-risk class

![EasyEnsembleClassifier](https://user-images.githubusercontent.com/77071776/124400951-e279f200-dceb-11eb-8ece-d29a3ec4695f.PNG)



## Summary
Because of the significance of the imbalance between the low-risk and high-risk class, the precision in the classification report isn't going to represent the entire story.  In this case, the recall (or accuracy) score should share more of the story.  The Easy Ensemble Classifier is the model that should be used because of the greatest accuracy of any of the models.  In combination with the accuracy score of 92.54% shown by the Easy Ensemble Classifier, the precision and recall scores place this model above the other five.  
