# Learner Demographics and Course Enrollment Behavior Analysis on EduPro
## Descriptive Exploratory Data Analysis Research Report

**Prepared for:** EduPro Academic Review & Unified Mentor Project Evaluation  
**Collaborating Institution:** City of Toronto Government – Parks, Forestry & Recreation / Educational Technology Initiative  
**Analysis Type:** Descriptive Learner Intelligence and Exploratory Data Analysis (EDA)  
**Dataset Reference:** `EduPro Online Platform.xlsx` (Users: 3,000 rows | Courses: 60 rows | Transactions: 10,000 rows)  
**Publication Date:** October 2026  

---

## Abstract
This research study provides foundational descriptive learner intelligence for the EduPro online education platform. As digital learning environments scale, understanding demographic composition and enrollment choice behavior is vital for evidence-based course design, targeted marketing, inclusive curriculum development, and resource planning. Utilizing an integrated multi-table relational schema linking learner profiles (`Users`), curriculum specifications (`Courses`), and enrollment records (`Transactions`), this paper evaluates 10,000 course enrollment transactions across 3,000 unique learners and 60 courses. 

Key empirical findings indicate:
1. **Age concentration:** The learner population is concentrated exclusively between ages 15 and 35 (mean: 24.97 years, median: 25.0 years), with young working adults aged 26–35 driving 48.0% of total enrollments, followed by higher education students aged 18–25 (37.3%) and secondary learners under 18 (14.7%).
2. **Gender parity:** Female and male learners demonstrate near-perfect balance in platform representation (50.7% female vs. 49.3% male) and enrollment activity (50.8% female vs. 49.2% male), across technical and business subjects alike.
3. **Course demand:** Data Science (916 enrollments, 9.16%) and Finance (864 enrollments, 8.64%) represent the highest-demand subject domains, while free courses account for 64.03% of all enrollments compared to 35.97% for paid offerings.
4. **Skill level distribution:** Foundational courses (Beginner: 35.73%) and mastery courses (Advanced: 34.75%) attract substantial interest, outpacing Intermediate offerings (29.52%).
5. **Engagement concentration:** While median enrollment per active user is 1.0 course, a highly engaged core of 25.6% of learners account for 3 or more enrollments (up to 16 courses).

This study emphasizes descriptive empirical observations without causal speculation or predictive modeling, establishing verified baselines for municipal and institutional education planning.

---

## 1. Background and Context
Online learning platforms serve an increasingly diverse global populace across varied age cohorts, gender distributions, academic preparations, and career aspirations. For an educational enterprise like EduPro, understanding learner identities and enrollment dynamics is foundational for:
- Designing pedagogically relevant and structured course curricula.
- Enhancing learner retention and sustained engagement.
- Developing targeted outreach campaigns for underserved demographics.
- Fostering equity, inclusivity, and accessibility across course catalogs.

In partnership with municipal human capital development frameworks (such as the City of Toronto Parks, Forestry & Recreation initiatives), this project centers strictly on **descriptive learner intelligence**. The methodology avoids black-box predictive algorithms or commercial monetization optimization, prioritizing transparent, verifiable data governance and empirical clarity.

---

## 2. Problem Statement
Despite maintaining transactional activity logs and registered user databases, EduPro previously lacked systematic empirical answers to core institutional questions:
1. **Age cohort participation:** Which age brackets constitute the platform's primary demographic base, and where do participation gaps exist?
2. **Gender-differentiated patterns:** Do enrollment rates, subject selections, or skill level choices differ systematically between female and male learners?
3. **Catalog demand dynamics:** Which course subject categories attract maximum learner engagement, and which areas underperform?
4. **Skill-level readiness:** Are beginner, intermediate, and advanced courses equally utilized, or do specific demographic segments cluster at particular skill levels?
5. **Behavioral concentration:** Does platform engagement reflect uniform distributed participation or heavy skew toward repeat learners?

Without answers to these questions, organizational decisions regarding curriculum investment, instructor hiring, and community outreach remain driven by intuition rather than empirical evidence.

---

