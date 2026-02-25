# Investigating Students' Self-Directed Learning on Learnbar During Summer Vacation

## Project Overview

This project analyzes how students in Yilan, Taiwan engaged in self-directed learning on the **Learnbar (學習吧)** platform during the summer vacation of July 2024. The dataset was sourced from the **Yilan Distance Learning Center** and explored through a series of data mining techniques to uncover learning behavior patterns.

---

## Data Source

- **Platform:** Learnbar (學習吧)
- **Provider:** Yilan Distance Learning Center (宜蘭網教中心)
- **Period:** July 2024
- **Format:** Google Sheets (imported via Google Sheets API)

---

## Environment & Dependencies

This notebook is designed to run on **Google Colab**.

### Required Libraries

```
pandas
matplotlib
seaborn
scipy
scikit-learn
gspread
google-auth
```

> **Note:** Chinese font rendering in Matplotlib requires downloading `TaipeiSansTCBeta-Regular.ttf`, which is handled automatically in the notebook.

---

## Project Structure

```
DataMining_FinalProject.ipynb   # Main analysis notebook
README.md                       # Project documentation
```

---

## Analysis Questions

### Question 1 — Correlation Between Online Time and Total Learning Time
- Computed total learning time by summing all activity columns.
- Removed outliers (students with abnormally high online time but minimal learning activity).
- Calculated **Pearson correlation coefficient = 0.42**, indicating a **moderate positive correlation**.
- **Finding:** Online time reflects attendance but does not fully represent learning engagement.

### Question 2 — Time Distribution Across Learning Activities
- Visualized total time spent on each activity (videos, quizzes, voice assignments, audio files, books, in-class materials).
- **Finding:** Video browsing dominates, followed by voice assignments and book browsing. Audio files and in-class materials are underutilized.

### Question 3 — Correlations Among Different Learning Activities
- Generated a correlation heatmap across all activity types.
- **Key findings:**
  - Quiz Time vs. Video Time: r = 0.23 (weak positive)
  - Book Browsing vs. Voice Assignment: r = 0.13 (very weak positive)
  - Video Time vs. Voice Assignment: r = -0.12 (very weak negative)
- **Finding:** Low cross-activity correlation suggests personalized and fragmented learning behavior; guided task structures may be needed.

### Question 4 — Learning Activity Distribution by Subject
- Categorized courses into subjects (Chinese, English, Science, Social Studies, etc.).
- Compared average tool usage time per subject.
- **Key findings:**
  - Science: highest video browsing time
  - Chinese: highest voice assignment time
  - Social Studies: overall low tool usage

---

## Clustering Analysis (Bonus)

- Used **K-Means clustering** (k=3, selected via Elbow Method) on standardized learning activity features.
- Applied **PCA** (2 components) for visualization.
- Result: Students were grouped into 3 distinct behavioral clusters reflecting different learning styles and engagement levels.

---

## Key Takeaways

- Students primarily rely on video content for self-directed learning.
- Different subjects have distinct learning tool preferences aligned with their pedagogical nature.
- Low inter-activity correlations suggest students do not naturally transition between activity types — platforms should consider designing structured learning pathways to encourage more balanced engagement.
