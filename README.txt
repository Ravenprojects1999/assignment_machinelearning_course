Predicting gait cycle phases based on angular kinematics in normal, knee brace and ankle brace gait.

#### Overview ####

This project the open source Kaggle data set 'Enhanced Gait Biomechanics Dataset' to predict the percentage of the gait cycle based on leg angular kinematics. To predict this a standard regression model was used and improved by adopting cyclicity in the data.

The overall goal was to demonstrate that predicting gait cycle percentage can be done through a model, regardless of knee and ankle braces. Furthermore, this model emphasizes the fact that gait is cyclic in nature and should be modelled as such.

#### Data ####

The data can be downloaded from:
https://www.kaggle.com/datasets/anitarostami/enhanced-gait-biomechanics-dataset

key variables:
- subject: 1 = subject 1, …, 10 = subject 10 (integer)
- condition: 1 = unbraced, 2 = knee brace, 3 = ankle brace (integer)
- replication: 1 = replication 1, …, 10 = replication 10 (integer)
- leg: 1 = left, 2 = right (integer)
- joint: 1 = ankle, 2 = knee, 3 = hip (integer)
- time: 0 = 0% gait cycle, …, 100 = 100% gait cycle (integer)
- angle: Joint angle in degrees (real valued)
- velocity: Normalized velocity of joint angle (real valued)
- acceleration: Normalized acceleration of joint angle (real valued)

#### Requirements ####

The code is written in jupyter notebook. Therefore, the user requires a working jupyter notebook environments. To run the code within this environment the user requires the fallowing packages:
- numpy
- pandas
- matplotlib
- scikit-learn
- kagglehub

which can all be installed through pip install. 

#### Running the code ####

step 1:
download the 'gait percentage prediction model.ipynb'

step 2:
open the file within your jupyter notebook environment.

step 3:
running the code. The whole code consists of 5 sections:
1: loading the data and basic data frame transformations
2: This section divides the data into training and testing data while separating randomly for participants. After this the data is thrown into a random forest regression model and its performance is evaluated over three seeds using a circularity adjusted root mean difference (RMD) of the predicted and actual outcome.
3: In this section the model's quality is displayed for each of the conditions with figures showing the predicted vs actual outcome values and the spread of the difference between these.
4 & 5: in section 4 and 5 these steps are repeated after transforming the data to an cos and sin variant of time so that there is a better circular interpretation of the data. Al together demonstrating improved prediction accuracy.

#### Outputs ####

This script gives: 
- The RMD values for both models.
- Scatter plots of predicted vs actual gait cycle percentage
- Histograms of prediction error distances
