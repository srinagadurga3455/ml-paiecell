 ### Task 1: Load Dataset Using Pandas

- Loaded the dataset `synthetic_smart_reminder_data.csv` using Pandas.
- Verified successful loading by viewing the first and last few rows.
- Checked the dataset shape to confirm the expected number of rows and columns.

**Code used:**
```python
import pandas as pd

df = pd.read_csv("synthetic_smart_reminder_data.csv")
df.head()
df.shape
