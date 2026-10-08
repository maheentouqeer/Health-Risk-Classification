# open-ended
Maheen Touqeer
24F-AI-001

1. Data Preprocessing

Handling Missing Values: Clinical features such as Glucose, BloodPressure, SkinThickness, Insulin, and BMI sometimes contain 0 values. Since physical measurements of 0 are physiologically impossible, these were treated as missing indicators and successfully replaced with their column-wise median values.

Data Splitting & Scaling: The dataset was split into an 80/20 train/test distribution (stratified by the outcome to maintain target balance). The features were normalized using a standard scaler ($z$$z$-score normalization), which is especially crucial for distance-sensitive models like SVM.

2. Model Performance & Overfitting Trade-offs

Support Vector Machine (SVM):
Train Accuracy: ~89.58%
Test Accuracy: ~83.77%
Analysis: SVM shows balanced generalization. The small gap between the training and testing accuracy (approx. 5.8%) suggests that the SVM with the RBF kernel handles non-linear decision boundaries well without severely overfitting.

Decision Tree (DT):
Train Accuracy: ~93.49%
Test Accuracy: ~82.47%
Analysis: Even with a restricted depth of 5, the Decision Tree shows a higher training accuracy (93.49%) but a slightly lower test accuracy (82.47%) than the SVM. This gap of ~11% indicates a greater tendency of the Decision Tree model to overfit on the training data compared to the SVM.

3. Key Evaluation Metrics (Precision, Recall, F1-Score)

SVM achieved a higher F1-score for the positive class (diabetic, class 1) at 0.77 compared to 0.75 for the Decision Tree.

In medical prediction tasks, minimizing false negatives (high recall) is crucial. SVM achieved a solid recall of 0.78 for the positive class, whereas the Decision Tree achieved 0.74.
