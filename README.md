# 📞 Call Centre Performance & Analytics Dashboard

An interactive Business Intelligence project designed to track, analyze, and visualize key performance indicators (KPIs) and operational metrics for a high-volume customer service call center.

---

## 📋 Table of Contents
1. [Project Overview](#-project-overview)
2. [Business Problem & Objectives](#-business-problem--objectives)
3. [Key Performance Indicators (KPIs)](#-key-performance-indicators-kpis)
4. [Project Directory & File Structure](#-project-directory--file-structure)
5. [Dataset Schema & Attributes](#-dataset-schema--attributes)
6. [Data Preparation & ETL Process](#-data-preparation--etl-process)
7. [DAX Measures & Calculations](#-dax-measures--calculations)
8. [Dashboard Layout & Visualizations](#-dashboard-layout--visualizations)
9. [Key Analytical Insights](#-key-analytical-insights)
10. [Tools & Technologies Used](#-tools--technologies-used)
11. [How to Run This Project](#-how-to-run-this-project)
12. [Author & Acknowledgments](#-author--acknowledgments)

---

## 🎯 1. Project Overview
Modern call centers handle thousands of inquiries daily. Without centralized visibility, tracking operational bottlenecks, agent efficiency, and customer satisfaction is extremely difficult. This dashboard provides team leads and management with a real-time, data-driven analytical view to optimize staffing, reduce customer wait times, and improve overall service quality.

---

## ❓ 2. Business Problem & Objectives
The project addresses several core operational challenges:
* **Service Level Tracking:** What proportion of incoming calls are answered versus abandoned by customers?
* **Responsiveness Evaluation:** How quickly are agents responding to customer queues?
* **Customer Satisfaction:** What is the average customer satisfaction score post-interaction, and how does it correlate with wait times?
* **Agent Benchmarking:** Which agents maintain high issue resolution rates while keeping handle times efficient?

---

## 📊 3. Key Performance Indicators (KPIs)
The dashboard tracks the following critical metrics:
* **Total Calls:** Total volume of incoming calls received by the center.
* **Answered Calls:** Total calls successfully picked up by agents.
* **Abandoned Calls:** Calls dropped or disconnected by customers before reaching an agent.
* **Resolution Rate:** Percentage of customer issues successfully resolved during the call.
* **Average Speed of Answer (ASA):** The average duration (in seconds) a customer waits in queue before connection.
* **Average Handle Time (AHT):** The average duration spent by an agent handling a call.
* **Customer Satisfaction (CSAT):** Average feedback score provided by customers (typically on a 1–5 scale).

---

## 🗂️ 4. Project Directory & File Structure
```text
Call-Centre-Dashboard/
│
├── Data/                   # Raw and cleaned dataset files (CSV / Excel)
├── Dashboard/              # Power BI (.pbix) or Excel workbook files
├── Screenshots/            # Visual previews of the dashboard views
└── README.md               # Comprehensive project documentation

```

---

## 📂 5. Dataset Schema & Attributes

The dataset contains historical logs of customer service interactions with the following key attributes:

* `Call ID`: Unique alphanumeric identifier for each interaction.
* `Agent`: Full name of the customer support agent handling the call.
* `Date & Time`: Timestamp of when the call entered the system.
* `Topic`: Primary classification of the customer inquiry (e.g., Billing, Technical Support, Streaming, Account Management).
* `Answered (Y/N)`: Binary flag indicating if the call was answered.
* `Resolved (Y/N)`: Binary flag indicating if the customer's issue was solved.
* `Speed of Answer (seconds)`: Wait time before connection.
* `Satisfaction Rating`: Numerical score (1 to 5) evaluating customer satisfaction.

---

## 🛠️ 6. Data Preparation & ETL Process

Before building visualizations, the data underwent a structured ETL (Extract, Transform, Load) procedure:

1. **Data Cleaning:** Checked and handled missing values, standardized text inputs across agent names and topics, and ensured valid numerical boundaries for ratings and seconds.
2. **Feature Engineering:** Extracted date parts (Month, Day Name, Hour) from timestamps to enable time-series analysis and peak-hour identification.

---

## 📐 7. DAX Measures & Calculations

Advanced data analysis expressions (DAX) used to power dynamic dashboard filters and aggregations include:

* **Total Calls Answered:**
```dax
Total Calls Answered = CALCULATE(COUNTA('Dataset'[Call ID]), 'Dataset'[Answered (Y/N)] = "Yes")

```


* **Total Calls Abandoned:**
```dax
Total Calls Abandoned = CALCULATE(COUNTA('Dataset'[Call ID]), 'Dataset'[Answered (Y/N)] = "No")

```


* **Average Speed of Answer (ASA):**
```dax
Avg Speed of Answer = AVERAGE('Dataset'[Speed of answer in seconds])

```


* **Overall Resolution Rate:**
```dax
Resolution Rate = DIVIDE(
    CALCULATE(COUNTA('Dataset'[Call ID]), 'Dataset'[Resolved (Y/N)] = "Yes"), 
    COUNTA('Dataset'[Call ID]), 
    0
)

```


* **Customer Satisfaction (CSAT):**
```dax
Average CSAT = AVERAGE('Dataset'[Satisfaction rating])

```



---

## 📈 8. Dashboard Layout & Visualizations

The dashboard is meticulously laid out to guide stakeholders from macro-level performance down to micro-level agent metrics:

1. **KPI Banner Cards:** Instant summary view showcasing Total Calls, Answer Rate %, ASA, and Average CSAT.
2. **Trend & Volume Analysis:** Line and area charts visualizing call traffic distribution across hours of the day and days of the week.
3. **Category Breakdown:** Donut charts illustrating the distribution of call topics to highlight common customer pain points.
4. **Agent Performance Matrix:** Detailed breakdown comparing agent efficiency, total call volumes handled, and resolution success rates.

---

## 💡 9. Key Analytical Insights

* **Peak Load Windows:** Call volumes spike consistently during specific midday hours, pointing to windows where staffing density needs adjustment.
* **Wait Time Impact:** Customer satisfaction scores drop noticeably when the Average Speed of Answer exceeds specific threshold seconds.
* **Issue Distribution:** Technical Support and Billing inquiries account for the vast majority of incoming call volume.

---

## 🧰 10. Tools & Technologies Used

* **Data Visualization & BI:** Microsoft Power BI / Tableau / Excel
* **Data Processing:** Power Query, SQL, Python (Pandas for data validation)
* **Version Control:** Git & GitHub

---

## 🚀 11. How to Run This Project

1. Clone the repository to your local machine:
```bash
git clone [https://github.com/Jabivulla369/Call-Centre-Dashboard.git](https://github.com/Jabivulla369/Call-Centre-Dashboard.git)

```


2. Navigate to the project directory.
3. Open the dataset file inside the `Data/` folder or open the Power BI/Excel workbook file directly in your preferred analytics tool.
4. Explore the interactive filters, slicers, and DAX calculations.

---

## 👤 12. Author & Acknowledgments

* **Shaik Mohammad Ismael Jabivulla**
* [GitHub Profile](https://github.com/Jabivulla369)


<img width="1410" height="775" alt="image" src="https://github.com/user-attachments/assets/8596828a-77a6-4f0b-8bf1-3b1efd6c3ac7" />
<img width="1405" height="776" alt="image" src="https://github.com/user-attachments/assets/9112d689-5bf6-43be-9d42-2dc060f5d6ab" />

