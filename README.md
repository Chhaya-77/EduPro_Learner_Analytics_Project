# EduPro Learner Demographics & Course Enrollment Analysis

Comprehensive exploratory data analysis, descriptive learner intelligence, and interactive Streamlit analytics application prepared for **EduPro** and **Unified Mentor**.

---

## 📁 Project Structure

- `app.py`: Interactive Streamlit dashboard with automated dataset loading, KPI scorecards, demographic analyses, cross-segment heatmaps, behavioral distributions, referential audits, and CSV exports.
- `EduPro Online Platform.xlsx`: Operational platform dataset containing `Users`, `Courses`, `Teachers`, and `Transactions` sheets.
- `requirements.txt`: Python runtime dependencies (`streamlit`, `pandas`, `plotly`, `openpyxl`).
- `reports/research_paper.md`: Complete research paper detailing background, methodology, empirical findings, and academic discussion.
- `reports/executive_summary.md`: Stakeholder-oriented executive summary with KPI scorecards, strategic insights, and institutional recommendations.

---

## 🚀 Running the Streamlit Dashboard

### Local Environment (Windows / Mac / Linux)
1. Ensure Python 3.10+ is installed.
2. Open a terminal in this project directory:
   ```bash
   py -3.12 -m pip install -r requirements.txt
   py -3.12 -m streamlit run app.py
   ```
   *(Or using virtual environment:)*
   ```bash
   python -m venv .venv
   .venv\Scripts\activate       # Windows
   pip install -r requirements.txt
   streamlit run app.py
   ```
3. The dashboard will automatically detect and load `EduPro Online Platform.xlsx` from the root directory. You can also upload custom workbooks using the sidebar file uploader.

---

## 📊 Key Findings Summary

- **Total Enrollments:** 10,000 transactions across 3,000 unique learners and 60 courses.
- **Data Quality:** 100% referential integrity with zero missing IDs and zero orphan records.
- **Dominant Age Segment:** 26–35 years old (48.0% of total enrollments), followed by 18–25 (37.3%) and <18 (14.7%). Learners are aged 15–35 (mean: 24.97 years).
- **Gender Parity:** 50.8% female vs. 49.2% male enrollments, demonstrating balanced participation across technical, creative, and business domains.
- **Top Course Category:** Data Science (916 enrollments, 9.16%), followed by Finance (864 enrollments) and Web Development (844 enrollments).
- **Delivery Model:** Free courses drive 64.03% of enrollments, serving as the primary discovery and top-of-funnel entry point.
- **Engagement Skew:** 54.0% of users take 1 course, while a dedicated core of 25.6% take 3+ courses (up to 16 courses).

---

## 🔗 Project Links & Submission Assets

- **GitHub Repository:** [https://github.com/Chhaya-77/EduPro_Learner_Analytics_Project](https://github.com/Chhaya-77/EduPro_Learner_Analytics_Project)
- **Academic Research Paper:** [reports/research_paper.md](reports/research_paper.md)
- **Executive Summary Report:** [reports/executive_summary.md](reports/executive_summary.md)
