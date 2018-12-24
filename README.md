# comparing-handwriting-samples-MachineLearning

Problem-:
The problem that we are trying to solve here is to find the similarity between the samples of the known and the questioned writer, using the linear and logistic regression. Though the similarity can be decided using 0 or 1, but we would be using the real values computed out of linear regression, and for logistic regression it would be a 2-class classification problem

DataSet-: The data set available is an AND dataset, which means that every writer was asked to write 3 manuscripts, image of AND was extracted from each of these manuscripts. Every image has got an image id , for example 1121a_num1, in which  1121 is the writer Id, a refers to the page and num1 refers to the sample number on that page. From these extracted images features have been extracted, thus leading to the formation of the 2 data sets-: 
 
1)Human Observed DataSet-: This dataset is based upon the features extracted manually from the images and for each sample extracted we have  got  9 features. 

2)GSC Dataset-: This dataset has been extracted from the images using a GSC algorithm which has got 512 features. 

Why Scheme is required-: 
Our one data sample is actually the comparison between two image samples, and with that input for linear regression (black box) is always a vector, so to get resulting Vector, which would be acting as features for our data sample, I would be using two schemes on each data set-: 

1)Subtraction Scheme-In this for comparing two image samples, the samples of GSC dataset from the human dataset would be subtracted, which results in the same number of features.  

2)Concatenation Scheme-In this scheme instead of subtracting, the features of the GSC dataset would be getting concatenated with the features of the Human Observed data set. Thus total features would be equal to double the features for an image. 


Linear Regression: 

Setup-: 

1) Creation of the design matrix using gaussian radial basis function from the data matrix available for training, validation and test.  2) Applying linear regression to predict weights, using SGD for updating weights


Logistic Regression-: 
A function takes inputs and returns outputs. To generate probabilities, logistic regression uses a function that gives outputs between 0 and 1 for all values of X. There are many functions that meet this description, but the used in this case is the logistic function. From here we will refer to it as sigmoid. 

Setup-: 

1)Using the data matrix as the input, as sigmoid is itself a non linear function so won’t be needing the basis fucntions. 
 
2)Computing the logistic regression with the randomly initialized weights using training data set , using gradient descent for updating the weights. 3)Evaluating on the basis of the accuracy, as it is a logistic regression. Though the output of the sigmoid functions would be between 0 and 1, but we can round off the value to make it in a discreet form








