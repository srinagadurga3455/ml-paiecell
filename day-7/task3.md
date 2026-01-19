task_3_model_comparison:
  title: Compare Linear vs Logistic Regression

  objective: >
    To compare the performance and suitability of Linear Regression
    and Logistic Regression for a binary classification problem.

  why_it_matters: >
    Comparing models highlights why certain algorithms are better
    suited for specific problem types and prevents incorrect model
    selection in real-world systems.

  evaluation_metrics:
    logistic_regression_metrics:
      - accuracy
      - precision
      - recall
      - f1_score

  evaluation_code: |
    from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score

    accuracy = accuracy_score(y_test, y_pred)
    precision = precision_score(y_test, y_pred)
    recall = recall_score(y_test, y_pred)
    f1 = f1_score(y_test, y_pred)

    accuracy, precision, recall, f1

  comparison_summary:
    linear_regression:
      limitations:
        - outputs_continuous_values
        - not_designed_for_binary_decisions
        - regression_metrics_less_interpretable
    logistic_regression:
      advantages:
        - outputs_probabilities
        - built_for_binary_classification
        - interpretable_metrics
        - aligns_with_real_world_decisions

  final_finding: >
    Logistic Regression is more appropriate than Linear Regression
    for predicting binary reminder decisions due to its probabilistic
    outputs and classification-specific evaluation metrics.

  conclusion: >
    Logistic Regression was selected as the final model for the mini
    project based on problem suitability and evaluation results.
