task_2_train_logistic_regression:
  title: Train Logistic Regression Model

  objective: >
    To train a Logistic Regression model for predicting whether
    a reminder should be triggered.

  why_it_matters: >
    Logistic Regression is designed for binary classification and
    outputs probabilities, making it suitable for decision-based
    systems such as notifications and alerts.

  model_details:
    algorithm: LogisticRegression
    library: scikit-learn
    output_type: probability_between_0_and_1

  input_data:
    features: X_train_encoded
    target: y_train

  training_code: |
    from sklearn.linear_model import LogisticRegression

    log_model = LogisticRegression(max_iter=1000)
    log_model.fit(X_train_encoded, y_train)

  prediction_code:
    probabilities: |
      y_prob = log_model.predict_proba(X_test_encoded)[:, 1]
    final_predictions: |
      y_pred = log_model.predict(X_test_encoded)

  learning_explanation: >
    The model learns feature weights that estimate the probability
    of the positive class using a sigmoid function.

  conclusion: >
    The Logistic Regression model was successfully trained and
    generated probability-based predictions on unseen data.
