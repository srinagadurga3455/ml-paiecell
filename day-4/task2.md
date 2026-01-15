
---

### ✅ Task 2: Clean the Dataset

```md
### Task 2: Clean the Dataset

- Checked the dataset for missing values using `isnull()`.
- Verified that no missing values were present in the dataset.
- Checked for duplicate rows using `duplicated()`.
- Removed duplicates (if any) to ensure data quality.

**Code used:**
```python
df.isnull().sum()
df.duplicated().sum()
df = df.drop_duplicates()
