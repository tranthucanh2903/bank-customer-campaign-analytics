# Bank Customer Campaign Analytics

**SQL | Python | Statistics | Power BI**

An end-to-end analytics portfolio project based on the **UCI Bank Marketing dataset**.  
The project analyzes **45,211 campaign contact records** to explore customer conversion, previous campaign outcomes, contact channels, and campaign contact frequency.

---

## Dashboard

> Add the final Power BI dashboard screenshot here after uploading it to the repository.

```markdown
![Bank Customer Campaign Analytics Dashboard](dashboard/bank_dashboard_preview.png)
```

---

## Business Questions

This project focuses on several practical campaign questions:

- What is the overall campaign conversion rate?
- How does conversion differ by previous campaign outcome?
- Does conversion vary with the number of contacts made during the current campaign?
- Which contact channels show higher observed conversion?
- Which customer groups show different conversion patterns?
- Which variables should **not** be used for pre-contact targeting because of data leakage?

---

## Key KPIs

| KPI | Result |
|---|---:|
| Total campaign contacts | **45,211** |
| Total conversions | **5,289** |
| Overall conversion rate | **11.70%** |
| Average campaign contacts | **2.76** |
| Previous campaign success conversion rate | **64.73%** |

---

## Key Findings

### 1. Previous campaign outcome is strongly associated with conversion

Observed conversion rates by previous campaign outcome:

| Previous outcome | Conversion rate |
|---|---:|
| Success | **64.73%** |
| Other | **16.68%** |
| Failure | **12.61%** |
| Unknown | **9.16%** |

Customers with a successful previous campaign showed substantially higher observed conversion than the other groups.

### 2. Higher contact frequency is associated with lower conversion

| Campaign contact frequency | Conversion rate |
|---|---:|
| 1 contact | **14.60%** |
| 2–3 contacts | **11.20%** |
| 4+ contacts | **7.35%** |

The pattern suggests that repeated campaign contact does not necessarily correspond to higher conversion. Because this is observational data, this result should not be interpreted as a causal effect of additional contacts.

### 3. Conversion differs by contact channel

| Contact channel | Conversion rate |
|---|---:|
| Cellular | **14.92%** |
| Telephone | **13.42%** |
| Unknown | **4.07%** |

The `unknown` contact group shows a considerably lower observed conversion rate than the identified contact channels.

---

## Power BI Dashboard

The interactive Power BI report was designed to provide a management-friendly view of campaign performance.

Main dashboard elements include:

- Total campaign contacts
- Total conversions
- Overall conversion rate
- Average campaign contacts
- Conversion rate by previous campaign outcome
- Campaign contacts and conversion rate by month
- Conversion rate by age group
- Conversion rate by contact channel
- Campaign outcome distribution
- Interactive filters for customer and campaign characteristics

---

## Analytical Workflow

```text
Raw Data
   ↓
Data Cleaning & Transformation
   ↓
Exploratory Analysis
   ↓
KPI Validation
   ↓
Statistical / Business Interpretation
   ↓
Power BI Data Model
   ↓
Interactive Dashboard
```

The Power BI package also contains validation outputs used to reconcile the dashboard KPIs with the underlying data.

---

## Data Leakage Consideration

The dataset contains a `duration` variable representing the duration of the campaign call.

This variable is only known **after the call has occurred**. Therefore, it should not be used as an input for pre-contact targeting or prediction because doing so would introduce **data leakage**.

In this project, `duration` is treated only as a post-call descriptive variable rather than a targeting feature.

---

## Interpretation Principle

The analysis is based on observational campaign data.

Accordingly:

- reported patterns are **associations**, not causal effects;
- differences between customer or campaign groups should not be interpreted as proof that one factor caused conversion;
- business recommendations should be treated as hypotheses for further testing, such as controlled experiments or A/B tests.

---

## Repository Structure

A clean public repository can be organized as follows:

```text
bank-customer-campaign-analytics/
│
├── README.md
│
├── dashboard/
│   ├── bank_dashboard_preview.png
│   └── Bank_Customer_Campaign_Analytics.pbix
│
├── data/
│   └── data_dictionary.csv
│
├── sql/
│   └── analysis.sql
│
├── python/
│   └── bank_analysis.py
│
└── docs/
    └── methodology.md
```

> The SQL/Python folders should only be added when the corresponding analysis files are available. Do not upload placeholder code as if it had been used in the project.

---

## Power BI Model Files

The current project package includes:

- `Bank_Customer_Campaign_Analytics.pbip`
- Power BI Report definition files
- Semantic Model definition files
- `fact_customers.csv`
- `dim_date.csv`
- `kpi_management_summary.csv`
- `KPI_VALIDATION.csv`

These files support reproducibility of the Power BI reporting layer.

---

## Data Source

**UCI Bank Marketing Dataset**  
Moro et al. (2014)

The public dataset contains direct marketing campaign information from a Portuguese banking institution.

---

## Tools

- **Power BI** — dashboard development and interactive reporting
- **Power Query / Data Model** — data preparation and reporting structure
- **SQL** — analytical querying *(include code in the repository when available)*
- **Python / pandas** — data analysis and validation *(include code in the repository when available)*
- **Statistics** — interpretation of observed conversion patterns

---

## Limitations

- The dataset is observational and does not establish causal effects.
- Campaign records should not automatically be interpreted as unique real-world customers without considering the dataset grain.
- `duration` cannot be used for pre-contact targeting without introducing leakage.
- Monthly results represent the month categories available in the dataset and should not automatically be interpreted as a continuous modern time-series trend.

---

## Author

**Thục Anh Trần**  
Development Economics — Data Analysis Orientation  
University of Economics and Business, Vietnam National University, Hanoi

LinkedIn: *add LinkedIn profile link here*

---

## Project Status

**Power BI dashboard completed.**  
GitHub documentation and supporting analytical files are being organized for portfolio publication.