## 3. Dataset Architecture and Field Specifications
The analysis examines the complete `EduPro Online Platform.xlsx` workbook comprising three primary operational tables joined via referential keys (`UserID`, `CourseID`):

| Entity Table | Dimensions | Primary Keys | Key Utilized Fields | Purpose & Analytical Role |
| :--- | :--- | :--- | :--- | :--- |
| **Users** | 3,000 rows × 5 cols | `UserID` | `UserID`, `UserName`, `Age`, `Gender`, `Email` | Demographic baseline; age segmentation and gender parity assessment. |
| **Courses** | 60 rows × 8 cols | `CourseID` | `CourseID`, `CourseName`, `CourseCategory`, `CourseType`, `CourseLevel`, `CoursePrice`, `CourseDuration`, `CourseRating` | Catalog taxonomy; subject categories (12 domains, 5 courses each), access model (Free/Paid), skill tiers. |
| **Transactions** | 10,000 rows × 7 cols | `TransactionID` | `TransactionID`, `UserID`, `CourseID`, `TransactionDate`, `Amount`, `PaymentMethod`, `TeacherID` | Platform engagement event log; timestamps (Jan 1, 2025 – Dec 30, 2025), pricing transactions, payment channels. |

---

## 4. Analytical Methodology (Step-by-Step)

### Step 1: Data Integration & Referential Integrity Audit
Data integration was conducted using a left-outer join model rooted on the `Transactions` fact table, linking learner attributes from `Users` (`Transactions.UserID = Users.UserID`) and curriculum metadata from `Courses` (`Transactions.CourseID = Courses.CourseID`).
- **Integrity Result:** 100% referential integrity achieved. Zero (0) orphan transaction records were detected; every enrollment strictly corresponds to a valid user and an active course.
- **Completeness:** Zero missing values across `UserID`, `CourseID`, `Age`, `Gender`, `CourseCategory`, `CourseType`, and `CourseLevel`.

### Step 2: Demographic Segmentation
Learners were classified into standardized analytical age brackets:
- `<18`: Secondary school / minor learners (observed range: 15–17 years).
- `18–25`: Tertiary / university-age emerging adults.
- `26–35`: Early-to-mid career professionals and upskillers.
- `36–45` & `46+`: Mid-to-late career adult learners (observed count: 0).
- Gender identifiers were standardized into clean binary categorical labels (`Female`, `Male`).

### Step 3: Key Performance Indicators (KPIs) Formulation
In compliance with the project framework, five core KPIs were formalized:
1. **Total Enrollments:** Platform engagement volume indicator ($N = 10,000$).
2. **Enrollments by Age Group:** Demographic reach across generation cohorts.
3. **Gender Participation Ratio:** Balance and inclusivity index across courses and categories.
4. **Category Popularity Index:** Relative demand across 12 distinct educational categories.
5. **Level Preference Distribution:** Skill maturity index (Beginner vs. Intermediate vs. Advanced).

---

## 5. Empirical Results and Findings

### 5.1 Platform Scale & Demographic Distribution
The learner population consists of 3,000 registered individuals generating 10,000 total course enrollments.

| Demographic Segment | Unique Learners ($n$) | Share of Learners (%) | Total Enrollments ($N$) | Share of Enrollments (%) | Enrollments / Learner |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Age Cohort** | | | | | |
| `<18` (15–17 yrs) | 433 | 14.43% | 1,469 | 14.69% | 3.39 |
| `18–25` yrs | 1,121 | 37.37% | 3,732 | 37.32% | 3.33 |
| `26–35` yrs | 1,446 | 48.20% | 4,799 | 47.99% | 3.32 |
| `36–45` yrs | 0 | 0.00% | 0 | 0.00% | 0.00 |
| `46+` yrs | 0 | 0.00% | 0 | 0.00% | 0.00 |
| **Gender** | | | | | |
| Female | 1,520 | 50.67% | 5,078 | 50.78% | 3.34 |
| Male | 1,480 | 49.33% | 4,922 | 49.22% | 3.33 |
| **Platform Total** | **3,000** | **100.00%** | **10,000** | **100.00%** | **3.33** |

