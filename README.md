# Charity-Funding-Predictor

For this part of the Challenge, you’ll write a report on the performance of the deep learning model you created for AlphabetSoup.
The report should contain the following:


Overview of the analysis: Explain the purpose of this analysis.

This is a  model designed to predict whether or not applicants for funding will be successful. 
This is a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. The purpose of this model specificaly is to predict
if the money spent on the aplicants where well spent or not. 



Results: Using bulleted lists and images to support your answers, address the following questions.



Data Preprocessing

What variable(s) are considered the target(s) for your model?

Below you will see the Features that I considered possible targets for the model

* "STATUS"
* "SPECIAL_CONSIDERATIONS"
* "IS_SUCCESSFUL"

Below you will see a list of all features and the number of unique values in each observation. 
<img width="500" alt="Screen Shot 2022-08-07 at 2 32 02 PM" src="https://user-images.githubusercontent.com/96738642/183307923-08ec4238-7c47-42d4-b72b-740bf3c31539.png">
The reason that the three features stated previuosly stood out to me is
because of the binary structure held in the those three variables. Once the structre of the data set was reveled I took a deeper dive into what would be an effective target
out of the three columns.






What variable(s) are considered to be the features for your model?
What variable(s) are neither targets nor features, and should be removed from the input data?


Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take to try and increase model performance?





Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

