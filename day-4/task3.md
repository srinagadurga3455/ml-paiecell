
---

### ✅ Task 3: Create Feature and Target DataFrames

```md
### Task 3: Create Feature and Target DataFrames

- Identified `should_remind_now` as the target variable.
- Separated input features and target into separate DataFrames.
- Verified the shape of feature and target data.

**Code used:**
```python
target = "should_remind_now"

X_df = df.drop(columns=[target])
y_df = df[target]

X_df.shape
y_df.shape
