1. What is Data and Dataset

Data
Data refers to raw facts collected from user activity, time, and interactions. Individually, these values have little meaning, but together they help identify patterns.

Examples (from reminder system):

Time: 09:00

Day: Monday

Event type: Gym

User response: Dismissed

Dataset
A dataset is an organized collection of data arranged in rows and columns, where:

Each row represents a past situation where a reminder could have been triggered.

Each column represents a feature or the target variable.

2. Features and Target Variable
Features (Independent Variables – X)

Features are the input variables used by the model to make predictions.

For the reminder prediction system, selected features are:

hour – Hour of the day

day_of_week – Day index (0–6)

is_weekend – Whether the day is a weekend (0/1)

event_type – Type of scheduled activity (Gym, Meeting, Study, None)

minutes_to_event – Time remaining before the event starts

last_response – User’s previous reaction to reminders

reminders_today – Number of reminders already sent that day

Target Variable (Dependent Variable – y)

The target variable is what the model is trained to predict.

should_remind_now

1 → Trigger reminder

0 → Do not trigger reminder

This makes the problem a binary classification task.

3. Types of Datasets
Structured Dataset

Data organized in tabular form (rows and columns)

Easy to store, process, and model

Used in this project

Example: CSV file with numerical and categorical columns.

Unstructured Dataset

Data without a fixed structure (text, audio, images)

Example: calendar event descriptions or notification text

Not used in the initial phase of this project

4. Common Dataset Formats

The dataset is stored in CSV (Comma-Separated Values) format because:

It is simple and lightweight

Easily readable by humans

Directly supported by Pandas and ML libraries

File example:
synthetic_reminder_data.csv