# Alphabet Soup Success Predictor
## Module 21 Challenge (Deep Learning)

In this challenge we are using machine learning and neural networks help a fictional nonprofit foundation,  Alphabet Soup, to select the applicants for funding with the best chance of success in their ventures. Using the features in the dataset, we will create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Overview
The purpose of this analysis is to look at how we processed our data for training, how we compiled our models, and how accurately our models performed. 
### Data Processing
The target variable of our dataset is the 'IS_SUCCESSFUL' column, which has either a 1 or 0, representing yes or no respectively. The predictions generated from our model will tell us whether a new line of data will be successful or not with the highest degree of accuracy possible.
</br></br>
The variables used as our features are 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', and 'ASK_AMT'. Two of these columns, 'APPLICATION_TYPE' and 'CLASSIFICATION' had over 10 different unique values, so in order to limit the number of columns once the get_dummies function was used, a cutoff value was chosen for each of them and if a value had less than the cutoff value, it was stored under "Other". 
</br></br>
The variables removed were 'EIN' and 'NAME', as these are identification columns.
## Results
### Compiling, Training, and Evaluating the Model
The first model that was ran had the following layers:
1. First Layer
  * 80 nodes
  * ReLU activation
2. Second Layer
  * 30 nodes
  * ReLU activation

</br>

![first_model_unoptimized](https://github.com/rileyunverferth/deep-learning-challenge/blob/main/Images/first_model_unoptimized.png)

</br>

This model gave us the following results:
- Accuracy: 0.7272
- Loss: 0.5592

</br>
After this model, a KerasTuner was imported and three tuner searches were run in order to find optimal hyperparameters. 
</br></br>

The first model that was run using hyperparameters found in the tuner search had the following layers:
1. First Layer
  * 111 nodes
  * Sigmoid activation
2. Second Layer
  * 33 nodes
  * ReLU activation

</br>

![first_model_optimized](https://github.com/rileyunverferth/deep-learning-challenge/blob/main/Images/first_model_optimized.png)

</br>
This model gave us the following results:
- Accuracy: 0.7273
- Loss: 0.5555
 
</br></br>

The second model that was run using hyperparameters found in the tuner search had the following layers:
1. First Layer
  * 71 nodes
  * Sigmoid activation
2. Second Layer
  * 47 nodes
  * ReLU activation
3. Third Layer
  * 53 nodes
  * ReLU activation
4. Fourth Layer
  * 131 nodes
  * ReLU activation
5. Fifth Layer
  * 45 nodes
  * ReLU activation
6. Sixth Layer
  * 105 nodes
  * ReLU activation

</br>

![second_model_optimized_1](https://github.com/rileyunverferth/deep-learning-challenge/blob/main/Images/second_model_optimized_1.png)
![second_model_optimized_2](https://github.com/rileyunverferth/deep-learning-challenge/blob/main/Images/second_model_optimized_2.png)

</br>
This model gave us the following results:
- Accuracy: 0.7279
- Loss: 0.5758

</br></br>

The third model that was run using hyperparameters found in the tuner search had the following layers:
1. First Layer
  * 93 nodes
  * ReLU activation

</br>

![third_model_optimized](https://github.com/rileyunverferth/deep-learning-challenge/blob/main/Images/third_model_optimized.png)

</br>
This model gave us the following results:
- Accuracy: 0.7282
- Loss: 0.5548

</br></br>
The goal of running the optimizations for the models was to get a model that had at least 75% accuracy. Unfortunately, the highest accuracy percentage that was yielded was 72.82%. In pursuit of this percentage, the numbers of hidden layers were changed, the number of nodes per layer changed, and the activation method was changed, yet a combination that satisfied our goal was not found. 


## Summary
In summary, using machine learning and neural networks on our processed data, a model was created that can with 72.82% accuracy predict whether or not an applicant will be successful if funded by Alphabet Soup. The model did not perform as well as was hoped, so perhaps a different model would work better. Some ways to further improve the model would of course be to try more combinations of number of layers, number of nodes, and activation types, but also dropping potentially misleading features, increasing  or decreasing the number of values for each bin, or adding or reducing the number of epochs to the training regimen.

