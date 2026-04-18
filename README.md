# 📊 Student Satisfaction Survey — Exploratory Data Analysis

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/Plotly-Interactive%20Viz-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" />
  <img src="https://img.shields.io/badge/Seaborn-Statistical%20Plots-4C72B0?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  A rigorous exploratory data analysis of an institutional student satisfaction survey, examining teaching quality, mentoring effectiveness, curriculum delivery, and overall learning experience across <strong>13 academic departments</strong> and <strong>20 structured questions</strong>.
</p>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Business Problem](#-business-problem)
- [Project Workflow](#-project-workflow)
- [Dataset Description](#-dataset-description)
- [Survey Structure](#-survey-structure)
- [Analysis Breakdown](#-analysis-breakdown)
- [Key Findings & Insights](#-key-findings--insights)
- [Technologies Used](#-technologies-used)
- [Getting Started](#-getting-started)
- [Recommendations](#-recommendations)
- [Future Work](#-future-work)
- [Contact](#-contact)

🔗 Live Report: https://tamurone10.github.io/Students-Satisfaction-Survey-Analysis/
---

## 🔍 Overview

This project conducts a comprehensive **Exploratory Data Analysis (EDA)** on an academic institution's student satisfaction survey dataset. The survey captures student perceptions across 20 structured questions, covering dimensions such as:

- Teaching quality and preparation
- Mentorship and academic support
- Institutional initiatives and student engagement
- Curriculum coverage and learning outcomes
- ICT adoption in classrooms

The analysis surfaces actionable insights to help academic administrators, faculty, and policy-makers improve educational delivery across programs.

---

## 💼 Business Problem

> *"Which departments are underperforming in student satisfaction, and what specific teaching or institutional factors are driving dissatisfaction?"*

Academic institutions invest heavily in faculty and infrastructure, yet student satisfaction often remains unmeasured at a granular level. This analysis answers:

- Which courses score consistently high or low across the 20 survey dimensions?
- Are there structural patterns (e.g., MSc programs vs. Bachelor programs) in satisfaction scores?
- Which specific teaching behaviours — preparation, communication, feedback — need institutional attention?
- Where should leadership prioritise intervention for maximum impact?

---

## 🔄 Project Workflow

```
Raw CSV Data (Student_Satisfaction_Survey.csv)
         │
         ▼
  ┌─────────────────────────────────┐
  │   1. Data Loading & Inspection  │  → df.head(), df.info(), df.tail()
  └─────────────────────────────────┘
         │
         ▼
  ┌─────────────────────────────────┐
  │   2. Data Quality Assessment    │  → Null check, duplicate detection,
  │                                 │    unique value validation, type audit
  └─────────────────────────────────┘
         │
         ▼
  ┌─────────────────────────────────┐
  │   3. Statistical Summary        │  → df.describe(), nunique(), value counts
  └─────────────────────────────────┘
         │
         ▼
  ┌─────────────────────────────────┐
  │   4. Aggregated EDA             │  → Dept-level feedback averages,
  │                                 │    course distribution, rating summaries
  └─────────────────────────────────┘
         │
         ▼
  ┌─────────────────────────────────┐
  │   5. Question-by-Question EDA   │  → Per-question groupby analysis
  │      (Q1 – Q20)                 │    across all 13 departments
  └─────────────────────────────────┘
         │
         ▼
  ┌─────────────────────────────────┐
  │   6. Visualisation              │  → Violin plots, bar charts,
  │                                 │    pie charts, histograms
  └─────────────────────────────────┘
         │
         ▼
  ┌─────────────────────────────────┐
  │   7. Observations & Insights    │  → Per-question textual analysis
  │                                 │    with course-level breakdowns
  └─────────────────────────────────┘
```

---

## 📊 Dataset Description

| Attribute | Details |
|-----------|---------|
| **File** | `Student_Satisfaction_Survey.csv` |
| **Encoding** | `latin-1` |
| **Null Values** | None ✅ |
| **Duplicates** | None ✅ |
| **Survey Questions** | 20 |
| **Departments Covered** | 13 |

### Column Reference

| Column | Description |
|--------|-------------|
| `Questions` | One of 20 survey questions asked to students |
| `Basic Course` | Academic department / program (e.g., BMS, MSc IT, BA) |
| `Total Configured` | Total students configured to give feedback |
| `Total Feedback Given` | Actual number of students who submitted feedback |
| `Average/ Percentage` | Mean satisfaction score for the question per department |

### Departments in the Dataset

| # | Department |
|---|-----------|
| 1 | Bachelor of Arts (BA) |
| 2 | Bachelor of Commerce (B.Com) |
| 3 | Bachelor of Commerce – Accounting & Finance (BAF) |
| 4 | Bachelor of Commerce – Banking & Insurance (BBI) |
| 5 | Bachelor of Management Studies (BMS) |
| 6 | B.Sc. Computer Science |
| 7 | B.Voc Food Technology |
| 8 | MA Psychology |
| 9 | MSc Analytical Chemistry |
| 10 | MSc Data Science |
| 11 | MSc Information Technology |
| 12 | MSc Physics |

---

## 📋 Survey Structure

The 20 survey questions are grouped across the following thematic dimensions:

| Theme | Questions |
|-------|-----------|
| **Curriculum & Syllabus** | Q1 – Syllabus coverage |
| **Teaching Quality** | Q2 – Teacher preparation, Q3 – Communication, Q4 – Teaching approach, Q12 – Use of examples |
| **Evaluation & Feedback** | Q5 – Fairness of evaluation, Q6 – Assignment discussion |
| **Mentorship** | Q11 – Mentor follow-up, Q13 – Identifying strengths, Q14 – Addressing weaknesses |
| **Institutional Initiatives** | Q7 – Internships & field visits, Q9 – Learning opportunities, Q15 – Quality improvement engagement |
| **Student Development** | Q8 – Cognitive/social/emotional growth, Q17 – Extracurricular encouragement, Q18 – Soft skills & employability |
| **Learning Outcomes** | Q10 – Communication of course outcomes, Q16 – Student-centric methods |
| **Technology in Teaching** | Q19 – ICT tool usage |
| **Overall Quality** | Q20 – Overall teaching-learning quality |

---

## 🔬 Analysis Breakdown

### Aggregated Analysis
- **Average feedback given per department** — violin plot showing distribution spread
- **Batch strength by course** — pie chart of student population distribution
- **Average rating per department across all 20 questions** — bar chart with department comparison

### Per-Question Drill-Down (Q1 – Q20)
Each question is analysed using:
```python
question_df = df[df['Questions'] == '<question text>']
avg = question_df.groupby('Basic Course')['Average/ Percentage'].mean()
avg.agg(['min', 'max'])
```
Followed by a **histogram of score distribution** and **written observations** identifying high-performing and low-performing departments for each dimension.

---

## 💡 Key Findings & Insights

### 🏆 Consistently High-Performing Departments

| Department | Notable Strengths |
|-----------|------------------|
| **Bachelor of Arts (BA)** | Top ratings in mentor follow-up (4.50), teaching approach, fairness of evaluation (4.77), cognitive/emotional growth (4.68), and weakness identification (4.53) |
| **MSc Information Technology** | Highest overall average (4.35); leads in learning opportunities (4.59), employability development (4.75), and course outcome communication (4.75) |
| **B.Com – Banking & Insurance** | Consistent top-3 finisher in syllabus coverage (4.70), internship promotion (4.50), extracurricular encouragement (4.30), and student engagement |
| **MSc Analytical Chemistry** | Strong performance in student-centric methods (4.40) and mentor follow-up (4.36) |

### ⚠️ Departments Requiring Intervention

| Department | Primary Area of Concern | Score Range |
|-----------|------------------------|-------------|
| **MSc Data Science** | Lowest overall average (3.05); critical gaps in communication (3.17), use of examples (2.67), strength identification (1.67), and growth facilitation (2.33) | 1.67 – 3.67 |
| **MSc Physics** | Mentor follow-up (2.50), student-centric methods (2.50), internship initiative (2.50) | 2.50 – 4.00 |
| **B.Voc Food Technology** | Cognitive growth facilitation (2.00), employability skills (2.00), teaching-learning engagement (3.00) | 2.00 – 5.00 |
| **MA Psychology** | ICT tool usage (2.79), weakness identification (2.92) | 2.79 – 4.30 |
| **B.Sc. Computer Science** | Extracurricular encouragement (3.15), evaluation fairness (3.41) | 3.00 – 4.30 |

### 📈 Score Range Summary

| Metric | Value |
|--------|-------|
| **Highest** single-question score | 5.00 — B.Voc Food Technology (Teacher Preparation & Communication) |
| **Lowest** single-question score | 1.665 — MSc Data Science (Identifying student strengths) |
| **Widest variance** question | Q13 – Identifying student strengths (range: 1.665 → 4.470) |
| **Most consistent** top performer | Bachelor of Arts |
| **Most consistent** low performer | MSc Data Science |

### 🔎 Notable Patterns

- **MSc Data Science** is an outlier in nearly every dimension — despite being a technically advanced and high-demand program, student satisfaction is the lowest across the institution, warranting urgent curriculum and faculty review
- **Bachelor of Arts** outperforms most STEM programs on qualitative teaching dimensions (mentoring, communication, approach), suggesting soft pedagogical skills may be more embedded in humanities faculty culture
- **B.Voc Food Technology** presents a paradox: top scores in teacher preparedness (5.00) and ICT usage, but bottom scores in growth facilitation (2.00) and employability skill development (2.00) — strong content delivery but weak holistic student development
- **Feedback participation rates** vary significantly across departments; Master's program cohorts are smaller, making their scores less statistically robust than Bachelor's programs

---

## 🛠️ Technologies Used

| Category | Library / Tool | Purpose |
|----------|---------------|---------|
| Data Manipulation | `pandas`, `numpy` | Data loading, groupby aggregations, type handling |
| Static Visualisation | `matplotlib`, `seaborn` | Histograms, bar charts, pie charts |
| Interactive Visualisation | `plotly.express` | Violin plots, interactive department charts |
| Warning Suppression | `warnings` | Clean notebook output |
| Environment | `Jupyter Notebook` | Iterative analysis and documentation |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab

### Installation

```bash
# Clone the repository
git clone https://github.com/TamurOne10/Students-Satisfaction-Survey-EDA.git

# Navigate to the project directory
cd Students-Satisfaction-Survey-EDA

# Install required dependencies
pip install pandas numpy matplotlib seaborn plotly
```

### Running the Notebook

```bash
# Launch Jupyter Notebook
jupyter notebook Students-Satisfaction-Survey.ipynb
```

> **Note:** Ensure `Student_Satisfaction_Survey.csv` is in the same directory as the notebook. The file uses `latin-1` encoding — preserve this if you re-export the CSV.

---

## ✅ Recommendations

Based on the EDA findings, the following actions are recommended for institutional leadership:

**1. 🚨 Targeted Faculty Development for MSc Data Science**
Implement immediate pedagogical support — coaching in communication, concept illustration, and student engagement techniques. Consider peer observation programmes pairing MSc Data Science faculty with high-performing colleagues from BA or MSc IT.

**2. 📚 Replicate BA & BBI Best Practices Institutionally**
Conduct structured knowledge-transfer workshops where faculty from Bachelor of Arts and B.Com (Banking & Insurance) share mentoring frameworks and teaching approaches with underperforming departments.

**3. 🧑‍🏫 Address MSc Physics Mentorship Gap**
The consistently low mentor follow-up score (2.50) suggests structural mentoring is absent. Introduce formal mentoring frameworks with scheduled task check-ins, progress tracking, and accountability mechanisms.

**4. 🌱 Holistic Development Review for B.Voc Food Technology**
Strong content delivery does not translate to career readiness. Integrate structured soft skills modules, employability workshops, industry exposure, and growth-oriented activities into the program curriculum.

**5. 💻 Standardise ICT Usage Across All Programs**
Departments like MA Psychology (2.79) and B.Com (2.98) lag in ICT adoption. Mandate basic ICT training for faculty and ensure infrastructure (projectors, multimedia tools) is available and utilised in all classrooms.

**6. 📊 Improve Survey Participation for Master's Programs**
Smaller cohort sizes reduce statistical reliability for Master's program insights. Implement structured, incentivised feedback collection to ensure representative data in future survey cycles.

---

## 🔮 Future Work

- [ ] Conduct **statistical significance testing** (ANOVA / t-tests) to validate observed differences between departments
- [ ] Build an **interactive institutional dashboard** using Streamlit or Power BI for administrative stakeholders
- [ ] Perform **year-over-year trend analysis** if historical survey data across multiple academic years is available
- [ ] Apply **clustering** (K-Means / Hierarchical) to group departments by overall satisfaction profile
- [ ] Incorporate **open-ended feedback responses** via NLP sentiment analysis
- [ ] Expand analysis to **faculty-level granularity** if individual instructor data becomes available
- [ ] Create **automated per-department scorecards** for distribution to department heads each semester

---

## 🤝 Contributing

Contributions and suggestions are welcome! To contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add: description of change'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — free to use, modify, and distribute with attribution.

---

## 📬 Contact

**Tamoor Abbas**

[![Email](https://img.shields.io/badge/Email-Tamur110%40gmail.com-red?style=flat-square&logo=gmail)](mailto:Tamur110@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Tamoor%20Abbas-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/tamoor-abbas)
[![GitHub](https://img.shields.io/badge/GitHub-TamurOne10-black?style=flat-square&logo=github)](https://github.com/TamurOne10)

---

<p align="center">
  ⭐ If this project added value to your work, please consider giving it a star!
</p>
