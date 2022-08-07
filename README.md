# Charity-Funding-Predictor-Report


## Overview of the analysis

This is a  model designed to predict whether or not applicants for funding will be successful. 
This is a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. The purpose of this model specificaly is to predictif the money spent on the aplicants was used effectively or not. 



## Data Preprocessing

### What variable(s) are considered the target(s) for your model?

Below you will see the Features that I considered possible targets for the model

* "STATUS"
* "SPECIAL_CONSIDERATIONS"
* "IS_SUCCESSFUL"

### list of all features and the number of unique values in each observation. 

<img width="500" alt="Screen Shot 2022-08-07 at 2 32 02 PM" src="https://user-images.githubusercontent.com/96738642/183307923-08ec4238-7c47-42d4-b72b-740bf3c31539.png">
The reason that the three features stated previuosly stood out to me is
because of the binary structure held in the those three variables. Having only 2 unique values could be usful as a target 
when making a classification model. Once the structre of the data set was reveled I took a deeper dive into what would be an effective target
out of the three columns.


### What variable(s) are considered to be the features for your model?

See the variables in each potential target feature

* "STATUS" 1,0
* "SPECIAL_CONSIDERATIONS": N,Y
* "IS_SUCCESSFUL": 1,0

### Picure of the potential targets and the count on the unique variables

<img width="500" alt="Screen Shot 2022-08-07 at 3 09 09 PM" src="https://user-images.githubusercontent.com/96738642/183309409-83467991-5751-40af-afdf-0a5586ff06d7.png">

The count of the two unique rows in the "IS_SUCCESSFUL" feature are musch more even compared to the other two. this will most likely reult in a less biased model,
and also factored into why i choice "IS_SUCCESSFUL" as the target column.

### What variable(s) are neither targets nor features, and should be removed from the input data?

* "EIN"
* "NAME"
 
 The EIN and NAME features are indifiers. both of these columns so not add to the models purpose of predicting money being well spent on orginizations. EIN is a natural
 index that would be usual for identifify trend on what orginisation Name is getting the most funding for example. In that case the columns would sty in the data set, but since we are predicting how well the money is being spent and not predicting where the money will go, there is now reason to keep these features in the data set.
 

### Picture of EIN and NAME with unique counts

<img width="500" alt="Screen Shot 2022-08-07 at 3 58 33 PM" src="https://user-images.githubusercontent.com/96738642/183310866-01716c18-bac6-48df-b2cb-3c68ced814da.png">


THis shows the EIN is an index becuase the number of unique values in the feaure is the same ammount of features in the whole data set. We do not need an index,
that will ascociate with the names in this context so they where dropped.
## Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?

### Count of neurons,layer and activation functions for Starter_Code notebook

* ns=euron count: 40. I chose 40 neurons becuase a basic rule of thumb is that the ammount of neurons should be more or less even with the amount of features which is 35.
* layer count: 1 input, 1 hidden, 1 output. I thought that a good default number is one hiden layer.
* 2 "relu", 1 "sigmoid"> I chose relu and sigmoid becuase they are the most common and reliable activation functions

<img width="500" alt="Screen Shot 2022-08-07 at 4 22 59 PM" src="https://user-images.githubusercontent.com/96738642/183311421-c561c556-9f59-4276-88ba-abf9e2d0fa45.png">

### Count of neurons,layer and activation functions for Starter_Code notebook

* nuron count: 60. To try and raise my accuracy score I raised the numbers of neurons becuase I read in the article
* layer count: 1 input, 2 hidden, 1 output
* 3 "tanh", 1 "sigmoid"

<img width="500" alt="Screen Shot 2022-08-07 at 4 28 02 PM" src="https://user-images.githubusercontent.com/96738642/183311594-e3af72db-0283-4e7b-8550-513d8cea2243.png">


Were you able to achieve the target model performance?
What steps did you take to try and increase model performance?





Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

