## INTRODUCTION
Project 4: SafeComm Digital Security Solutions uses machine learning to identify phoney SMS texts. The initiative aims to automatically detect possible fraud by examining trends in message data, improving digital security for communication networks.

## METHODS
We decided to use Python for this project in a Jupyter Notebook setting, utilising packages like Matplotlib for visualisation  step that gave us the possibility of creating many graphs covering fews subjects as :

-sms length , (perceive a lenght difference between fraudolent and non fraudolent message as the fraudolent ones are generally shorter )

-the distribution of non and fraudulent messages (shows a considerabel inbalance between the distribution of fraudulent and non-fraudulent messages) 

-the words frequency in a fraudulent sms 
and finally the distribution of messages per month and year 
But we just kept tree parameters to proceed forward with . 



Additionally we used Scikit-learn for training models, and Pandas for data processing. Text length, time stamps, and TF-IDF ratings derived from message content were among the features we used. 

We employed class weights to manage unbalanced datasets and concentrated on the appropriateness of Random Forests, Decision Trees, and Logistic Regression for classification tasks. These models were selected based on how well they handled binary classification issues and how easily they could be understood. By enclosing the environment setting in a Conda environment, which makes it simple to duplicate, we assured repeatability.


## EXPERIMENTAL DESIGN
Our tests were conducted with the aim of determining the optimal model for SMS fraud detection. Our baseline models were the selected algorithms' default settings. Since these metrics are important for evaluating the performance of classification models, particularly in unbalanced datasets, we used accuracy, precision, recall, and F1 score as our evaluation metrics.  

We also used different  hyparameter to finesse and optimize  our models : here are they 
Each of these hyperparameters is adjusted with the intent to improve the model's ability to correctly classify SMS messages as fraudulent or non-fraudulent. By tuning these parameters, the model can potentially achieve a better balance between bias and variance, ultimately leading to more accurate and generalized predictions on unseen data.

Logistic Regression:
C: This is the inverse of regularization strength; smaller values specify stronger regularization. Adjusting this hyperparameter helps to prevent overfitting and underfitting by controlling the complexity of the model.
penalty: Specifies the norm used in the penalization (regularization term). The choices of penalties, such as L1 or L2, affect feature selection, with L1 having the ability to select only a subset of features.
solver: Algorithm to use in the optimization problem. Different solvers are more suitable for certain types of data and models, and choosing the right one can affect both the performance of the model and the speed of the training process.
class_weight: Used to handle imbalanced data. Setting this to 'balanced' automatically adjusts weights inversely proportional to class frequencies in the input data.
max_iter: Maximum number of iterations taken for the solvers to converge. This is set to a higher number to ensure convergence when the default iterations are not enough.
Decision Tree:
criterion: The function to measure the quality of a split. 'Gini' for the Gini impurity and 'entropy' for the information gain.
max_depth: The maximum depth of the tree. Limits the number of splitting points and can prevent overfitting.
min_samples_split: The minimum number of samples required to split an internal node. A higher value prevents the model from learning too much noise in the training data.
min_samples_leaf: The minimum number of samples required to be at a leaf node. This smoothens the model, especially for regression.
max_features: The number of features to consider when looking for the best split. This can help in reducing the variance of the model and thus overfitting.
class_weight: Similar to Logistic Regression, used to make the model pay more attention to the minority class.
Random Forest:
n_estimators: The number of trees in the forest. A higher number of trees increases the performance of the model at the cost of computational efficiency.
max_depth, min_samples_split, min_samples_leaf, max_features, and class_weight: These parameters serve the same purpose as in the Decision Tree model but are applied across the ensemble of trees.

## RESULTS
As a consequence of its effectiveness with the linear nature of the characteristics and the interpretability of its coefficients, Logistic Regression proved to be very beneficial, even if all of the models performed well, according to our data. Transparency and reproducibility are ensured if and buy using ROC curves and confusion matrices that are produced straight from the code to display our findings.

## CONCLUSION 
The project's key finding is that, by striking a balance between interpretability and accuracy, logistic regression is a useful tool for identifying whether or not SMS messages are fake. Still, there are concerns about how well the model works in a real-world situation where the data might not be as well divided. To further improve the robustness and dependability of the model, future research should investigate deeper text analysis using natural language processing techniques and the incorporation of more varied datasets.
