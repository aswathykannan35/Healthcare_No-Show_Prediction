# Healthcare Appointment No-Show Prediction

Predicting whether a patient will miss their scheduled medical appointment using machine learning, explainability (SHAP), and Power BI analytics.

---
### 1. Introduction

Many times, patients do not show up for their medical appointments.
Previous studies report nearly 25% of all scheduled appointments become No-Shows.

This leads to two major losses:
- Financial loss for hospitals / doctors (empty appointment slots).
- Loss of timely treatment for other patients, who could have taken the slot.
- This project helps clinics and hospitals:
- Understand what factors influence No-Show behavior
- Build a prediction model to estimate the probability of No-Show
- Use insights to optimize overbooking, resource allocation, and patient engagement

---
### 2. Dataset Description (KaggleV2-May-2016)

This project uses the famous Brazilian Medical Appointment No-Show dataset.

#### Columns Description
- PatientId – Unique patient identifier
- AppointmentID – Unique appointment identifier
- Gender – Male/Female
- ScheduledDay – When the appointment was booked
- AppointmentDay – Actual appointment date
- Age – Patient age
- Neighbourhood – Clinic location
- Scholarship – Bolsa Família financial aid
- Hypertension – True/False
- Diabetes – True/False
- Alcoholism – True/False
- Handcap – Number of disabilities (0–4)
- SMS_received – Number of SMS reminders sent
- No-show – Whether the patient missed the appointment

---
### Machine Learning Workflow

#### Data Cleaning & Transformation
- Converted date formats
- Calculated LeadDays (Scheduled → Appointment gap)
- Created AgeCategory and LeadDayCategory
- Target encoded neighbourhood → Neighbourhood_TE
- Added medical risk flag: Old_Chronic
- Extracted:
     - Appointment_Weekday
     - Scheduled_Weekday
     - Appointment_Hour

#### Model Training
Models tested:
- Logistic Regression
- Random Forest
- XGBoost (Best Model)

**Final XGBoost Scores**
- Accuracy: ~0.80
- ROC-AUC: ~0.75

#### Predictions Added to Dataset
- NoShow_Prob (probability of missing the appointment)
- ShowUp_Prob
- Risk_Segment (Low / Medium / High)

---
### Power BI Dashboard

The dashboard includes:
- Total Appointments
- Total No-Shows
- No-Show Rate (%)
- High-Risk %
- No-Shows by Weekday
- Gender Distribution
- Age Category Distribution
- Lead Days vs No-Show Rate (line chart)
- Risk Segment Donut Chart

---

### Summary
This project helps healthcare providers:
- Identify patients likely to miss appointments
- Reduce no-show rates using predictive analytics
- Improve scheduling, reminders, and resource planning
- Understand patient behavior using SHAP explainability
