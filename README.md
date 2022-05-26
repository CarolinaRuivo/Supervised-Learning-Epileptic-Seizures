# Supervised-Learning-Epileptic-Seizures

Curricular Unit: Machine Learning in Bioengineering.
Goal: Exploration of Supervised Learning Methods for the Identification of Epileptic Seizures (binary task) and the Distinction between Epileptic Seizures (multiclass task).

Files in this folder:
1. MLB-features/MSEL_00172/features_b_ACC-BVP-EDA-HR-TEMP_20s_50 - baseline data (data when the patient was not having a seizure).
2. MLB-features/MSEL_00172/features_s_ACC-BVP-EDA-HR-TEMP_20s_50 - seizures' data (data when the patient was having a seizure).
3. MSEL_00172 - contains information about all seizures the patient had: type of seizure, when it started and when it ended.
3. The script - Patient 00172.ipynb

Main conclusions of the project:
Overall, AdaBoost and Random Forest presented the best balanced accuracies. 
LDA has lower computational demand, and so it can provide a more cost-effective solution, alongside the non linear Decision Tree.
Stepwise feature selection (with grid search), overall, led to better or similar results and less computation time than using all features. 
Combining the correlation filter method with stepwise did not produce good enough results.
PCA was not viable, once more than 20 PCs would be needed to keep 80% of the original variability. 
As expected, the balanced accuracy for the binary task (just distinguishing if the patient was having a seizure or not) was higher than the balanced accuracy for the multiclass task (which aimed at distinguishing if the patient was having a seizure or not, and which type of seizure it was).

Regarding the poor results of PCA, it may be because it does not take classes’ information into account, i.e., it just looks at the variance of each feature and assumes that high variance is better, but it may not be related with the outcome whatsoever.
Regarding the poor results of the correlation filter method, one must keep in mind that filter methods ignore the interaction with the classifier, and each feature is considered independently. Also, ther isn’t a threshold for selecting only the required features and exclude noise.
