task_1_plot_relationships:
  task_name: Plot Relationships Between Features and Target
  objective: >
    Visualize how features relate to the target variable (should_remind_now)
    to understand patterns and influence before model training.

  dataset:
    name: synthetic_smart_reminder_data
    cleaned_rows: 429
    target_column: should_remind_now

  setup_code: |
    import matplotlib.pyplot as plt
    import pandas as pd

    # df is assumed to be the cleaned DataFrame
    # df = pd.read_csv("synthetic_smart_reminder_data.csv")

  plots:
    target_distribution:
      description: Distribution of target classes
      code: |
        df["should_remind_now"].value_counts().plot(kind="bar")
        plt.title("Target Variable Distribution")
        plt.xlabel("Should Remind Now")
        plt.ylabel("Count")
        plt.show()

    event_type_vs_target:
      description: Reminder probability by event type
      code: |
        df.groupby("event_type")["should_remind_now"].mean().plot(kind="bar")
        plt.title("Reminder Probability by Event Type")
        plt.ylabel("Probability of Reminder")
        plt.show()

    minutes_to_event_vs_target:
      description: Relationship between time to event and reminder trigger
      code: |
        plt.scatter(df["minutes_to_event"], df["should_remind_now"])
        plt.xlabel("Minutes to Event")
        plt.ylabel("Should Remind Now")
        plt.title("Minutes to Event vs Reminder Trigger")
        plt.show()

  expected_outcomes:
    - understand class imbalance
    - identify influential features
    - observe threshold-like behavior
