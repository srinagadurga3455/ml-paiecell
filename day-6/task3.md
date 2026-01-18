task_3_model_evaluation:
  title: Evaluate Model Performance

  objective: >
    To evaluate the performance of the trained Linear Regression model
    using standard regression metrics.

  why_it_matters: >
    Model evaluation helps determine how well the trained model
    generalizes to unseen data and highlights issues such as
    underfitting or overfitting.

  evaluation_data:
    test_features: X_test
    true_labels: y_test

  prediction_step:
    code: |
      y_pred = model.predict(X_test)

  metrics_used:
    mean_absolute_error:
      purpose: Measures average magnitude of prediction error.
    mean_squared_error:
      purpose: Penalizes larger errors more strongly.
    r2_score:
      purpose: Indicates how much variance in the target is explained.

  evaluation_code: |
    from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

    mae = mean_absolute_error(y_test, y_pred)
    mse = mean_squared_error(y_test, y_pred)
    r2 = r2_score(y_test, y_pred)

    mae, mse, r2

  interpretation_notes: >
    Since the target variable is binary and imbalanced, Linear Regression
    is not expected to achieve high R² scores. The evaluation highlights
    the limitations of Linear Regression for classification problems.

  conclusion: >
    Model evaluation was completed successfully, demonstrating the need
    for classification models such as Logistic Regression in the next stage.
