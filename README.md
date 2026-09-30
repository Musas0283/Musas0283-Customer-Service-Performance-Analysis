# Customer Service Data Analysis

## Project Overview

This project analyzes customer support ticket data using Python to evaluate customer service performance and identify actionable business insights.

The analysis focuses on ticket status distribution, customer satisfaction, ticket closure rates across priority levels, customer satisfaction across age groups, response-to-resolution times, and data-quality issues that may affect performance measurement.

## Business Questions

The analysis was designed to answer the following questions:

- What proportion of customer support tickets are Open, Closed, or Pending Customer Response?
- What is the overall level of customer satisfaction?
- How do ticket closure rates vary across priority levels?
- Does customer satisfaction vary across customer age groups?
- How long does it take to move from first response to resolution?
- Are there data-quality issues that could affect the reliability of the analysis?

## Tools Used

- **Python**
- **Pandas** — data cleaning, transformation, and analysis
- **Matplotlib** — data visualization
- **Jupyter Notebook** — analysis and documentation

## Data Preparation

Several data-preparation steps were performed before the analysis:

- Investigated missing values in Resolution, Time to Resolution, and Customer Satisfaction Rating.
- Determined that these missing values corresponded to Open or Pending Customer Response tickets and retained them because they reflected ticket status.
- Converted First Response Time and Time to Resolution into datetime format.
- Created customer age groups to support satisfaction analysis by age range.
- Investigated inconsistent response-to-resolution durations and documented them as a significant data-quality limitation.

## Key Findings

### Ticket Status

A total of **8,469 customer support tickets** were analyzed.

- **32.7%** of tickets were Closed.
- **67.3%** were Open or Pending Customer Response.

  <img width="600" height="600" alt="bar2" src="https://github.com/user-attachments/assets/6fdcfa10-1abb-46d7-9cd7-32fe83ea5050" />


The large proportion of unresolved tickets suggests that ticket age, resolution targets, and potential operational delays should be investigated.

### Customer Satisfaction

The average customer satisfaction rating among Closed tickets was approximately **2.99 out of 5**.
| Customer Satisfaction Rating | Number of Tickets | Percentage of Closed Tickets |
|-----------------------------:|------------------:|-----------------------------:|
| 1 | 553 | 19.97% |
| 2 | 549 | 19.83% |
| 3 | 580 | 20.95% |
| 4 | 543 | 19.61% |
| 5 | 544 | 19.65% |


Ratings were relatively evenly distributed across the five rating levels, with a rating of 3 being slightly more common.

### Ticket Closure Rate by Priority

Closure rates were relatively similar across all four priority levels:

- Critical: **34.10%**
- High: **33.81%**
- Medium: **31.66%**
- Low: **31.22%**

The relatively small differences suggest that further investigation is needed to determine whether higher-priority tickets are being handled according to expected service-level targets.

### Customer Satisfaction by Age Group

Average customer satisfaction was similar across all age groups.

Customers aged **31–40** had the highest average satisfaction rating at approximately **3.03/5**, while customers aged **51–60** had the lowest at approximately **2.94/5**.
<img width="640" height="480" alt="fig3" src="https://github.com/user-attachments/assets/51a4308a-8e76-4999-b923-53b97cb9602b" />


The small difference suggests that customer satisfaction did not vary substantially by age group in this dataset.

### Response-to-Resolution Time and Data Quality

A significant data-quality issue was identified.

Of the **2,769 Closed tickets**, **1,365 (49.3%)** had negative response-to-resolution durations, meaning the recorded resolution timestamp occurred before the first-response timestamp.
<img width="640" height="480" alt="pie1" src="https://github.com/user-attachments/assets/33ec6867-3bcf-4b12-b20a-faa3e95cf696" />


These records were retained because they contained other useful information, but invalid durations were excluded from response-to-resolution time calculations.

Among Closed tickets with valid positive durations, the average time between first response and recorded resolution was approximately **7 hours and 35 minutes**.

Because almost half of the Closed tickets contained inconsistent timestamp ordering, this metric should be interpreted cautiously.

## Business Recommendations

Based on the analysis:

- Investigate why 67.3% of tickets remain Open or Pending Customer Response.
- Review ticket age, workload distribution, staffing, and ticket assignment procedures.
- Investigate factors contributing to customer satisfaction, including recurring complaints and customer feedback.
- Review whether Critical and High-priority tickets are being handled according to established service-level targets.
- Improve timestamp recording and validation to ensure ticket creation, first-response, and resolution times are recorded accurately.
- Investigate common service issues across the entire customer base rather than focusing heavily on individual age groups.

## Project Files

- `Customer_Service_Analysis_Report.pdf` — Full project report, findings, visualizations, recommendations, and limitations.
- `Customer_service_analysis.ipynb` — Python analysis and data preparation.
- 'Customer_support_tickets.csv
- `README.md` — Project overview and summary.

## Conclusion

The analysis found that only 32.7% of customer support tickets were recorded as Closed, while closure rates were relatively similar across priority levels and customer satisfaction varied little across age groups.

The project also identified an important data-quality limitation: 49.3% of Closed tickets contained inconsistent response-to-resolution timestamps. Improving timestamp recording and validation would enable more reliable measurement of customer service performance.

## Skills Demonstrated

- Data Cleaning
- Exploratory Data Analysis (EDA)
- Data Quality Assessment
- Data Transformation
- Pandas
- Data Visualization
- Business Analysis
- Translating Data Findings into Business Recommendations
