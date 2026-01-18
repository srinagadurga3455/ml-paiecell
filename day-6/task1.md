from sklearn.linear_model import LinearRegression
import pandas as pd

# Concatenate train and test for consistent encoding
X_combined = pd.concat([X_train, X_test], ignore_index=True)
X_combined_encoded = pd.get_dummies(X_combined, drop_first=True)

# Split back into training and testing sets
X_train_encoded = X_combined_encoded.iloc[:len(X_train)]
X_test_encoded = X_combined_encoded.iloc[len(X_train):]

model = LinearRegression()
model.fit(X_train_encoded, y_train)