#### Key Demographic Insights:
- **Youth & Career-Transition Skew:** The learner base is strictly between ages 15 and 35. Over 85.5% of learners are aged 18 to 35, highlighting EduPro's adoption as a post-secondary and workplace advancement platform.
- **Remarkable Gender Parity:** The platform exhibits balanced participation across genders, with women representing 50.7% of learners and 50.8% of enrollments, and men representing 49.3% of learners and 49.2% of enrollments.

---

### 5.2 Course Category Popularity & Demand Index
The catalog features 60 courses distributed evenly across 12 categories (5 courses per category).

| Category Rank | Course Category | Available Courses | Total Enrollments | Share of Catalog (%) | Mean Rating |
| :---: | :--- | :---: | :---: | :---: | :---: |
| 1 | **Data Science** | 5 | 916 | 9.16% | 3.65 |
| 2 | **Finance** | 5 | 864 | 8.64% | 3.55 |
| 3 | **Web Development** | 5 | 844 | 8.44% | 3.52 |
| 4 | **Business** | 5 | 833 | 8.33% | 3.61 |
| 5 | **Artificial Intelligence** | 5 | 829 | 8.29% | 3.63 |
| 6 | **Project Management** | 5 | 829 | 8.29% | 3.64 |
| 7 | **Design** | 5 | 827 | 8.27% | 3.57 |
| 8 | **Cybersecurity** | 5 | 819 | 8.19% | 3.57 |
| 9 | **Machine Learning** | 5 | 819 | 8.19% | 3.65 |
| 10 | **Digital Marketing** | 5 | 808 | 8.08% | 3.73 |
| 11 | **Marketing** | 5 | 806 | 8.06% | 3.62 |
| 12 | **Programming** | 5 | 806 | 8.06% | 3.72 |

**Analysis:**
- Demand across categories is relatively balanced, ranging between 8.06% (Programming, Marketing) and 9.16% (Data Science).
- Data Science and Finance emerge as clear leaders, reflecting strong market demand for quantitative analytical skills.

---

### 5.3 Course Level & Delivery Model Distribution

| Dimension | Classification | Courses Offered | Enrollments ($N$) | Proportion (%) |
| :--- | :--- | :---: | :---: | :---: |
| **Course Level** | Beginner | 21 | 3,573 | 35.73% |
| | Advanced | 21 | 3,475 | 34.75% |
| | Intermediate | 18 | 2,952 | 29.52% |
| **Course Type** | Free | 38 | 6,403 | 64.03% |
| | Paid | 22 | 3,597 | 35.97% |

**Cross-Tabulation: Level vs. Delivery Type:**
- Free courses account for 67.0% of Beginner enrollments (2,395 free vs. 1,178 paid) and 67.8% of Intermediate enrollments (2,003 free vs. 949 paid).
- Advanced courses see stronger willingness to pay, with 1,470 paid enrollments (42.3%) out of 3,475 total.

---

### 5.4 Demographics × Course Preference Interaction

#### A. Age Group × Course Category Preferences (Percentage within Age Cohort)
Cross-tabular evaluation demonstrates that learner interests are broadly distributed across all age groups:
- **`<18` Cohort:** Highest relative interests in Web Development (8.99%), Artificial Intelligence (8.78%), and Data Science (8.78%).
- **`18–25` Cohort:** Highest relative interests in Web Development (8.98%), Finance (8.82%), and Data Science (8.79%).
- **`26–35` Cohort:** Highest relative interests in Data Science (9.56%), Finance (8.69%), and Project Management (8.48%).

#### B. Gender × Course Level Preferences
- **Female Learners:** Beginner (35.66%, $n=1,811$), Advanced (34.62%, $n=1,758$), Intermediate (29.72%, $n=1,509$).
- **Male Learners:** Beginner (35.80%, $n=1,762$), Advanced (34.88%, $n=1,717$), Intermediate (29.32%, $n=1,443$).
- **Conclusion:** There is virtually identical level selection across genders (within 0.2 percentage points across all three levels), demonstrating no gender disparity in difficulty preference.

---

