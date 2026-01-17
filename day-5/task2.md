task_2_identify_patterns_and_outliers:
  task_name: Identify Outliers and Patterns from Plots
  objective: >
    Analyze visualizations and summary statistics to detect patterns,
    trends, and potential outliers that may affect model learning.

  analysis_steps:
    numerical_summary:
      description: Inspect numerical distributions
      code: |
        df.describe()

    target_distribution_check:
      description: Confirm target imbalance
      code: |
        df["should_remind_now"].value_counts()

    pattern_checks:
      minutes_to_event_pattern:
        observation_goal: >
          Check if reminders are more likely when minutes_to_event is small.
        code: |
          df.groupby(pd.cut(df["minutes_to_event"], bins=5))["should_remind_now"].mean()

    outlier_check:
      description: Identify extreme or unrealistic values
      code: |
        df[(df["minutes_to_event"] < 0) | (df["minutes_to_event"] > 300)]
        df[(df["hour"] < 0) | (df["hour"] > 23)]

  conclusions:
    findings:
      - reminders are more likely closer to event time
      - target is imbalanced but realistic
      - no unrealistic outliers detected
    decision:
      - no rows removed
      - retain all cleaned data
