data_cleaning_complete_guide:
  purpose: >
    This document describes all essential data cleaning steps used in
    machine learning projects. It explains what each step does, why it
    exists, how Pandas behaves internally, and how decisions should be made.
    This guide focuses on correctness, not preprocessing or modeling.

  core_principle:
    - Cleaning makes data correct and reliable
    - Preprocessing makes data usable for ML models
    - Cleaning always comes before preprocessing
    - Never delete data without inspecting it first

  dataset_assumption:
    - Data is loaded as a Pandas DataFrame
    - Each row represents one observation or decision moment
    - Columns represent features or the target variable

  missing_values:
    description: >
      Missing values (NaN) indicate absent data in individual cells.
      Pandas stores missing values at the cell level, but many operations
      act on entire rows.

    detection:
      check_per_column:
        explanation: >
          Counts how many missing values exist in each column.
          This is always the FIRST step.
        code: df.isnull().sum()

      check_rows_with_any_nan:
        explanation: >
          Displays rows that contain at least one NaN in any column.
        code: df[df.isnull().any(axis=1)]

      check_rows_for_specific_column:
        explanation: >
          Displays rows where a specific column contains NaN.
        code_example: df[df["column_name"].isnull()]

    dropna_behavior:
      rule: >
        dropna() removes the ENTIRE ROW if ANY column in that row contains NaN.
        It does not require the full row to be empty.

      consequences:
        - single NaN in one column deletes the whole row
        - safe only when missing rows are very few

      code:
        basic: df.dropna()

    when_to_drop_rows:
      safe_conditions:
        - missing values are very rare
        - dataset is large
        - missing values appear random
      risk:
        - significant data loss if many rows contain NaN

    filling_missing_values:
      numerical_columns:
        strategies:
          mean:
            when: data is normally distributed
            code_example: df["num_col"].fillna(df["num_col"].mean(), inplace=True)
          median:
            when: data contains outliers
            code_example: df["num_col"].fillna(df["num_col"].median(), inplace=True)

      categorical_columns:
        strategy: mode
        code_example: df["cat_col"].fillna(df["cat_col"].mode()[0], inplace=True)

      guiding_rule: >
        Prefer filling values when dropping rows would remove useful information.

  duplicates:
    description: >
      Duplicate data refers to repeated observations. Pandas primarily
      identifies duplicates at the FULL ROW level.

    full_row_duplicates:
      definition: >
        Two rows are duplicates only if ALL column values match exactly.

      detection:
        code: df.duplicated().sum()

      removal:
        code: df.drop_duplicates()

      example_logic:
        identical_rows:
          result: duplicate
        same_hour_different_event:
          result: not_duplicate

    column_level_duplicates:
      explanation: >
        Repeated values in a single column do NOT mean duplicate rows.
        This is normal behavior in most datasets.

      examples_of_normal_repetition:
        - same hour across different days
        - same event type multiple times
        - same location repeated

      warning:
        - do NOT remove rows just because one column repeats

    subset_based_duplicates:
      purpose: >
        Used only when a column is expected to be UNIQUE (ID-like columns).

      examples_of_id_columns:
        - user_id
        - transaction_id
        - order_id
        - email

      detection:
        code_example: df["id_column"].duplicated().sum()

      removal:
        code_example: df.drop_duplicates(subset=["id_column"])

      rule: >
        Using subset means duplication is judged ONLY by that column,
        regardless of other column values.

  data_types:
    description: >
      Ensures each column has the correct data type for its meaning.

    detection:
      code: df.dtypes

    common_issues:
      - numbers stored as strings
      - dates stored as text

    fixes:
      numeric_conversion:
        code_example: df["col"].astype(int)
      datetime_conversion:
        code_example: pd.to_datetime(df["date_col"])

  invalid_values:
    description: >
      Invalid values are logically impossible or out-of-range values.

    examples:
      - hour < 0 or hour > 23
      - negative time durations
      - invalid binary flags

    detection:
      code_example: df[(df["hour"] < 0) | (df["hour"] > 23)]

    actions:
      - remove invalid rows
      - replace with valid defaults
      - investigate data source

  categorical_consistency:
    description: >
      Ensures categorical values are consistent in formatting.

    common_problems:
      - inconsistent casing (Home vs home)
      - extra whitespace

    fixes:
      lowercase:
        code_example: df["col"].str.lower()
      strip_whitespace:
        code_example: df["col"].str.strip()

  outliers:
    description: >
      Outliers are extreme values that may distort learning.

    detection:
      basic:
        code: df.describe()

    handling_strategies:
      - keep if realistic
      - cap values
      - remove rows cautiously

    warning: >
      Not all outliers are errors. Do not remove without reasoning.

  irrelevant_columns:
    description: >
      Columns that do not help prediction should be removed.

    detection:
      criteria:
        - no predictive value
        - constant values
        - identifiers not needed for ML

    removal:
      code_example: df.drop(columns=["irrelevant_col"])

  target_variable_check:
    description: >
      Ensures the target variable is valid and usable.

    checks:
      class_distribution:
        code: df["target_col"].value_counts()

    expectations:
      - no missing target values
      - only valid class labels
      - reasonable balance

  final_sanity_checks:
    description: >
      These checks must pass before moving to preprocessing.

    required:
      - df.info()
      - df.isnull().sum()
      - df.duplicated().sum()
      - df.describe()
dropna() without subset drops rows with NaN anywhere;
dropna(subset=[...]) drops rows only when specific columns are NaN.

  boundaries:
    what_cleaning_does_not_include:
      - encoding categorical variables
      - scaling or normalization
      - train-test split
      - feature engineering

  final_takeaways:
    - inspect before deleting
    - dropna removes rows with ANY NaN
    - duplicated checks FULL rows by default
    - subset defines what "duplicate" means
    - repeated column values are usually normal
    - stop cleaning once data is correct
