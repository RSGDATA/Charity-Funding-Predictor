# Charity-Funding-Predictor-Report


## Overview of the analysis

This is a  model designed to predict whether or not applicants for funding will be successful. 
This is a binary classifier that is capable of predicting whether applicants will be successful if funded. The purpose of this model specifically is to predict whether or not money was spent effectively on applicants.



## Data Preprocessing

### What variable(s) are considered the target(s) for your model?

Below you will see the Features that I considered possible targets for the model

* "STATUS"
* "SPECIAL_CONSIDERATIONS"
* "IS_SUCCESSFUL"

### list of all features and the number of unique values in each observation. 

<img width="500" alt="Screen Shot 2022-08-07 at 2 32 02 PM" src="https://user-images.githubusercontent.com/96738642/183307923-08ec4238-7c47-42d4-b72b-740bf3c31539.png">
The reason that the three features stated previously stood out to me, is
because of the binary structure held in those three variables. Having only 2 unique values could be usful as a target 
when making a classification model. Once the structure of the data was reveled, I took a deeper look into what would be an effective target
out of the three columns.


### What variable(s) are considered to be the features for your model?

See the variables in each potential target feature

* "APPLICATION_TYPE            
* AFFILIATION                  
* CLASSIFICATION              
* USE_CASE                     
* ORGANIZATION                 
* STATUS                       
* INCOME_AMT                   
* SPECIAL_CONSIDERATIONS       
* ASK_AMT  STATUS" 1,0



### Picure of the potential targets and the count of the unique variables

<img width="500" alt="Screen Shot 2022-08-07 at 3 09 09 PM" src="https://user-images.githubusercontent.com/96738642/183309409-83467991-5751-40af-afdf-0a5586ff06d7.png">

The count of the two unique rows in the "IS_SUCCESSFUL" feature are much more even compared to the other two. This will most likely reult in a less biased model,
and also factored into why I chose "IS_SUCCESSFUL" as the target column.

### What variable(s) are neither targets nor features, and should be removed from the input data?

* "EIN"
* "NAME"
 
 The EIN and NAME features are indifiers. both of these columns do not add value to the models purpose of predicting money being well spent on orginizations. EIN is a natural index that would be useful for identifying trends by organisation Name, and identifying which organization is getting the most funding as an example. In that case the columns would stay in the data set, but since we are predicting how well the money is being spent in general, these two columns do not add anything to the 
data set.

### Picture of EIN and NAME with unique counts

<img width="500" alt="Screen Shot 2022-08-07 at 3 58 33 PM" src="https://user-images.githubusercontent.com/96738642/183310866-01716c18-bac6-48df-b2cb-3c68ced814da.png">


This shows the EIN is an index becuase the number of unique values in the column is the same ammount of rows in the whole data set. We do not need an index,
that will ascociate with the names in this context so tthe two features where dropped from the data set.


## Compiling, Training, and Evaluating the Model

### How many neurons, layers, and activation functions did you select for your neural network model, and why?

### Count of neurons,layer and activation functions for Starter_Code notebook

* neuron count: 40. I chose 40 based on intuition.
* layer count: 1 input, 1 hidden, 1 output. I thought that a good default number is one hidden layer.
* function count:2 "relu", 1 "sigmoid"1. I chose relu and sigmoid becuase they are the most common and very reliable activation functions

<img width="500" alt="Screen Shot 2022-08-07 at 4 22 59 PM" src="https://user-images.githubusercontent.com/96738642/183311421-c561c556-9f59-4276-88ba-abf9e2d0fa45.png">

### Count of neurons,layer and activation functions for Starter_Code notebook 

* nuron count: 60. To try and raise my accuracy score I raised the numbers of neurons, this was an experiment and the increase of neurons do not neccesarily equate to  an improved performance in the model.
* layer count: 1 input, 2 hidden, 1 output. I chose to add a 1 extra hidden layer to the model in hopes that it would improve the score
* activation function count: 3 "tanh", 1 "sigmoid". I chose tanh becuase in the previous notebook, I chose relu. The change of activation function is an eperiment in an atempt to raise the models score

<img width="500" alt="Screen Shot 2022-08-07 at 4 28 02 PM" src="https://user-images.githubusercontent.com/96738642/183311594-e3af72db-0283-4e7b-8550-513d8cea2243.png">


### Were you able to achieve the target model performance?

I was not able to get the accuracy score higher than the 0.72 range

### What steps did you take to try and increase model performance?

### Model optimization
Below you will see my three attempts to raise the model score. Adjusting the input data to ensure that there are no variables or outliers that are causing confusion in the model.

## First Attempt
Below you will see my first attempt to raise the model score: I will change the binning threshold numbers to create more features in the models and perhaps increase the score.

