# Neural Network Charity Analysis

# Main Objective

 The main objective of this challenge was to build a machine learning binary classifier that would accurately predict whether or not applicants for charity funds would be successful if they were funded.
Taking historical data of past funding, a model was built using TensoFlow and was attempted to be tuned to successfully predict whether a project would be succesful.

## DATA PREPROCESSING

### Columns 

 - the following is a list of the columns in the original dataset.

	-	EIN and NAME—Identification columns
	-	APPLICATION_TYPE—Alphabet Soup application type
	-	AFFILIATION—Affiliated sector of industry
	-	CLASSIFICATION—Government organization classification
	-	USE_CASE—Use case for funding
	-	ORGANIZATION—Organization type
	-	STATUS—Active status
	-	INCOME_AMT—Income classification
	-	SPECIAL_CONSIDERATIONS—Special consideration for application
	-	ASK_AMT—Funding amount requested
	-	IS_SUCCESSFUL—Was the money used effectively

 - Preprocessing Steps taken.
	- Dropped columns EIN and NAME as they are Identification fields
	- Dropped SPECIAL_CONSIDERATIONS column as I didn't believe it would have a effect on the success rate and it was after the initial model was tested without great results.
	- Used the STATUS column to drop inactive records from the dataset. Also, part of the effort to whittle down the data to produce effective results.
		- Dropped STATUS column after that step
	- Put APPLICATION_TYPE values into bins - everything with less than 500 moved to an "Other" bin.
	- Put CLASSIFICATION values into bins - everything with less than 800 moved to an "Other" bin.
	- Grouped the ASK_AMT into price ranges and then into bins to help determine if the amount requested had an impact on the success rate.
    - Used OneHotEncoder to encode a list of categorical columns.
	- Split data into test and training sets.
	- Scaled the datasets.
	
 ## Compiling, Training, and Evaluating the Model
- The first attempt was made using two hidden layers. 80 Neurons in the first hidden layer and 30 in the second. ReLU was selected as the activation function for the hidden    layers as we had the most success with this function in practice.
- The first attempt accuracy was much less than 75% at only in the low 50%'s.
- Attempts to achieve target performance included dropping more columns, binning data, adding hidden layer and neurons and changing activation functions. I was never able to get anywhere near the target of 75%.
	
## Summary

I was never able to reach the goal accuracy with the deep learning model. I think that using the ASK_AMT and how it related to the INCOME_AMT  - like what percentage of the INC_AMT is the ASK_AMT and using that number in the model would have add a useful datapoint and maybe helped get my accuracy up to an acceptable level. I didn't think of that until just now.
Changing the number of hidden layers, neurons, and activation function didn't help me at all. It makes me think that maybe I don't have enough of a grasp of how this works to make good guesses as to how to improve it.
 
