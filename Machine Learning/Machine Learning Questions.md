# Machine Learning Questions for Data Science/Data Analytic Roles #

## Questions & Answers ##

### Q1: Why do we split data into training and test data? ###

Answer:

When we train a model, the hope is that we will then be able to apply this model to new data and generate accurate predictions. Before we deploy a model that has been trained, it should be tested on data it has never seen before to ensure our model performs as we advertise. We can do this by splitting our data we have during model development into a training dataset -- data used to help the model "learn" -- and into a test dataset -- the unseen data used to see how well our trained model performs on new data.

Using Scikit-Learn's *train_test_split* method will easily create these datasets for us, with the control over what percentage of the data should be allocated to the training versus testing data, if we want to randomly shuffle the data, apply a seed for reproducibility of the random shuffle of the data, as well as other options (explained in the Scikit-Learn documentation).


### Q2: Why is it important to standardize data for machine learning models before fitting? ###

Answer:

Before answering why standarization is important, we should know what is meant by standardizing data. Standardizing data is taking data from a dataset and scaling it a common scale. A common way to do this is to scale the data such that it has a mean of zero and a standard deivation of 1:

$$
\begin{align*}
\bar{x}=\frac{x-\mu}{\sigma}
\end{align*}
$$

where $\bar{x}$ is the scaled data, $x$ is the original data, $\mu$ is the mean of the data, and $\sigma$ is the standard deviation of the data.

The reason for standardizing the data is to reduce introduced bias in our model from having data with different ranges of values. If we have some data that's range of possible values is much larger than another, our model may favor the larger valued data. Scikit-Learn's StandardScaler class allows for an easy implementation of such stadardization. Using the *fit_transform* method, we can pass column(s) from a data frame to the *StandardScaler* object and return standardized columns as inputs into our model.


### Q3: What is continuous numerical data in Machine Learning? Give an example. ###

Answer:

A continuous numerical variable is a variable that can take on any (real) value, including decimals. An example of a continuous numerical variable is a person's weight, where the value could be 100 lbs, 100.5 lbs, 100.345678987654567... lbs. 


### Q4: If a target column in the dataset has 0s and 1s, is this a classification or regression problem? ###

Answer:

The target column is the column of data in a dataframe that we are trying to solve for with our model. If the column is only 0 or 1, we can think of this as a classification problem, where 1 represents an event being true and a 0 representing an event being false. An example of this could be determining if a medical test result is positive or negative. This specific type of classification is known as binary classification (only a True or False event, not multiclass).

If the target column contained continuous numerical data (defined in Q3), than the problem would be a regression problem.

### Q5: ###
