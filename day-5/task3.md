task_3_finalize_features:
  task_name: Finalize Features for Model Training
  objective: >
    Finalize the feature set and target variable after visualization
    and pattern analysis.

  target_variable:
    name: should_remind_now
    type: binary

  feature_groups:
    numerical_features:
      - hour
      - day_of_week
      - is_weekend
      - minutes_to_event
      - device_silent_mode
      - time_since_last_reminder

    categorical_features:
      - event_type
      - event_priority
      - user_location
      - screen_state
      - last_response

  feature_target_creation:
    description: Separate features and target using Pandas
    code: |
      target = "should_remind_now"

      X_df = df.drop(columns=[target])
      y_df = df[target]

      print(X_df.shape)
      print(y_df.shape)

  validation_checks:
    description: Ensure correct separation
    code: |
      X_df.head()
      y_df.head()

  final_status:
    total_features: 11
    dataset_ready_for:
      - categorical encoding
      - train_test_split
      - model training
