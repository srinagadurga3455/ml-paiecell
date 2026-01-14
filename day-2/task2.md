Task 2 – Identifying Features and Target Column

| Column Name                | Data Type      | Description                                                                  |
| -------------------------- | -------------- | ---------------------------------------------------------------------------- |
| `hour`                     | Integer (0–23) | Hour of the day when the decision is made                                    |
| `day_of_week`              | Integer (0–6)  | Day of the week (0 = Monday, 6 = Sunday)                                     |
| `is_weekend`               | Integer (0/1)  | Indicates whether the day is a weekend                                       |
| `event_type`               | Categorical    | Type of upcoming event (Breakfast, Lunch, Dinner, Gym, Meeting, Study, None) |
| `event_priority`           | Categorical    | Importance of the event (Low, Medium, High)                                  |
| `minutes_to_event`         | Integer        | Time remaining (in minutes) before the event starts                          |
| `user_location`            | Categorical    | User’s current location (Home, Office, Outside)                              |
| `screen_state`             | Categorical    | Phone screen state at decision time (Active, Inactive)                       |
| `device_silent_mode`       | Integer (0/1)  | Whether device is in silent / DND mode                                       |
| `time_since_last_reminder` | Integer        | Minutes elapsed since the previous reminder                                  |
| `last_response`            | Categorical    | User’s previous reminder response (Accepted, Snoozed, Ignored)               |
| `should_remind_now`        | Integer (0/1)  | **Target variable** indicating whether to trigger a reminder                 |
