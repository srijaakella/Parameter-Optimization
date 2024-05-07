# Parameter-Optimization
#**Methodology:**
1. **Data Preprocessing:** The dataset is loaded from a URL, with column names assigned. Categorical variables are converted to dummy variables. Certain categorical variables are encoded into numerical values for better processing.
2. **Model Training:** Support Vector Machine (SVM) classifier is employed using the `svm.SVC` class from Scikit-learn. A fitness function is defined to evaluate the accuracy of the model on test data.
3. **Hyperparameter Tuning:** The dataset is divided into training and testing sets using stratified sampling. For each sample, hyperparameters (C, gamma, kernel) are randomly selected. The model is trained using these hyperparameters, and the accuracy is evaluated. This process is repeated for a defined number of iterations.
4. **Result Storage:** The best accuracy along with the corresponding hyperparameters (C, gamma, kernel) for each sample is stored in a DataFrame.
5. **Learning Curve:** Finally, a learning curve is plotted using the hyperparameters corresponding to the sample with the highest accuracy. This curve illustrates how the accuracy of the model evolves with the increase in the training dataset size.

**Result Table:**
The result table (`df_sample`) contains the following columns:
- `sample#`: Sample number indicating the iteration.
- `best accuracy`: The highest accuracy achieved for each sample.
- `c`: The value of the hyperparameter C.
- `gamma`: The value of the hyperparameter gamma.
- `kernel`: The kernel function used.

**Result Graph (Learning Curve):**
The learning curve plots the training score and cross-validation score against the number of iterations (train sizes). It helps visualize the model's performance as more data is used for training. The training score shows how well the model fits the training data, while the cross-validation score indicates how well the model generalizes to unseen data. 

**Interpretation:**
- If the training score is high but the cross-validation score is low, it indicates overfitting.
- If both scores are low, it indicates underfitting.
- If both scores converge and are high, it indicates a well-fit model.

This methodology allows assessing the SVM model's performance and understanding how it generalizes to unseen data.
