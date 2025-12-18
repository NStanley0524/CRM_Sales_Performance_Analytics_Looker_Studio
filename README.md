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

## Key Insights
- **Technology and Finance** industries contribute the largest share of total revenue.  
- Most deals drop off at the **Negotiation** stage, signaling a need to strengthen follow-up and pricing strategies.  
- **Alice Johnson** and **Michael Smith** show consistently high win rates across multiple clients.  
- The company’s overall **win rate is around 35%**, with significant room for improvement.  
- Around **20% of contacts** have incomplete information (missing emails or job titles), highlighting a need for CRM data enrichment.

---

## Business Recommendations

## 1 Strengthen the Negotiation Stage to Reduce Deal Drop-Off

### Problem Identified  
Most deals are lost at the **Negotiation** stage, making it the weakest point in the sales funnel.

### Action  
Standardize and reinforce the negotiation process.

### How to Implement  
- Create a **Negotiation Playbook** covering:
  - Pricing flexibility rules (discount thresholds, approval limits)
  - Common objections and approved response scripts
  - Deal acceleration tactics (limited-time incentives, bundled offers)
- Require sales reps to log **loss reasons** specifically for negotiation-stage failures in HubSpot
- Introduce **weekly pipeline review sessions** focused on deals stuck in Negotiation for more than 14 days

### Owner  
Sales Manager / Head of Sales

### Expected Impact  
- Reduced deal stagnation  
- Higher close rates at the most critical funnel stage  
- Improved revenue predictability  

---

## 2 Replicate Top Sales Rep Strategies Across the Team

### Problem Identified  
**Alice Johnson** and **Michael Smith** consistently outperform others in win rate and revenue.

### Action  
Turn top performers into internal benchmarks and mentors.

### How to Implement  
- Analyze their historical deals to identify:
  - Average deal cycle length  
  - Discount usage patterns  
  - Industries with highest close rates  
- Document these findings into a **Best Practices Sales Guide**
- Assign them as **mentors** to lower-performing reps for deal reviews
- Use their performance metrics as **team benchmarks**, not just individual KPIs

### Owner  
Sales Leadership / Revenue Operations

### Expected Impact  
- Reduced performance gap across reps  
- Faster onboarding for new sales hires  
- Overall win rate uplift without additional lead spend  

---

## 3 Focus Marketing Spend on High-Revenue Industries

### Problem Identified  
**Technology and Finance** generate the highest share of total revenue.

### Action  
Prioritize lead generation and campaigns in these industries.

### How to Implement  
- Segment CRM leads by industry and calculate **cost per closed deal**
- Reallocate marketing budget toward:
  - Industry-specific landing pages  
  - Webinars or case studies tailored to Tech and Finance  
- Create **industry-specific sales scripts** aligned with known pain points

### Owner  
Marketing Manager / Sales Manager

### Expected Impact  
- Higher quality leads  
- Improved lead-to-deal conversion  
- Increased ROI on marketing spend  

---

## 4 Improve CRM Data Quality Through Mandatory Field Enforcement

### Problem Identified  
Approximately **20% of contacts** have missing emails or job titles.

### Action  
Enforce CRM data completeness at the point of entry.

### How to Implement  
- Make **email and job title mandatory fields** in HubSpot for new contacts
- Use third-party enrichment tools (e.g., Clearbit, Apollo) to backfill missing data
- Add a **data completeness KPI** to the dashboard, tracked monthly
- Assign data accuracy responsibility to sales reps during lead qualification

### Owner  
CRM Administrator / Revenue Operations

### Expected Impact  
- Better lead qualification  
- More accurate reporting and analytics  
- Improved personalization and outreach performance  

---

## 5 Introduce Stage-Based Sales SLAs to Speed Up the Funnel

### Problem Identified  
Deals stall across multiple pipeline stages, slowing revenue realization.

### Action  
Define and enforce **Service Level Agreements (SLAs)** for each pipeline stage.

### How to Implement  
- Set maximum allowed time per stage:
  - Qualification: ≤ 5 days  
  - Proposal: ≤ 7 days  
  - Negotiation: ≤ 14 days  
- Create automated CRM alerts when deals exceed SLA thresholds
- Include SLA adherence in sales performance reviews

### Owner  
Sales Operations / Sales Managers

### Expected Impact  
- Faster deal cycles  
- Reduced deal leakage  
- More predictable revenue outcomes  

---

## 6 Improve Revenue Forecasting Using Win Rate and Deal Size

### Problem Identified  
Revenue forecasting relies too heavily on raw pipeline totals.

### Action  
Adopt a **weighted pipeline forecasting model**.

### How to Implement  
- Calculate Expected Revenue using:
  - `Expected Revenue = Deal Amount × Historical Win Rate (by stage)`
- Add weighted forecasts to the executive dashboard
- Use weighted metrics for quarterly and annual planning

### Owner  
Finance Team / Revenue Operations

### Expected Impact  
- More accurate revenue forecasts  
- Fewer end-of-quarter surprises  
- Better financial planning and decision-making  

---

## 7 Align Sales and Marketing Using Contact-to-Deal Conversion Metrics

### Problem Identified  
Not all contacts convert into deals at the same efficiency.

### Action  
Optimize lead quality instead of lead quantity.

### How to Implement  
- Track **Contact-to-Deal Conversion Rate by Industry**
- Review this metric jointly in monthly sales–marketing alignment meetings
- Adjust lead scoring models using high-conversion attributes (job title, industry, company size)

### Owner  
Sales & Marketing Leadership

### Expected Impact  
- Higher-quality leads entering the pipeline  
- Improved sales productivity  
- Stronger alignment between sales and marketing teams  

---


## Live Dashboard

[Here](https://lookerstudio.google.com/reporting/004d9040-eebd-4547-8409-6a1affaf2933) is the live dashboard for the analysis
