# 🎵 Gaana Music Analysis

A Python-based Exploratory Data Analysis (EDA) project on songs scraped from the Gaana music streaming platform. This project focuses on data cleaning, preprocessing, feature engineering, and extracting insights from a large multi-language music dataset using Python.


## 📌 Project Overview

This project analyzes Gaana music data to understand:

- Song frequency trends
- Singer popularity
- Language-wise song distribution
- Average song duration patterns
- Duplicate and inconsistent data handling

The project follows a complete EDA workflow including:

- Data Cleaning
- Feature Engineering
- Exploratory Data Analysis
- Aggregation & GroupBy Operations
- Data Visualization


## 📂 Project Files

- `Gaana_Data_Analysis.ipynb` → Complete Python analysis notebook
- `songs.csv` → Raw dataset
- `Gaana_Data_Analysis_Documentation.docx` → Project documentation
- `Gaana_Data_Analysis_Presentation.pptx` → Presentation slides


## 🛠️ Tools & Technologies Used

<p align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="55"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pandas/pandas-original.svg" width="55"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/84/Matplotlib_icon.svg" width="55"/>
  <img src="https://seaborn.pydata.org/_images/logo-mark-lightbg.svg" width="55"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/d/d0/Google_Colaboratory_SVG_Logo.svg" width="55"/>
</p>

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Google Colab**


## 📊 Dataset Overview

| Metric | Value |
|---|---|
| Rows Before Cleaning | 41,355 |
| Rows After Cleaning | 32,499 |
| Total Columns | 7 |
| Languages Available | 16 |
| Dataset Type | Multi-language Music Dataset |

### Dataset Columns

| Column | Description |
|---|---|
| `name` | Song title |
| `singer` | Singer name(s) |
| `singer_id` | Unique singer IDs |
| `language` | Song language |
| `link` | Unique Gaana song URL |
| `duration` | Original duration column |
| `Duration_in_sec` | Engineered duration in seconds |


## 🧹 Data Cleaning & Preprocessing

The dataset contained several inconsistencies and duplicate records which were handled during preprocessing.

### ✔ Link-Based Duplicate Removal

Duplicate songs were removed using the `link` column because songs categorized under `"Old"` and `"Hindi"` shared identical URLs.

```python
df.drop_duplicates(subset=['link'], inplace=True)
```


### ✔ Singer Name Standardization

A spelling inconsistency was corrected:

```python
S P Balasubrahamanyam
→
S. P. Balasubrahmanyam
```

This fixed mismatch issues between `singer` and `singer_id`.


### ✔ Multi-Column Duplicate Removal

Additional duplicate records were removed using:

```python
['name', 'singer', 'singer_id']
```

This ensured repeated songs across albums/playlists were removed.


## ⚙️ Feature Engineering

The `duration` column contained mixed formats:

- `MM:SS`
- `H:MM:SS`

A custom loop using `if-elif` conditions was implemented to convert durations into total seconds.

### Example

| Original Duration | Converted |
|---|---|
| `04:55` | `295 sec` |
| `1:02:34` | `3754 sec` |

A new column was created:

```python
Duration_in_sec
```


## 📈 Exploratory Data Analysis (EDA)

The notebook includes:

- `info()` and `describe()` analysis
- Null value checking
- Duplicate detection
- Language distribution analysis
- Singer frequency analysis
- Duration analysis
- GroupBy aggregations
- Value count analysis


## 📊 Visualizations Used

The project includes visualizations created using **Matplotlib** and **Seaborn**:

- Horizontal bar charts
- Vertical bar charts

These visualizations were used for:

- Top occurring songs
- Most popular singers
- Language-wise song counts
- Average duration by language


# 🎯 Key Insights & KPI Analysis

## 🎵 Most Occurring Songs

| Song | Count |
|---|---|
| Ahe Ramahari | 8 |
| Padhyams | 8 |
| Music | 7 |
| Duha | 7 |
| Boliyan | 7 |


## 🎤 Most Popular Singers

Collaborative singer entries separated using `"|"` were split before analysis.

| Singer | Song Count |
|---|---|
| S. P. Balasubrahmanyam | 3015 |
| P. Susheela | 2872 |
| S. Janaki | 1811 |
| Asha Bhosle | 1693 |
| Lata Mangeshkar | 1385 |


## 🌐 Languages with Highest Number of Songs

| Language | Song Count |
|---|---|
| Telugu | 4581 |
| Marathi | 4228 |
| Tamil | 4140 |
| Hindi | 3918 |
| Punjabi | 3543 |


## ⏱️ Total Listening Duration

Total cumulative duration of all songs:

- **10,160,548 seconds**

Equivalent to approximately:

- **117 days of continuous music playback**


## 📏 Highest Average Song Duration by Language

| Language | Average Duration (sec) |
|---|---|
| Urdu | 410.79 |
| Punjabi | 410.03 |
| Bhojpuri | 367.18 |
| Haryanvi | 316.39 |
| Telugu | 315.16 |


## 💡 Key Findings

- Telugu songs had the highest representation in the cleaned dataset
- Duplicate `"Old"` songs were actually repeated Hindi records
- Singer collaborations required custom splitting logic using `"|"`
- S. P. Balasubrahmanyam appeared in over 3000 songs
- The dataset contains over 117 days of cumulative music duration


## 🎯 Conclusion

This project demonstrates a complete real-world Exploratory Data Analysis workflow using Python. The analysis includes data cleaning, preprocessing, feature engineering, aggregation analysis, and visualization to extract meaningful insights from large-scale music streaming data.
