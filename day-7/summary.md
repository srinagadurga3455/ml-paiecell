day_7_logistic_regression_theory:

  title: Logistic Regression and Binary Classification

  purpose: >
    Day 7 introduces Logistic Regression, a supervised learning
    algorithm used for binary classification problems. This day
    focuses on understanding when to use Logistic Regression,
    how it works internally, and why it is more suitable than
    Linear Regression for decision-based tasks.

  when_to_use_logistic_regression:
    description: >
      Logistic Regression is used when the target variable has
      two possible outcomes and the goal is to predict the
      probability of one class occurring.

    suitable_cases:
      - yes_or_no_decisions
      - true_false_predictions
      - binary_labels_0_and_1
      - probability_based_decisions

    examples:
      - spam_vs_not_spam
      - fraud_vs_not_fraud
      - disease_present_or_not
      - send_reminder_or_not

  binary_classification:
    definition: >
      Binary classification is a supervised learning task where
      each input is assigned to one of two possible classes.

    characteristics:
      - exactly_two_classes
      - discrete_output
      - decision_threshold_required

    relation_to_project:
      target_variable: should_remind_now
      class_0: do_not_remind
      class_1: remind_now

  logistic_regression_intuition:
    core_idea: >
      Logistic Regression models the probability that an input
      belongs to the positive class by applying a sigmoid function
      to a linear combination of features.

    comparison_with_linear_regression:
      linear_regression:
        output: unbounded_real_values
        limitation: >
          Outputs are not constrained between 0 and 1, making it
          unsuitable for probability estimation.
      logistic_regression:
        output: probability_between_0_and_1
        advantage: >
          Outputs can be directly interpreted as class probabilities.

  sigmoid_function:
    purpose: >
      The sigmoid function converts any real-valued number into
      a value between 0 and 1.

    intuition:
      - large_positive_input_results_in_probability_close_to_1
      - large_negative_input_results_in_probability_close_to_0
      - middle_values_produce_uncertain_probabilities

    role_in_logistic_regression: >
      It allows the model to map linear scores into probabilities,
      enabling binary decision-making.

  model_output_and_decision:
    probability_output: >
      Logistic Regression outputs a probability score indicating
      the likelihood of the positive class.

    decision_threshold:
      default_value: 0.5
      explanation: >
        If the predicted probability is greater than or equal to
        the threshold, the model predicts class 1; otherwise,
        it predicts class 0.

    flexibility: >
      The threshold can be adjusted based on business or product
      requirements.

  why_logistic_over_linear:
    explanation: >
      Logistic Regression is preferred over Linear Regression
