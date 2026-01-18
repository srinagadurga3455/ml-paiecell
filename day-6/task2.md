task_2_train_linear_regression:
  title: Train Linear Regression Model

  objective: >
    To train a baseline machine learning model using Linear Regression
    and understand the supervised learning workflow.

  why_it_matters: >
    Linear Regression is used as a simple baseline model to understand
    how features influence predictions and how model training works
    before using more complex classification algorithms.

  model_details:
    algorithm: Linear Regression
    library: scikit-learn
    problem_type: supervised_learning
    output_type: continuous_values

  training_data:
    features: X_train
    target: y_train

  code: |
    from sklearn.linear_model import LinearRegression

    model = LinearRegression()
    model.fit(X_train, y_train)

  learning_explanation: >
    During training, the model learns a weight for each feature and a bias
    term such that the prediction error on the training data is minimized.

  conclusion: >
    The Linear Regression model was successfully trained and is ready
    to generate predictions on unseen test data.