### 5.5 Learner Engagement & Behavioral Concentration
Analysis of individual enrollment frequencies demonstrates significant variation in engagement depth:
- **Mean enrollments per active user:** 3.33 courses.
- **Median enrollments per active user:** 1.00 course.
- **Single-Course Enrollees:** 1,620 learners (54.00%) enrolled in exactly 1 course.
- **Two-Course Enrollees:** 612 learners (20.40%) enrolled in 2 courses.
- **Power Learners (3+ courses):** 768 learners (25.60%) enrolled in 3 or more courses, reaching a maximum of 16 courses.
- **Super Users (10+ courses):** 453 learners (15.10%) enrolled in 10 or more courses, generating nearly half of all platform transaction volume.

---

## 6. Discussion and Strategic Implications
1. **The 35+ Demographic Blind Spot:**
   The absence of learners aged 36 and above in the dataset represents an opportunity for adult education programs. With demographic trends emphasizing lifelong learning, reskilling, and mid-career adaptation, EduPro has an untapped market among older adult learners.
2. **Equal Technical Participation by Gender:**
   Unlike historical STEM enrollment disparities reported in legacy literature, EduPro exhibits gender parity in Data Science, Artificial Intelligence, Cybersecurity, and Programming. Marketing and outreach efforts should build on this baseline.
3. **Free Course "On-Ramp" Model:**
   With 64.03% of all enrollments in free courses, free content serves as the primary top-of-funnel discovery mechanism for the platform.
4. **Bimodal Skill Distribution:**
   Demand is concentrated at Beginner (35.73%) and Advanced (34.75%) tiers, with Intermediate offerings receiving fewer enrollments (29.52%). Learners appear to prioritize foundational entry points followed by mastery certifications.

---

## 7. Actionable Recommendations

### Recommendation 1: Expand Adult & Mid-Career Learner Outreach (Ages 36+)
- **Action:** Collaborate with municipal workforce development agencies (such as Toronto Employment & Social Services) to launch targeted retraining modules for career changers aged 36–60.
- **Rationale:** The current demographic boundary at age 35 indicates that older adults are either unaware of the platform or find the catalog unsuited to mid-career needs.

### Recommendation 2: Capitalize on Proven Gender Parity in Technical Domains
- **Action:** Highlight gender balance in promotional materials and community forums. Implement peer-mentoring groups to sustain high completion rates among female technologists.
- **Rationale:** 50.8% female enrollment across technical courses is a competitive differentiator.

### Recommendation 3: Bridge the Intermediate Level Chasm
- **Action:** Redesign intermediate course syllabi into hands-on project portfolios, creating clear progression paths from beginner courses into advanced specializations.
- **Rationale:** Intermediate courses capture the lowest enrollment share (29.52%), suggesting a perceived value gap between basic tutorials and expert content.

### Recommendation 4: Nurture Repeat & Multi-Course Learners
- **Action:** Introduce curated "Learning Pathways" (e.g., *Data Science + Business Analytics + Python Programming*) to guide single-course users (54.0%) toward multi-course skill development.
- **Rationale:** Moving just 15% of single-course learners to a second course would yield over 240 additional completions.

---

## 8. Limitations and Ethical Considerations
- **Descriptive Boundary:** The dataset captures transaction-level enrollment registrations rather than course completions, test scores, or drop-out timings. High enrollment does not directly confirm academic success or course satisfaction.
- **Synthetic/Sampling Constraints:** The exact upper bound of age at 35 and uniform course counts (5 per category) suggest a curated or synthetic cohort dataset. Findings should be re-evaluated as additional live transaction data is recorded.
- **Privacy Safeguards:** In accordance with municipal and privacy best practices, all user identification numbers (`UserID`) are anonymized, and direct personal identifiers (`UserName`, `Email`) are excluded from public dashboard visualizers.

---

## 9. Conclusion
This study provides an empirical profile of learner demographics and course enrollment behaviors on EduPro. By establishing exact quantitative baselines—spanning 3,000 unique learners, 10,000 enrollment records, and 60 courses—the findings offer actionable insights for curriculum structuring, platform accessibility, and municipal educational partnerships. The accompanying Streamlit analytics application operationalizes these insights for stakeholders, enabling interactive slice-and-dice exploration across all core demographics.
