## Overview   
The purpose of this analysis to evaluate the effectiveness of a deep learning model (binary classifier utilizing a neural network) used to predict whether organizations funded by Alphabet Soup will be successful.

## Results   
**Data Preprocessing**
* Variable used as the target class for the model: 
    * IS_SUCCESSFUL
* Variables used as the features for the model:
    * APPLICATION_TYPE
    * AFFILIATION
    * CLASSIFICATION
    * USE_CASE
    * ORGANIZATION
    * STATUS
    * INCOME_AMT
    * SPECIAL_CONSIDERATIONS
    * ASK_AMT
* Variables removed from the dataset becuase they did not contribute to the analysis:
    * EIN
    * NAME

**Compiling, Training, and Evaluating the Model**
* The final model consisted of:
    * Four layers (initial input layer, two hidden layers, and an output layer). Attempting to add a third hidden layed resulted in reduced performance (higher loss, lower accuracy)
    * Two-hundred thirty-three neurons (116 in the initial layer to match the final number of features, 58 in each hidden layer, one in the output layer).
    * Three activation functions (ReLU, tanh, sigmoid).
* The target model performance was 75% accuracy. The model reached 72.91% accuracy.
* In an effort to increase model accuracy, the model was modefied by:
    1. Adding an additional hidden layer, which was later removed due to decreased accuracy.
    2. Increasing the number of nodes in the second hidden layer from 29 to 58, resulting in increased accuracy and lower loss. This iteration of the model gave the highest accuracy: 72.99%.
    ![Trial #2 Layers](/Images/Trial2Layers.png)
    3. Changing the activation function of the second hidden layer to tanh from ReLU. This resulted in lower accuracy but also lower loss.
    4. Increasing the number of epochs in the training phase from 150 to 300. This resulted in lower loss and accuracy improving to 72.91%.
    ![Trial #4 Accuracy and Loss](/Images/Trial4AccuracyLoss.png)

## Summary   
The overall result of the model was a neural network that functioned as a binary classifier with 72.91% accuracy and 0.5599 loss.

Another candidate for addressing this classification problem would be the random forest model. Random forest tends to outperform other classifiers. Additionally with time, the complexity of the features could be reduced through additional binning (e.g. the ask amount).