In the Previous notebook, the line of code that puts rare rows into categories in the "APPLICATION_TYPE" column...
I originally set the cut off at <= 1200. I will change it to <= 500 resulting in more features after one-hot encoding

<img width="500" alt="Screen Shot 2022-08-07 at 6 20 23 PM" src="https://user-images.githubusercontent.com/96738642/183315039-184c6e5c-edd8-46bb-98a8-c113ab550933.png">

in the previous notebook, the line of code that puts rare rows into categories in the "CLASSIFICATION" column... 
I originally set the the cut off at <= 6000. I will change it to 4000 resulting in more features after one-hot encoding

<img width="500" alt="Screen Shot 2022-08-07 at 6 33 43 PM" src="https://user-images.githubusercontent.com/96738642/183315430-a7a25ce6-61f6-49c9-a8ae-6d2a0b8bc173.png">

## Result of first attempt
changing the binning cut off numbers made very little difference to the final score. Original score was 0.7219 and current is 0.7258 the difference in minimal.

<img width="500" alt="Screen Shot 2022-08-07 at 6 36 45 PM" src="https://user-images.githubusercontent.com/96738642/183315519-2cc9f1b0-ef8a-4ec0-bf17-e68f78f5e600.png">


## Second attempt
Below you will see my second attempt at improving the tensorflow model. I changed activation function from relu to tanh, I added a another hidden layer, I changed node numbers to 10,20,30 and changed epoch to 50.

<img width="500" alt="Screen Shot 2022-08-07 at 6 40 25 PM" src="https://user-images.githubusercontent.com/96738642/183315615-ab5bf343-ab80-4308-8ebe-aa0453b45327.png">


## Result of second attempt
very little defference in score after second attempt. a very slight decrease in score from 0.7258 to 0.7250. essentially no difference after adjustments have been made.

<img width="500" alt="Screen Shot 2022-08-07 at 6 44 16 PM" src="https://user-images.githubusercontent.com/96738642/183315739-7f723fcd-35d7-47c5-b929-ac7864963661.png">

## Third attempt
Below you will see feature engeneering in an attempt to increase the acurracy score. My strategy is to drop one of the other potential target columns "STATUS" and keep
the layers, nodes and activation functions the same.

<img width="500" alt="Screen Shot 2022-08-07 at 6 48 21 PM" src="https://user-images.githubusercontent.com/96738642/183315848-98ea1a75-f2a1-47ee-824d-5bcbffd3a8fd.png">

## Result of attempt 3
During this attempt I dropped the "STATUS" column. My reasoning is that this variable was another potential target that I did not choose and that perhaps does not factor into the models prediction, so if dropped, this might raise the score by clearing noise in the data.

The score remains in 0.72 range and accuracy has not changed by any meaningful ammount during all three attempts. Perhaps changing target variable or automating the 
change of layers, node amount, and activation layer by means of hyperparameter tuning may raise the score.

<img width="500" alt="Screen Shot 2022-08-07 at 6 55 49 PM" src="https://user-images.githubusercontent.com/96738642/183316137-779ff56e-02c4-480b-8150-1842d706990c.png">


Summary: Summarize the overall results of the deep learning model.

The overall result of this model is a solid 0.72. anythong over 70 percent is a decent model so overall the tensorflow neural network model was a moderate success. I have learned in this specific data architecture: Changing columns, adding rows and changing parameters has little effect in this data set. perhaps more tuning and a different approach is nesseary to raise the score to the 0.75 goal. overall the model is showing that it has a 72 percent chance of knowing if money was spent wisely or unwisely on any given organization.

## Include a recommendation for how a different model could solve this classification problem

A Random Forest classifier could be a better fit for this data, becuase a Random Forest Classifier model is specifically made to work with tubular data. A Random Forest Classifier is used for less complicated data structures than neural network models. This data set might be too simple to use a neural network model for best results. Running different algorithms will be necessary to insure that the best model was chosen.


explain your recommendation.

The tensorflow model perhaps might be better suited for a more complex data architecture. Using a Random Forest Classifier, the defalault parameters are fine tuned for tubular data and not will not have to scale the data. Random Forest Classifier will be much simpler to set up becuase of the nature of having many different trees that automatically calculate small subset problems naturally scaling the data. To put it simply, the Forest classifier is more automated and requires less parameter tuninging. NerualNetworks requirer much more manual parameter tuning for best results. This requires more trial and error apposed to a Random Forest Classifier algorithm.

Neural networks are primarly used for Images, Audio, and Text data, not tubular data. Random Forest classifier takes much less manual parameter tuning than neural networks, and should be used first, before neural network models in general. That being said, that does not mean the random forest classifier will be more effective with a tubular data set either, but the random froest classifier takes much less preprocessing and is easier to set up then neural network and would perhaps be a more natural choice before using a neural network model.

