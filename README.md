This repository documents my learning journey in Machine Learning, guided by a senior mentor. The focus of this project is to understand ML fundamentals by applying them to a real-world problem in a structured, step-by-step manner.
# Smart Reminder – Machine Learning Mini Project

## 📌 Project Overview
This project builds a Machine Learning model that predicts whether a reminder should be triggered at a given moment based on user context, time, event urgency, device state, and historical behavior.

The goal is to simulate how real-world notification systems make intelligent, non-intrusive decisions.

---

## 🎯 Problem Statement
Given a user's current context and past behavior, predict:

**Should a reminder be sent now?**

This is modeled as a **binary classification problem**.

---

## 🧠 Features Used

### Temporal Context
- hour_of_day
- day_of_week
- is_weekend

### Event Context
- event_type
- event_priority
- minutes_to_event

### User & Device Context
- user_location
- screen_state
- device_silent_mode

### Behavioral History
- time_since_last_reminder
- last_response

### Target Variable
- should_remind_now (0 = No, 1 = Yes)

---

## 🗂️ Dataset
- Total rows: **429**
- Training set: **343**
- Test set: **86**
- Categorical features encoded using One-Hot Encoding
- Missing values and duplicates handled during preprocessing

---

## 🤖 Models Used

### 1. Linear Regression (Baseline)
- Used to understand the ML workflow
- Highlighted limitations for binary decision problems

### 2. Logistic Regression (Final Model)
- Designed for binary classification
- Outputs probabilities
- Evaluated using classification metrics

---

## 📊 Evaluation Metrics
- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1 Score

These metrics were used to understand not just correctness, but real-world impact such as missed reminders and unnecessary notifications.

---

## 🧠 Key Learnings
- Proper data splitting prevents overfitting
- Feature engineering is as important as model choice
- Accuracy alone is misleading for imbalanced datasets
- Logistic Regression is more suitable than Linear Regression for binary decisions

---

## 🛠️ Tools & Libraries
- Python
- Pandas
- NumPy
- Matplotlib
- scikit-learn

---

## 🚀 Future Improvements
- Threshold tuning
- Feature importance analysis
- Model deployment using FastAPI
- Real-time inference pipeline

---

## 📎 Links
- Google Colab: https://colab.research.google.com/drive/1aNTXygvL-XH5YOsjAyOKVBXmL79Ipsni#scrollTo=fhgk-f9rqIj9
- GitHub Repository: https://github.com/srinagadurga3455/ml-paiecell
