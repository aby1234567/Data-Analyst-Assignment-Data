# 📊 BI Dashboard & Stakeholder Report

👉 Check out the 
<a href="https://your-bi-dashboard-link.com" target="_blank"><strong>BI Dashboard</strong></a> and the 
<a href="https://<username>.github.io/<repo-name>/reports/stake_holder.html" target="_blank"><strong>Stakeholder Report</strong></a>.

---

## 🔄 Overall Process & Workflow

1. **Data Loading**  
   All the provided datasets were first loaded into **Jupyter Notebooks** using **pandas**.

2. **Data Inspection & Cleaning**  
   Performed **Exploratory Data Analysis (EDA)** and data cleaning with **pandas**.

3. **Dataset Preparation**  
   The cleaned datasets were transformed into new datasets ready for visualization.

4. **Visualization & Reporting**  
   The processed datasets were loaded into **Google Looker Studio** for deeper analysis and stakeholder reporting.

---

## 🛠️ Tools & Libraries Used

- **[Jupyter Notebook](https://jupyter.org/)** (Python 3.11)  
- **[Google Looker Studio](https://lookerstudio.google.com/)**  
- **Gemini Canvas**  
- **[pandas](https://pandas.pydata.org/)**  
- **Python `re` library**

---

## ⚖️ Assumptions

- The **cost** in `ad_performance.csv` is considered as **INR**.  
- All accounts with an entry in `subscriptions.csv` are assumed to have gone through a **trial period before subscribing**.  
- In `subscriptions.csv`, the **status** column is taken as the **source of truth** for client status.  
- Some `billing_start_date` and `trial_start_date` values appear **after** `billing_end_date` and `trial_end_date`. In those cases, **end_date** is assumed to be correct.  
- `conversion_flag` conflicts with `status` in some cases.  
  - If **status = cancelled** and **conversion_flag = no** → _Dropped after trial_  
  - If **status = cancelled** and **conversion_flag = yes** → _Churned_  
- Retention is measured using **server activity** of accounts:  
  - **M1:** 1–30 days from first activity date  
  - **M2:** 30–60 days from first activity date  
  - **M3:** 60–90 days from first activity date  
  - *Note:* `event_date` is used even when it precedes `signup_date`, to maximize data points.

---

## 📌 Key Insights (Summary)

### 🪣 The Leaky Bucket  
Our biggest growth obstacle is the **~60% user drop-off** between **Signup → Took Trial**.  
🔑 This is the **top priority** to fix.

### 📉 Declining User Quality  
- **M1 retention** for new users **sharply declined** from **June → August**.  
- This is an **alarming trend** that is directly impacting revenue.

### 🎯 Channel Quality is Key  
- **Referral** → Best M3 retention (**14.1%**)  
- **Organic** → Lowest churn  
- **Google Ads** → High volume but **high churn** users

### 🚀 Path to Growth  
1. **Fix onboarding** → Increase trial activation  
2. **Shift marketing focus** → High-quality channels (**Referral, Organic**)  
3. **Optimize paid ads** → For **user quality**, not just volume

---

## 📂 Repository Structure

```bash
.
├── code/                # Jupyter notebooks (EDA & processing) 
├── data/                # Cleaned datasets 
├── datasets/            # Raw datasets
├── reports/             # Stake holder report
└── README.md            # Project overview
