# Quantium Retail Analytics: Chip Category & Trial Evaluation

## Project Overview
This repository contains my completed Quantium Data Analytics Job Simulation, undertaken through Forage.

The simulation involved a retail analytics case focused on understanding customer purchasing behaviour and evaluating the commercial impact of a new in-store chip layout trial. The analysis was prepared for Julia, Category Manager for Chips, with the objective of translating transaction and customer data into actionable commercial insights.

The project was completed in two primary phases:

* **Task 1: Customer Purchasing Behaviour Analysis**: Analysed customer segments, lifestages, brand performance, and pack-size preferences to identify opportunities for category growth.
* **Task 2: Trial Store Performance Evaluation**: Identified suitable control stores, evaluated the performance of trial stores over a three-month period, and assessed whether observed sales uplifts were statistically significant.

> **Dataset note:** The analysis used datasets provided as part of the Quantium Data Analytics Job Simulation. The original datasets are not included in this repository.

---

## Technical Stack & Libraries
* **Language:** Python 3
* **Data Manipulation:** `pandas`, `numpy`
* **Statistical Testing:** `scipy.stats` (Pearson correlation, paired t-tests, and independent t-tests)
* **Data Visualization:** `matplotlib`, `seaborn`
* **Environment:** Jupyter Notebook

---

## Dataset Overview
The analysis covered transaction and customer purchasing data spanning July 2018 to June 2019.

The datasets provided for the simulation included:
* **Transaction data:** 264,834 transactions across approximately 264–272 stores, containing transaction dates, store numbers, customer loyalty IDs, product descriptions, quantities, and sales values.
* **Purchase behaviour data:** Customer loyalty-card mappings containing lifestage classifications and premium/budget purchasing tiers.

---

## Phase 1: Customer Purchasing Behaviour

### Data Cleaning & Preprocessing
The transaction data was prepared for analysis through several preprocessing steps:

1. **Date conversion:** Converted Excel serial dates into standard datetime values covering 1 July 2018 to 30 June 2019.
2. **Non-chip filtering:** Identified and removed 18,094 non-chip salsa/dip records, including products such as Old El Paso and Doritos Salsa.
3. **Outlier removal:** Removed artificial bulk transactions associated with customer card `226000`, which contained two separate purchases of 200 bags of chips each.
4. **Feature engineering:** Extracted pack size in grams and standardized brand identifiers from product descriptions.

### Key Customer & Category Insights

#### Customer Segments
* **Budget Older Families** generated the highest overall sales at approximately $156,864 and the highest annual spend per customer at approximately $34.02.
* **Mainstream Young Singles/Couples** represented the largest customer base, with 7,917 unique buyers, generating approximately $147,582 in total sales.
* **Mainstream Retirees** represented another significant segment, generating approximately $145,169 across 6,358 buyers.

#### Brand & Pack Performance
* **Kettle**, **Smiths**, and **Doritos** accounted for the majority of category revenue.
* **175g** was the most popular pack size across all customer tiers.
* **Budget shoppers** showed a stronger preference for larger pack sizes, particularly **330g+** packs.

#### Seasonality
* Sales showed a pronounced peak in **December**, indicating increased chip purchasing activity ahead of the holiday period.

---

## Phase 2: Trial Store Evaluation

### Trial Design
The second phase evaluated the commercial performance of three stores that participated in a new chip-layout trial.

* **Pre-trial period:** July 2018 – January 2019 (7 months)
* **Trial period:** February 2019 – April 2019 (3 months)
* **Trial stores:** Store 77, Store 86, and Store 88

The objective was to compare each trial store against a suitably matched control store and determine whether the new layout was associated with improved performance.

### Control Store Matching Methodology
Control stores were selected using pre-trial performance across three measures:
* Total sales
* Customer counts
* Transactions per customer

A composite similarity score was calculated using Pearson correlation and magnitude distance:

$$\text{Composite Score} = 0.5 \times \text{Pearson Correlation} + 0.5 \times \text{Magnitude Distance Score}$$

The candidate control store with the lowest cumulative rank across the three metrics was selected for each trial store.

#### Selected Control Stores
| Trial Store | Control Store |
| :--- | :--- |
| **Store 77** | Store 233 |
| **Store 86** | Store 155 |
| **Store 88** | Store 125 |

### Trial Performance & Uplift
Control-store metrics were scaled to the pre-trial period, and 95% confidence intervals were used to assess monthly deviations in trial-store performance.

| Trial Store | Control Store | Sales Lift | Customer Lift | Transactions/Customer Lift | Main Driver |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Store 77** | Store 233 | +26.15% | +23.07% | -2.03% | Customer Acquisition |
| **Store 86** | Store 155 | +13.15% | +13.54% | +0.66% | Customer Acquisition |
| **Store 88** | Store 125 | +12.24% | +10.42% | +2.77% | Acquisition + Engagement |

The results showed positive directional sales uplifts across all three trial stores, ranging from approximately 12% to 26%.

### Statistical Significance
* Although all three trial stores showed positive directional sales uplifts, **none reached statistical significance at the 5% level ($p > 0.05$)** based on the paired t-tests.
* This means the observed uplift should be interpreted as a **promising commercial signal** rather than conclusive evidence of a causal effect.
* A key limitation was the relatively short three-month trial period ($n = 3$), which provides limited statistical power for detecting sustained effects.

---

## Recommendations & Commercial Action Plan

Based on the customer analysis and trial-store evaluation, the following actions were recommended:

1. **Phased Layout Rollout & Continued Monitoring**
   * Pilot a phased rollout in stores with customer profiles similar to **Store 77**, which recorded the strongest directional uplift.
   * For **Stores 86 and 88**, extend performance tracking and continue monitoring post-launch results to determine whether the observed uplift is sustained over a longer period.

2. **Shelf Space & Pack Management**
   * Prioritize primary shelf space for high-performing brands, particularly **Kettle, Smiths, and Doritos**.
   * Maintain strong availability and shelf depth for **175g** packs.
   * Consider targeted promotions around **330g+** packs for **Budget shoppers**.

3. **Targeted Customer Segment Campaigns**
   * Develop multi-pack and family-size offers targeted toward **Older Families** and **Retirees**, particularly given the strong spending contribution observed from these segments.

4. **Seasonal Inventory Planning**
   * Prepare inventory and promotional activity ahead of the **December** sales peak, including November stock planning and end-of-aisle promotional displays.

---

## Key Takeaways
* High-value customer segments can be identified through lifestage and purchasing-tier analysis.
* Brand and pack-size preferences provide opportunities for targeted shelf and promotional strategies.
* Matched control stores can be used to evaluate the performance of store-level interventions.
* Positive uplift does not necessarily imply statistical significance; trial duration and statistical power must be considered when interpreting experimental results.
* Commercial recommendations should balance observed performance with the strength and limitations of the underlying evidence.

---

## Project Deliverables
This repository contains the three presentation/report PDFs produced during the simulation:
* **Task 1**: Customer Purchasing Behaviour Analysis
* **Task 2**: Trial Store Performance Evaluation
* **Final Presentation**: Commercial Recommendations

> *The repository intentionally does not include the datasets used during the simulation.*

---

## Author & Project Information
* **Prepared by:** Fortune Casmir Mosha
* **Simulation:** Quantium Data Analytics Job Simulation
* **Platform:** Forage
* **Presented to:** Julia, Category Manager — Chips
* **Completed:** August 11, 2026
