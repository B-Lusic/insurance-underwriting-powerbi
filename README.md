# Insurance Portfolio & Underwriting Risk Performance Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](#)
[![DAX](https://img.shields.io/badge/DAX-Data_Analysis_Expressions-blue?style=for-the-badge)](#)

[View Live Portfolio Write-Up & Dashboard](https://benlusic.wixsite.com/bensportfolio/post/insurance-portfolio-underwriting-risk-performance-dashboard-power-bi)

---

## 1. What business question did you answer?
Insurance carriers face ongoing pressure to balance premium growth against claims payout risk across policy lines, coverage types, and geographic regions. This project answers:
* How is profitability (Loss Ratio) distributed across different policy lines and state territories?
* Which policy cohorts and underwriting segments exhibit high loss frequency or severity exceeding target thresholds?
* How are written premiums performing against claims payouts over time, and where should underwriting guidelines be tightened or loosened?

---

## 2. Where did the data come from?
The dataset consists of insurance transaction records capturing policy issuances, coverage classifications, premiums earned, and settled/pending claims data.

---

## 3. Is the data real, public, synthetic, or modified?
**Modified & Synthetic.** The dataset combines realistic policy and claims structures modeled after standard property and casualty (P&C) insurance datasets, anonymized and scaled to reflect real-world underwriting operations.

---

## 4. How many records and what time period?
* **Total Policy Records:** ~10,000+ policy records across multiple lines of coverage.
* **Time Period Covered:** Multi-year historical portfolio transactions (2021 – 2024).

---

## 5. What tools did you use?
* **Power BI Desktop:** Star schema data modeling, interactive visual canvas design, and report publishing.
* **Power Query (M):** Data extraction, transformation, attribute typing, and null handling.
* **DAX (Data Analysis Expressions):** Key performance indicators (KPIs), time-intelligence metrics, loss ratios, and earned premium measures.
* **Markdown:** Documentation and data dictionary formatting.

---

## 6. What transformations did you perform?
1. **Schema Standardization:** Promoted headers, removed duplicate policy numbers, and established strict column data types (Currency, Date, Integer).
2. **Date Table Creation:** Generated a dedicated, contiguous `DimDate` dimension table in Power Query to support time-intelligence DAX functions.
3. **Null & Missing Value Handling:** Replaced missing claim amounts with `0` for active policies with zero recorded claims.
4. **Conditional Formatting Flags:** Created custom columns categorizing policies into risk tiers based on claims frequency and coverage limits.

---

## 7. How did you validate the results?
* **Aggregated Audit Controls:** Reconciled total earned premiums and aggregate claim counts against raw source summary tables.
* **Cross-Filtering Spot Checks:** Verified that dynamic slicers (State, Line of Business, Policy Term) accurately updated measures without record duplicating.
* **DAX Measure Reconciliation:** Audited DAX Loss Ratio measures against manually calculated Excel benchmarks to ensure exact decimal precision.

---

## 8. What did you find?
* **Regional Disparities:** Commercial property lines in specific high-risk coastal territories exhibited loss ratios consistently exceeding the 70% profitability benchmark.
* **Policy Tier Performance:** Lower-deductible policies drove disproportionate claims frequency compared to high-deductible tiers.
* **Portfolio Concentration:** A minority of high-severity claims accounted for over 60% of total loss expenditures across personal lines.

---

## 9. What decisions could follow?
* **Underwriting Guidelines:** Adjust deductible structures and pricing thresholds in underperforming territories to lower loss frequency.
* **Risk Appetite Adjustments:** Reallocate marketing and underwriting focus toward policy lines demonstrating loss ratios under 55%.
* **Claims Management:** Target high-severity coverage categories for expedited claims auditing and early intervention.

---

## 10. What are the limitations?
* Macroeconomic factors such as regional inflation in repair/replacement costs are not dynamically factored into historical claim costs.
* Data represents static snapshot snapshots rather than real-time API streaming feeds.

---

## 11. How can someone reproduce the work?
1. Clone this repository:
   ```bash
   git clone [https://github.com/your-username/insurance-underwriting-powerbi.git](https://github.com/your-username/insurance-underwriting-powerbi.git)
