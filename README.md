# Email-spam-Detection-using-MCDM-algorithm
Import the necessary libraries: The code starts by importing the required libraries, including pandas for data handling, scikit-learn for machine learning operations, and MinMaxScaler for data normalization.

Load the email dataset: The code reads the email dataset from a CSV file using pandas and assigns it to the data variable.

Preprocess the data: The email text data is preprocessed using the CountVectorizer class from scikit-learn. It converts the text data into a numerical representation (term frequency matrix). The target variable (y) is assigned as the 'Label' column from the dataset.

Split the data: The dataset is split into training and testing sets using the train_test_split function from scikit-learn. It randomly splits the data into a training set (X_train, y_train) and a testing set (X_test, y_test) with a test size of 20%.

Train the random forest classifier: A random forest classifier is trained using the RandomForestClassifier class from scikit-learn. It uses 100 decision trees for classification.

Make predictions on the test set: The trained classifier is used to make predictions on the testing set (X_test). The predicted labels are stored in the y_pred variable.

Evaluate the model: The code calculates various evaluation metrics such as accuracy, precision, recall, and F1 score to assess the performance of the classifier.

Calculate the PROMETHEE scores: The PROMETHEE scores are calculated based on the predicted probabilities obtained from the random forest classifier. The 'Predicted_Probability' column is added to the dataset as 'Spam_Probability'.

Normalize the PROMETHEE data: The 'Spam_Probability' values are normalized using the MinMaxScaler from scikit-learn. This step ensures that the values are within the same range.

Calculate the PROMETHEE preference index: The preference matrix is constructed by comparing each pair of alternatives (emails) based on their normalized 'Spam_Probability' values. The preference index is calculated as the difference between the number of alternatives preferred and the number of alternatives not preferred.

Calculate the PROMETHEE preference flow: The preference flow is calculated for each alternative by summing the preference indices for that alternative and subtracting the sum of preference indices for all other alternatives.

Calculate the final rankings: The alternatives (emails) are ranked based on their preference flow in descending order.

Print the final rankings: The code prints the final rankings of the emails, along with their text and corresponding spam probabilities.
