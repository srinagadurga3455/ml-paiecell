day6_data_splitting_and_linear_regression:
  purpose: >
    Introduce the first machine learning model and the concept of
    honest evaluation using train-test split. This day establishes
    the core ML workflow used in all supervised learning tasks.

  train_test_split:
    definition: >
      The process of dividing the dataset into two parts so that
      model training and model evaluation happen on separate data.

    why_it_is_needed:
      - prevents memorization
      - simulates real-world prediction
      - reveals overfitting or underfitting

    typical_split_ratio:
      train: 80_percent
      test: 20_percent

    key_rule: >
      The test set must never be used during training.

  overfitting:
    definition: >
      A situation where the model learns training data too well,
      including noise, and fails to generalize to new data.

    symptoms:
      - high training performance
      - poor testing performance

  underfitting:
    definition: >
      A situation where the model is too simple to capture
      underlying patterns in the data.

    symptoms:
      - poor training performance
      - poor testing performance

  linear_regression:
    intuition: >
      Linear Regression learns a linear relationship between
      input features and the target variable.

    equation:
      form: y = w1*x1 + w2*x2 + ... + b

    learning_process:
      - initialize weights
      - predict outputs
      - calculate error
      - update weights to reduce error

    output_type:
      - continuous numeric value

  evaluation_metrics:
    purpose: >
      Quantify how well the model predictions match true values.

    metrics_used:
      mean_absolute_error:
        description: average absolute prediction error
      mean_squared_error:
        description: squared error penalizing large mistakes
      r2_score:
        description: how well variance is explained

  key_principles:
    - never evaluate on training data
    - simpler models first
    - evaluation metrics matter more than accuracy here
