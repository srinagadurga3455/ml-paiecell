day5_data_visualization_and_preprocessing:
  purpose: >
    To understand the dataset visually and conceptually before
    training a machine learning model. Visualization helps reveal
    patterns, distributions, and anomalies. Preprocessing prepares
    features for effective learning.

  data_visualization:
    definition: >
      The graphical representation of data to understand patterns,
      relationships, distributions, and anomalies.

    why_it_is_important:
      - reveals class imbalance
      - shows feature-target relationships
      - helps detect outliers
      - prevents blind modeling
      - improves feature selection decisions

    common_plot_types:
      line_plot:
        use_case: visualize trends over ordered values
        example_features:
          - hour vs should_remind_now (mean)
        insight: time-based patterns

      bar_plot:
        use_case: compare categorical distributions
        example_features:
          - event_type vs should_remind_now
          - user_location vs should_remind_now
        insight: category influence on target

      scatter_plot:
        use_case: visualize relationship between two numerical features
        example_features:
          - minutes_to_event vs time_since_last_reminder
        insight: clustering, separation, outliers

    data_distribution:
      definition: >
        The spread of values within a feature.
      importance:
        - identifies skewed features
        - detects extreme values
        - informs preprocessing decisions

  preprocessing:
    definition: >
      The process of transforming clean data into a format
      suitable for machine learning algorithms.

    preprocessing_is_not:
      - data cleaning
      - model training
      - hyperparameter tuning

    preprocessing_steps:
      feature_selection:
        purpose: >
          Decide which features should be used for model training.
        criteria:
          - relevance to target
          - non-redundancy
          - interpretability

      encoding:
        purpose: >
          Convert categorical text features into numerical form.
        methods:
          - label_encoding
          - one_hot_encoding

      scaling:
        purpose: >
          Ensure numerical features are on comparable scales.
        examples:
          - normalization
          - standardization
        note: optional for some models

      train_test_split:
        purpose: >
          Separate data for learning and evaluation to prevent data leakage.

    relationship_to_visualization:
      visualization_guides:
        - which features to keep
        - which features to drop
        - which features may dominate learning
        - whether target imbalance exists

  key_principles:
    - visualize before modeling
    - do not encode blindly
    - understand target distribution
    - preprocessing decisions must be explainable
