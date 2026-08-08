# Churn-and-Retention-Analysis-in-a-Subscription-Model

A data analysis project performing customer retention tracking, churn rate evaluation, and demographic segmentation on subscription-based user data using Python, Pandas, Matplotlib, and Seaborn.

---

## Project Overview

This repository analyzes user activity and subscription lifecycle data to evaluate customer retention and compute churn rates across different geographic locations. The analysis merges user profile data with recurring subscription transaction logs to determine each customer's latest status (Active vs. Churned).

> **Note on Data Source:** All datasets used in this project (`users_data.csv` and `subscriptions_data.csv`) are **synthetically generated using Python**. They do not represent real individuals, active commercial accounts, or proprietary business data from any company.

### Key Findings & Insights
* **Overall Customer Churn Rate:** **44.00%** (out of 100 total customers, 56 are Active and 44 have Churned).
* **Geographic Variations:**
  * **Highest Churn Rates:** Denmark (66.67%), Argentina (62.50%), Italy (62.50%), Spain (62.50%), and Portugal (61.54%).
  * **Lowest Churn Rates / Best Retention:** Germany (16.67%), Norway (23.08%), France (25.00%), and Poland (25.00%).


## Data Schema

### 1. `users_data.csv`
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `customer_id` | Integer | Unique identifier for each user |
| `signup_date` | Date (`YYYY-MM-DD`) | Account creation date |
| `country` | String | User's country of residence |
| `age` | Integer | Age of the user |

### 2. `subscriptions_data.csv`
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `subscription_id` | Integer | Unique transaction / billing event ID |
| `customer_id` | Integer | Associated customer identifier |
| `payment_date` | Date (`YYYY-MM-DD`) | Date of payment or status update |
| `status` | String | Subscription state (`Active` or `Churned`) |

---

## Key Analysis Workflow

1. **Data Ingestion & Merging:**
   * Load customer demographics and subscription logs.
   * Perform a left join on `customer_id` to attach demographic context to each transaction.

2. **Latest Status Identification:**
   * Sort records by `customer_id` and `payment_date`.
   * Group by `customer_id` to extract the most recent payment record for each user.

3. **Churn Metrics Computation:**
   * Calculate overall churn rate percentage across the active user base.
   * Group users by `country` and `status` to compute country-level retention metrics.

4. **Data Visualization:**
   * Generate grouped bar charts comparing `Active` vs. `Churned` user counts per country using Seaborn and Matplotlib.

---

## Setup & Usage

### Prerequisites
* Python 3.8+
* Jupyter Notebook / JupyterLab / Google Colab

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/vpersona/Churn-and-Retention-Analysis-in-a-Subscription-Model.git
   cd Churn-and-Retention-Analysis-in-a-Subscription-Model
   ```

2. **Install required dependencies:**
   ```bash
   pip install pandas matplotlib seaborn
   ```

3. **Run the analysis:**
   Launch `churn_analysis.ipynb` in Jupyter Notebook or Google Colab and execute all cells.


