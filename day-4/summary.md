# Day 4 – Pandas Essentials for Machine Learning

## 1. Overview: What Day 4 Is About

Day 4 focuses on **understanding, inspecting, and cleaning data** before it is used for Machine Learning.

Up to this point:
- **Day 2** → Defined what data is and designed the dataset
- **Day 3** → Learned NumPy and how machines work with numerical arrays

**Day 4 connects humans to machines.**

Pandas is used to:
- Read datasets
- Inspect data quality
- Clean data
- Prepare features and target variables

Only **clean and reliable data** should be given to ML models.

---

## 2. Why Pandas Is Needed in Machine Learning

Machine Learning models:
- Do not understand column names
- Do not handle missing values automatically
- Do not detect duplicates
- Only work with numerical arrays

Pandas helps **humans**:
- See and understand the dataset
- Fix data issues
- Organize data logically

**Rule:**  
> Pandas is for understanding and cleaning data.  
> NumPy is for feeding data to ML models.

---

## 3. Pandas Data Structures

### 3.1 Series
A **Series** is a one-dimensional labeled array (single column).

Example:
```python
df["hour"]

### 3.2 DataFrame

A DataFrame is a two-dimensional table consisting of rows and columns.

Example:
df

Most datasets used in Machine Learning are DataFrames.