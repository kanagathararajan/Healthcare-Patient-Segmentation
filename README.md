# Healthcare Patient Segmentation and Strategic Recommendation System

## Project Overview

This project focuses on identifying meaningful patient segments using healthcare utilisation patterns and claim-cost information. It applies RFM analysis and K-Means clustering to group patients into different categories and proposes strategic recommendations for each group.

The objective is to help healthcare management understand patient behaviour, identify high-utilisation groups and improve resource planning through data-driven insights.

## Problem Statement

Healthcare organisations often follow similar engagement and resource allocation strategies for all patients, regardless of their healthcare utilisation patterns.

This project addresses the problem by:
- Identifying different patient utilisation patterns.
- Understanding patient visit frequency and recency.
- Analysing claim-cost distribution across patient segments.
- Developing targeted strategies for each identified segment.

## Dataset

**Dataset:** Synthea Synthetic Healthcare Dataset

The dataset contains synthetic healthcare records, including patient demographics, encounters, conditions and other healthcare information.

**Analysis scope:**
- Selected period: January 2010 – April 2020.
- Patients included: 1,056.
- Data source: Synthea synthetic healthcare records.

**Note:** This is a synthetic, US-oriented dataset used as a prototype. It does not represent actual patients or the four fictional Hyderabad hospitals described in the assignment.

## Technologies Used

- Python
- Pandas – Data manipulation and cleaning
- NumPy – Numerical operations
- Matplotlib and Seaborn – Data visualisation
- Scikit-learn – Data preprocessing and K-Means clustering
- Google Colab – Development environment

## Project Methodology

### 1. Data Cleaning and Preprocessing
- Handled duplicate records.
- Processed missing values.
- Converted date columns into appropriate formats.
- Filtered the selected analysis period.
- Calculated encounter duration.
- Created patient-level features.

### 2. Feature Engineering

The following features were generated:

| Feature | Description |
|---|---|
| Recency | Days since the patient's latest encounter |
| Frequency | Total number of encounters |
| Monetary | Total healthcare claim cost |
| Inpatient Count | Number of inpatient encounters |
| Emergency Count | Number of emergency encounters |
| Average Duration | Average encounter duration |
| Unique Conditions | Number of distinct recorded conditions |

### 3. Exploratory Data Analysis

Analysed:
- Patient visit frequency.
- Claim-cost distribution.
- Patient recency.
- Feature correlations.
- Outliers and data distributions.

### 4. RFM Analysis

Applied Recency, Frequency and Monetary scoring to classify patients based on their healthcare utilisation patterns.

### 5. K-Means Clustering

- Applied percentile-based capping to reduce the influence of extreme values.
- Used logarithmic transformation.
- Applied StandardScaler.
- Compared clustering configurations using silhouette scores.
- Selected K=3 for further business interpretation.

### Model Comparison

| Number of Clusters | Silhouette Score |
|---|---:|
| K=2 | 0.3166 |
| K=3 | 0.2756 |
| K=4 | 0.3000 |
| K=5 | 0.2233 |
| K=6 | 0.2215 |

Although K=2 achieved the highest silhouette score, K=3 was selected as a business-oriented compromise because it provided three actionable segments, each containing more than 5% of the patients.

## Key Results

The final K=3 model identified the following patient segments:

| Patient Segment | Patient Count | Patient Share | Claim-Cost Share |
|---|---:|---:|---:|
| Low Utilisation Patients | 593 | 56.16% | 27.71% |
| Frequent Care Patients | 380 | 35.98% | 55.97% |
| High Inpatient Utilisation Patients | 83 | 7.86% | 16.32% |

### Key Insights

- Frequent Care Patients account for approximately 56% of total claim costs.
- High Inpatient Utilisation Patients represent approximately 8% of patients but contribute over 16% of claim costs.
- Low Utilisation Patients form the largest segment, representing over 56% of the analysed population.

## Strategic Recommendations

| Segment | Recommended Strategy |
|---|---|
| Low Utilisation Patients | Preventive healthcare awareness and follow-up reminders |
| Frequent Care Patients | Care coordination and appointment management |
| High Inpatient Utilisation Patients | Discharge follow-ups and inpatient care pathway reviews |

These strategies are proposed recommendations and require validation through real-world implementation.

## Project Limitations

- The dataset contains synthetic US-oriented healthcare records.
- The analysis does not represent actual Hyderabad hospital operations.
- Claim costs are used as a healthcare cost proxy, not actual hospital revenue or profit.
- Bed occupancy could not be calculated because bed-capacity information was unavailable.
- Average encounter duration should not be interpreted as inpatient length of stay.
- Validated 30-day readmission metrics were not established.

## Future Enhancements

- Incorporate larger and more representative healthcare datasets.
- Include hospital-level operational information.
- Develop validated readmission and bed-occupancy metrics.
- Compare patient segment migration across different time periods.
- Evaluate the effectiveness of proposed strategies using real-world outcomes.

## Conclusion

This project demonstrates how RFM analysis and K-Means clustering can be used to identify distinct healthcare utilisation patterns.

The resulting patient segments provide a foundation for developing targeted engagement strategies and improving healthcare resource planning.

---

**Project Type:** Data Science | Healthcare Analytics | Unsupervised Machine Learning

**Developed using:** Python and Google Colab
