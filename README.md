#Classification-of-Health-Care-Tickets-to-appropriate-category-based-on-written-call-summary.

Problem Statement:
LifeLine HealthServices is a top ranked Health care provider in USA with stellar credentials.
We need to classify the ticket to an appropriate category of the call written in the “Converse” column.
Following a ticketing system for all the telephonic calls received across all the departments.
The Tickets have the details of Summary of the call and description of the calls written by various staff members with no standard text guidelines.

Approach:
1. Max length has been chosen by the number of words.
2. Tokenizing the sentences into words.
3. Padding

1st Model MLP with One hot vectors:
As one-hot vectors don’t capture any relation between the words, the model was not very accurate at predicting the right class. 
Accuracy on validation – 18%
To counter the problem of vanishing gradient, we have used ReLu as the activation function.
![image](https://user-images.githubusercontent.com/34674852/142200885-439a5d73-37cd-4635-a2bb-7ab8168a0323.png)

Model 2 1D CNN:
CNN-1D captures relation between consecutive words 
Essence of sentence is captured hence the improvement in accuracy
Accuracy-70%
![image](https://user-images.githubusercontent.com/34674852/142201180-2ca583dd-4940-4180-8300-d346673d6364.png)

Model 3 LSTM:
Have used 1 hidden layers 100 units with the below features
Defined initial Dropout as 0.2 and recurrent dropout as 0.2
Final activation through softmax.
Accuracy 70%

Summary of all Models:
Embedded
Train-71.5
LSTM
Accuracy-70
MLP with Autoencoders
Train-35.7
MLP
Train-18.4, Validation-17.7
CNN
Train- 67.6 Validation-68.8



