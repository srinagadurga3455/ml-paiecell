detailed_revision_classification_metrics:

  context:
    topic: Accuracy, Precision, Recall
    model_type: Binary Classification
    example_project: Smart Reminder / Intent Prediction System
    target_variable: should_remind_now

    why_these_metrics_exist: >
      In binary classification problems, overall correctness alone
      is not enough. Different types of mistakes have different
      real-world consequences. Accuracy, Precision, and Recall
      measure different aspects of model behavior.

  confusion_matrix:
    definition: >
      A confusion matrix is a table that compares actual class labels
      with predicted class labels to show how a classification model
      is making decisions.

    structure:
      format: "[[TN, FP], [FN, TP]]"

    meaning_of_terms:
      TN:
        name: True Negative
        meaning: >
          The model correctly predicted the negative class.
        reminder_example: >
          The system correctly did NOT send a reminder when no reminder
          was needed.

      FP:
        name: False Positive
        meaning: >
          The model predicted positive when the actual class was negative.
        reminder_example: >
          The system sent an unnecessary reminder, potentially annoying
          the user.

      FN:
        name: False Negative
        meaning: >
          The model predicted negative when the actual class was positive.
        reminder_example: >
          The system failed to send a reminder when it was actually needed.
          This is often the most serious error.

      TP:
        name: True Positive
        meaning: >
          The model correctly predicted the positive class.
        reminder_example: >
          The system sent a reminder exactly when it should have.

  accuracy:
    definition: >
      Accuracy measures how often the model makes the correct prediction
      overall, considering both positive and negative classes.

    question_it_answers: >
      Out of all predictions made by the model, how many were correct?

    formula: "(TP + TN) / (TP + TN + FP + FN)"

    how_to_interpret:
      high_accuracy: >
        The model is generally correct most of the time.
      low_accuracy: >
        The model is making many incorrect predictions.

    major_limitation: >
      Accuracy can be misleading when the dataset is imbalanced.
      A model can achieve high accuracy by always predicting
      the majority class and still fail at the actual task.

    reminder_system_example: >
      If most situations do not require reminders, a model that
      never sends reminders can still have high accuracy while
      being completely useless.

  precision:
    definition: >
      Precision measures how trustworthy the model's positive predictions are.

    question_it_answers: >
      When the model says "send a reminder", how often is it correct?

    formula: "TP / (TP + FP)"

    how_to_interpret:
      high_precision: >
        The model sends reminders only when it is very confident,
        resulting in fewer unnecessary notifications.
      low_precision: >
        The model sends many reminders that are not actually needed.

    real_world_meaning: >
      Precision reflects how annoying or spammy the system feels to users.

    reminder_system_example: >
      High precision means users rarely receive reminders they
      did not actually need.

  recall:
    definition: >
      Recall measures how well the model captures all actual positive cases.

    question_it_answers: >
      Out of all situations where a reminder was truly needed,
      how many did the model successfully catch?

    formula: "TP / (TP + FN)"

    how_to_interpret:
      high_recall: >
        The model misses very few important reminders.
      low_recall: >
        The model frequently fails to send reminders when it should.

    real_world_meaning: >
      Recall reflects reliability and user trust in the system.

    reminder_system_example: >
      High recall ensures that important meetings, tasks, or events
      are rarely missed.

  accuracy_vs_precision_vs_recall:
    core_difference:
      accuracy: Overall correctness
      precision: Quality of positive predictions
      recall: Completeness of positive predictions

    why_accuracy_alone_is_dangerous: >
      Accuracy does not distinguish between types of errors.
      It treats missed reminders and unnecessary reminders
      as equally bad, which is unrealistic.

  practical_priority_for_reminder_system:
    false_positive_cost: >
      Unnecessary reminders cause annoyance but are usually tolerable.
    false_negative_cost: >
      Missing an important reminder can break user trust
      and reduce system usefulness.

    preferred_focus: >
      Recall is often slightly more important than precision,
      while maintaining a reasonable balance.

  final_intuition_summary:
    plain_language_explanation:
      accuracy: "Am I usually right?"
      precision: "Am I being annoying?"
      recall: "Am I missing important things?"

    key_learning: >
      A good classification model is not defined by high accuracy alone.
      Precision and recall must be analyzed to understand real-world impact.

  exam_ready_one_liner: >
    Accuracy measures overall correctness, precision measures how reliable
    positive predictions are, and recall measures how well the model
    captures all actual positive cases.
