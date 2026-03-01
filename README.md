# Behavioral Analytics-Based Financial Impulse Risk Modeling - VR Sona (22MIA1161)

An AI-powered behavioral analytics platform that detects impulsive financial patterns using machine learning and behavioral signal engineering.

---

## Objective

The objective of this project is to:

- Detect impulsive spending patterns using ML
- Analyze behavioral financial signals
- Provide explainable AI insights
- Generate strategic financial recommendations
- Present results through an interactive modern dashboard

This system combines behavioral psychology + anomaly detection + volatility modeling to classify financial behavior into meaningful categories.

---
## Synthetic Data Generation & Feature Engineering

Since real personal financial transaction data is sensitive and restricted, this project uses a carefully designed synthetic transaction dataset that mimics real-world financial behavior patterns.

---

### How the Dataset Was Generated

The synthetic dataset was generated using controlled statistical distributions and behavioral assumptions to simulate realistic financial patterns.

#### Transaction Amount Distribution

Transaction values were generated using:

- Normal distribution for regular spending
- Log-normal distribution for high-value purchases
- Random anomaly injection for outlier detection testing

Assumptions:
- Most daily transactions fall within a moderate spending range.
- Occasional high-value transactions simulate impulse events.
- Standard deviation reflects volatility in spending behavior.

---

#### Time-Based Behavioral Rules

To simulate behavioral psychology patterns:

- Late-night transactions were probabilistically assigned between 9 PM – 5 AM.
- Weekend spending was assigned higher discretionary spending weights.
- End-of-month days (after 25th) were assigned increased probability for clustered spending.

Assumptions:
- Emotional spending is more likely at night.
- Weekends increase discretionary purchases.
- Month-end may trigger budget exhaustion or bulk payments.

---

#### Frequency Modeling

Transaction frequency was generated using:

- Poisson distribution to simulate realistic transaction counts.
- Variable transaction density across daily, weekly, and monthly periods.

Assumptions:
- Higher frequency correlates with increased impulsivity.
- Sudden transaction spikes indicate potential anomaly behavior.

---

## Dataset Size

- Total Records: 10,000+ synthetic transactions
- Time Span Simulated: 12 months
- Categories Included:
  - Food
  - Transport
  - Shopping
  - Bills
  - Entertainment
  - Other

---

## Feature Engineering

The following behavioral features were derived from raw transactions:

| Feature Name        | Description |
|---------------------|------------|
| `mean_spend`        | Average transaction value |
| `std_spend`         | Spending volatility |
| `night_ratio`       | % of transactions between 9PM–5AM |
| `weekend_ratio`     | % of weekend transactions |
| `end_month_ratio`   | % of transactions after 25th |
| `frequency_spike`   | Total transaction count in selected period |
| `anomaly_score`     | Isolation Forest anomaly detection score |
| `impulse_risk_score`| Final weighted behavioral risk score |

---

## Risk Score Construction

The impulse risk score is calculated as a weighted aggregation of:

- Anomaly intensity (30%)
- Spending volatility (30%)
- Transaction frequency (20%)
- Night behavior ratio (10%)
- Weekend behavior ratio (10%)

The final score is normalized to a 0–100% scale.

---

## Behavioral Assumptions Embedded

The model assumes:

- High volatility = unstable spending control
- Night-heavy spending = emotional decision bias
- High anomaly score = irregular purchase patterns
- Month-end clustering = budget pressure behavior
- High frequency = impulsive tendency

These behavioral signals collectively determine classification into:

- High Impulse Behaviour
- High Volatility Pattern
- Late-Night Emotional Spending
- Weekend-Driven Spending
- Controlled Financial Behaviour

---

## Why Synthetic Data?

Using synthetic data ensures:

- No privacy violations
- Controlled experimentation
- Reproducibility
- Safe model evaluation
- Transparent behavioral simulation

---

This dataset enables the system to realistically simulate behavioral finance scenarios while maintaining ethical data practices.


---


## What This System Does

The platform:

✔ Calculates Impulse Risk Score (0–100%)  
✔ Detects financial behavior type  
✔ Classifies severity (Low / Medium / High)  
✔ Calculates confidence score  
✔ Generates AI-written executive summary  
✔ Provides ML explainability breakdown  
✔ Produces strategic recommendations  

---

## Machine Learning Engine

The backend uses:

- Isolation Forest (Anomaly Detection)
- Volatility Scoring
- Behavioral Signal Engineering:
  - Night Spending Ratio
  - Weekend Ratio
  - End-of-Month Ratio
  - Spending Frequency
- Weighted Risk Aggregation Model

---

## Architecture
Frontend (Next.js + Tailwind + Recharts)
↓
FastAPI Backend
↓
ML Scoring Engine
↓
Behavioral Classification

---


---

## Project Structure
financial-impulse-detection/
│
├── api/ # FastAPI backend
│ ├── app.py
│ ├── engine.py
│ ├── scoring.py
│ ├── profiles.py
│ ├── nudges.py
│ ├── finance.db
│ └── requirements.txt
│
├── impulse-frontend/ # Next.js frontend
│ ├── app/
│ ├── components/
│ ├── globals.css
│ └── package.json
│
├── data/
│ └── synthetic_transactions.csv
│
├── models/
├── notebooks/
├── README.md
└── requirements.txt

---


---

## Features Implemented

### Risk Detection
- Impulse Risk Score (percentage)
- Behavioral Severity Classification
- Confidence Score

### Interactive Dashboard
- Risk Gauge
- Spending Trend Chart
- Category Distribution Pie Chart
- Radar Behavior Chart
- Feature Cards

### AI Insights
- Executive Summary
- Behavior Detection Banner (Dynamic Color)
- ML Explainability Breakdown
- Professional Strategic Recommendations

---

### Dashboard Overview

<img width="1469" height="576" alt="image" src="https://github.com/user-attachments/assets/e5d99649-68e8-401f-be9a-9d5d17f1af79" />

<img width="1450" height="831" alt="image" src="https://github.com/user-attachments/assets/725fc3a7-6fc3-4846-b402-b041b17c2071" />

---

### Risk Gauge + Feature Cards

<img width="1451" height="828" alt="image" src="https://github.com/user-attachments/assets/0d98d99f-5f05-49f7-a4a4-54166cd35b22" />

<img width="1414" height="460" alt="image" src="https://github.com/user-attachments/assets/cb044268-1e4a-4ea7-91ca-2905f3458926" />

---

### Behaviour Analysis & Recommendations

<img width="1451" height="812" alt="image" src="https://github.com/user-attachments/assets/81d1f5ef-2f9c-4584-839a-9c4a55b294f6" />


---

### ML Explainability Breakdown

<img width="784" height="376" alt="image" src="https://github.com/user-attachments/assets/66c75f29-0ee8-4ae4-b8f5-c327e82bf795" />

---

## Deployment

### Frontend
- Built using **Next.js**
- Can be deployed on:
  - Vercel
  - Netlify

### Backend
- Built using **FastAPI**
- Can be deployed on:
  - Render
  - Railway
  - AWS EC2
  - DigitalOcean

---

## Local Setup Instructions

### Backend Setup
cd api
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app:app --reload

---

### Frontend Setup
cd impulse-frontend
npm install
npm run dev








