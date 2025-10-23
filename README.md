# CRM Analytics Dashboard — Sales and Pipeline Performance

## Overview
This project presents a **CRM (Customer Relationship Management) analytics dashboard** built to evaluate how effectively a company’s sales process converts leads into paying customers.  
The analysis leverages **HubSpot CRM data** stored in **Google BigQuery** and visualized with **Looker Studio**.  

The dashboard provides executives, sales managers, and analysts with a clear view of **pipeline performance**, **revenue distribution**, and **data quality** across the company’s CRM system.

---

## Aim of the Project

The goal of this project is to analyze a company’s CRM data to uncover actionable insights into its sales performance and pipeline efficiency.
It aims to:

- Evaluate how effectively leads are converted into deals.

- Identify top-performing sales representatives and industries.

- Detect weak points in the sales funnel where deals often drop.

- Provide business leaders with a real-time view of revenue and performance.

Ultimately, the dashboard helps transform raw CRM data into strategic business intelligence for better decision-making.

---


## This dashboard and analysis are designed for:

- Sales Managers: to track sales reps’ performance and deal progress.

- Executives / Business Leaders: to monitor overall revenue trends and company growth.

- Marketing Teams: to align lead-generation efforts with high-performing industries.

- Data Analysts: to practice CRM analytics workflows involving SQL, BigQuery, and Looker Studio.

💡 It’s both a business reporting tool and a data analytics case study.

---

## Business Context
The company, is a **B2B technology firm** that provides cloud-based software and automation tools to other organizations.  
Its business relies on generating leads (contacts) from various industries, nurturing them into opportunities (deals), and managing those relationships through its CRM system.

The data represents:
- **Companies**: Client organizations the business interacts with.  
- **Contacts**: Individuals (decision-makers) within those companies.  
- **Deals**: Sales opportunities or transactions pursued by the sales representatives.

By analyzing these datasets together, the company aims to understand:
- Which industries and clients bring the highest revenue.  
- How efficiently leads move through the sales funnel.  
- Which sales representatives perform best.  
- Where deals most often get stuck or lost.  
- How complete and reliable the CRM data is.

---


## Data Modelling and Transformation

Before visualization, the three datasets — companies, contacts, and deals — were transformed and queried in **Big Query**.

Using SQL scripts, the data was joined across tables (company_id as the key) to create a unified view.

This process created a single analytical dataset (crm_analysis_view) used in Looker Studio for reporting. [Here](crm_analytics_view.txt) is the sql script used.

## Project Objectives
1. Evaluate the **health of the sales pipeline** across six stages.  
2. Measure **conversion and win rates** to identify sales efficiency.  
3. Analyze **revenue distribution** by industry, company, and sales owner.  
4. Highlight **data quality gaps** (missing emails, job titles, etc.) in the CRM.  
5. Provide executives with actionable insights to improve sales performance and forecasting.

---

## Data Structure

| Table | Description | Key Columns |
|--------|--------------|--------------|
| **Companies** | Information about all client organizations | `company_id`, `company_name`, `industry`, `country`, `annual_revenue` |
| **Contacts** | People associated with each company | `contact_id`, `first_name`, `last_name`, `email`, `job_title`, `company_id` |
| **Deals** | Active and closed sales opportunities | `deal_id`, `deal_name`, `company_id`, `industry`, `amount`, `stage`, `close_date`, `owner` |

---

## Tools & Technologies
- **Google BigQuery** → Used to store and transform the data (SQL-based analysis).  
- **Google Looker Studio** → Used to visualize and design the interactive dashboard.  
- **Excel** → For initial data validation and export checks.

---

## 📊 Dashboard Structure

### **Page 1 – Executive Summary**

![Images](Images/Executive%20Summary.png)


Provides a high-level view of company performance.
- KPIs: Total Revenue, Total Deals, Win Rate, Active Pipeline.  
- Pipeline Funnel by Stage.  
- Revenue Trend Over Time.  
- Top Sales Representatives.  
- Key Takeaways text box summarizing major insights.

### **Page 2 – Leads & Contacts**

![Images](Images/Leads%20and%20Contact%20Insights.png)


Focuses on contact and data quality analysis.
- Total Contacts and Industries.  
- Contact-to-Deal Conversion Rate.  
- Missing Email or Job Title Percentages.  
- Top Job Titles by Industry.  
- Interactive filters by Industry and Country.

### **Page 3 – Deals & Companies**

![Images](Images/Deals%20and%20Company%20Insights.png)


Deep-dives into revenue and deal breakdowns.
- Total Revenue by Industry and Owner.  
- Average Deal Size by Stage.  
- Top 10 Companies by Revenue.  
- Deals Distribution by Country.  
- KPI summary for closed-won vs closed-lost.

---

## 📈 Key Insights
- **Technology and Finance** industries contribute the largest share of total revenue.  
- Most deals drop off at the **Negotiation** stage, signaling a need to strengthen follow-up and pricing strategies.  
- **Alice Johnson** and **Michael Smith** show consistently high win rates across multiple clients.  
- The company’s overall **win rate is around 35%**, with significant room for improvement.  
- Around **20% of contacts** have incomplete information (missing emails or job titles), highlighting a need for CRM data enrichment.

---

## Live Dashboard

[Here](https://lookerstudio.google.com/reporting/004d9040-eebd-4547-8409-6a1affaf2933) is the live dashboard for the analysis
