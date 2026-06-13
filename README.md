# Hotel Booking Cancellation Analysis

End-to-end data analysis of hotel reservations to uncover why bookings get cancelled and how City Hotel and Resort Hotel can reduce cancellation rates and boost revenue.

## Table of Contents

- [Overview](#overview)
- [Business Problem](#business-problem)
- [Dataset](#dataset)
- [Tools and Technologies](#tools-and-technologies)
- [Project Structure](#project-structure)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Key Insights](#key-insights)
- [Dashboard/Model/Output](#dashboardmodeloutput)
- [How to Run This Project?](#how-to-run-this-project)
- [Final Recommendation](#final-recommendation)
- [Future Work](#future-work)
- [Author & Contact](#author--contact)

## Overview

This project performs an end-to-end exploratory data analysis (EDA) on a real-world hotel bookings dataset covering City Hotel and Resort Hotel reservations from 2015–2017. The workflow includes loading and cleaning the raw data, exploring booking and cancellation patterns, visualizing key trends, and converting those findings into clear, actionable business recommendations presented in a final report.

## Business Problem

In recent years, City Hotel and Resort Hotel have experienced high cancellation rates. This results in fewer realized revenues and under-utilized rooms. The objective of this project is to:

- Identify the variables that affect hotel reservation cancellations.
- Understand how cancellations can be reduced.
- Provide insights that help hotels make better pricing and promotional decisions.

## Dataset

- **Name:** Hotel Bookings dataset (`hotel_bookings 2.csv`)
- **Records:** 119,390 bookings
- **Columns:** 32 (hotel type, lead time, arrival date, stays, market segment, distribution channel, average daily rate (ADR), reservation status, cancellation flag, country, etc.)
- **Hotels covered:** City Hotel and Resort Hotel
- **Time period:** 2015 – 2017

## Tools and Technologies

- **Language:** Python
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn
- **Environment:** Jupyter Notebook
- **Reporting:** PDF (project report)

## Project Structure

```
Hotel-Booking-Cancellation-Analysis/
│
├── Dataset/
│   └── hotel_bookings 2.csv
│
├── Data_Analysis_Hotel_Bookings_.ipynb
├── Hotel_Booking_Cancellation_Analysis_Report.docx
├── Hotel_Booking_Cancellation_Analysis_Report.pdf
└── README.md
```

## Data Cleaning & Preparation

The raw dataset required several cleaning steps before analysis:

1. **Date conversion** – Converted `reservation_status_date` from string to datetime format (`%d/%m/%Y`).
2. **Dropped sparse columns** – Removed `company` and `agent` columns due to a high proportion of missing values.
3. **Removed null rows** – Dropped remaining rows containing missing values (e.g., `children`, `country`).
4. **Outlier removal** – Filtered out records where `adr` (Average Daily Rate) was ≥ 5000, as these were unrealistic outliers.
5. **Feature extraction** – Extracted the `month` from `reservation_status_date` to support monthly trend analysis.

## Exploratory Data Analysis (EDA)

The cleaned data was analyzed and visualized using bar charts, grouped bar charts, line charts, and pie charts to explore:

- Overall reservation status (cancelled vs. not cancelled)
- Cancellation rates by hotel type (City Hotel vs. Resort Hotel)
- Average Daily Rate (ADR) trends over time, and ADR comparison between cancelled and non-cancelled bookings
- Monthly cancellation patterns and ADR lost to cancellations per month
- Top 10 countries by number of cancelled reservations
- Booking source / market segment distribution (overall vs. cancelled bookings)

## Key Insights

- About **37.1%** of all bookings were cancelled overall.
- **City Hotel** has a higher cancellation ratio (~41.7%) than **Resort Hotel** (~28%), despite receiving more total bookings.
- **Higher Average Daily Rate (ADR)** is strongly associated with higher cancellation likelihood — cancelled bookings consistently show a higher ADR than non-cancelled ones (2016–2017).
- **January** records the highest number of cancellations and the highest total ADR lost to cancellations of any month.
- **Portugal (PRT)** is by far the top country by number of cancelled reservations, followed by the UK, Spain, France, and Italy.
- **Online Travel Agents (OTA)** are the leading booking channel overall (~47%), but **Group bookings** are disproportionately more likely to be cancelled compared to Direct or Offline Travel Agent bookings.

## Dashboard/Model/Output

- `Data_Analysis_Hotel_Bookings_.ipynb` – Jupyter Notebook containing all data cleaning, EDA, and visualizations (bar charts, line charts, and pie charts).
- `Hotel_Booking_Cancellation_Analysis_Report.docx` / `.pdf` – Final structured project report covering the Business Problem, Hypothesis, Assumptions, Research Questions, Analysis & Findings (with charts), Suggestions, and Conclusion.

## How to Run This Project?

1. Clone or download this repository.
2. Make sure the dataset file `hotel_bookings 2.csv` is placed inside a `Dataset/` folder in the project directory.
3. Install the required Python libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
5. Open `Data_Analysis_Hotel_Bookings_.ipynb` and run all cells from top to bottom.
6. Review the generated charts inline, and refer to the project report (PDF) for the full written analysis and recommendations.

## Final Recommendation

1. **Pricing strategy** – Since cancellation rates rise with price, hotels should review pricing for high-cancellation locations and offer targeted discounts to price-sensitive guests.
2. **Weekend/holiday discounts** – City Hotel, which has a higher cancellation ratio, should offer reasonable discounts on weekends and holidays to retain bookings.
3. **Seasonal campaigns** – Since January sees the highest cancellations and ADR loss, hotels should run targeted marketing or promotional campaigns ahead of this month.
4. **Service quality improvements** – Focus on improving service quality, particularly for guests from Portugal (the top source of cancellations), and strengthen relationships with Group and OTA channels, which show the highest cancellation propensity.
5. **Flexible booking policies** – Consider partially refundable booking options for high-ADR reservations to reduce the incentive to cancel for cheaper alternatives.

## Future Work

- Build a predictive machine learning model (e.g., logistic regression, random forest) to classify bookings as likely-to-cancel vs. likely-to-honor.
- Create an interactive Power BI / Tableau dashboard for real-time monitoring of cancellation trends.
- Incorporate additional features such as lead time, deposit type, and special requests into a deeper cancellation-driver analysis.
- Perform a cost-benefit analysis of the suggested pricing and discount strategies.

## Author & Contact

**Author:** Vishal
**Role:** Data Analyst (Aspiring)
**Contact:** Add your email / LinkedIn / GitHub profile link here
