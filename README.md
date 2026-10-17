# ABC–XYZ Inventory Classification & Pareto Analysis

## Overview

Inventory mein har product ko same level of attention dena efficient nahi hota. Kuch products sales value mein zyada contribute karte hain, jabki kuch ki demand zyada fluctuate karti hai.

This project uses inventory classification and data visualization techniques to analyze **1,000 SKUs across 5 product categories**. It combines ABC Analysis, XYZ Classification, and Pareto Analysis to understand product importance, demand stability, and revenue distribution.

## What This Project Covers

- Identifying high-value products using ABC Analysis.
- Measuring demand variability using XYZ Classification.
- Combining both classifications to create a nine-group inventory matrix.
- Analyzing revenue concentration across products and categories.
- Visualizing inventory patterns to support operational decision-making.

## Technology Stack

- **Python** – Data analysis
- **Pandas** – Data cleaning and manipulation
- **NumPy** – Numerical calculations
- **Matplotlib and Seaborn** – Data visualization
- **Jupyter Notebook** – Analysis and experimentation

## Analysis Methodology

### 1. ABC Analysis: Prioritizing by Value

ABC Analysis ranks products according to their contribution to total sales value and groups them using cumulative contribution thresholds.

- **A:** Highest-value products, approximately the first 80% of cumulative sales value.
- **B:** Products contributing to the next portion, up to approximately 95%.
- **C:** Remaining products with a lower individual contribution to total sales value.

The implemented classification contains:

| Class | Number of SKUs |
|---|---:|
| A | 87 |
| B | 170 |
| C | 743 |

### 2. XYZ Classification: Understanding Demand Stability

XYZ Classification groups products based on variations in their monthly demand. The Coefficient of Variation (CV) is used to compare demand variability relative to average demand.

$$
CV = \frac{\text{Standard Deviation}}{\text{Mean Demand}} \times 100
$$

The project uses these thresholds:

- **X:** CV below 10%
- **Y:** CV from 10% to 25%
- **Z:** CV above 25%

The resulting distribution is:

| Class | Number of SKUs |
|---|---:|
| X | 637 |
| Y | 216 |
| Z | 147 |

### 3. ABC–XYZ Matrix

The two classifications are combined to segment inventory according to both sales value and demand variability.

| Group | Interpretation |
|---|---|
| AX | High value, stable demand |
| AY | High value, moderately variable demand |
| AZ | High value, highly variable demand |
| BX | Medium value, stable demand |
| BY | Medium value, moderately variable demand |
| BZ | Medium value, highly variable demand |
| CX | Low value, stable demand |
| CY | Low value, moderately variable demand |
| CZ | Low value, highly variable demand |

The combined classification identifies **65 AX products**, while **458 products belong to the CX group**. These segments illustrate how inventory policies can be differentiated according to product value and demand patterns.

### 4. Pareto Analysis: Revenue Concentration

Pareto Analysis ranks products by sales value and examines cumulative revenue contribution. It helps identify whether a relatively small proportion of products accounts for a large share of total revenue.

The category-level analysis reports the following revenue distribution:

| Category | Revenue Contribution |
|---|---:|
| Grocery | 85.03% |
| Apparel | 9.27% |
| Electronics | 2.34% |
| Toys | 2.05% |
| Home & Kitchen | 1.32% |

Grocery accounts for the largest share of revenue in the analyzed dataset, making category-level concentration an important finding for further investigation.

## Visualizations

The analysis includes:

- Revenue and quantity by category
- Category-wise revenue contribution
- ABC and XYZ class distributions
- SKU distribution across ABC–XYZ groups
- Revenue Pareto chart by SKU
- Revenue Pareto chart by category
- ABC–XYZ classification heatmap
- Revenue by ABC–XYZ group
- Demand by ABC–XYZ group
- Top 10 revenue-generating SKUs

## Key Findings

- **1,000 SKUs** were analyzed across **5 product categories**.
- **87 SKUs** were classified as Class A based on cumulative sales value.
- **637 SKUs** were classified as Class X under the selected demand variability thresholds.
- **65 SKUs** fall into the AX group, combining high value with stable demand.
- **458 SKUs** fall into the CX group, combining lower value with stable demand.
- Grocery contributes **85.03%** of the reported category-level sales value.

## Business Relevance

The analysis can help inventory and supply chain teams identify where different control strategies may be appropriate.

- **High-value products:** Consider closer monitoring and tighter review procedures.
- **Stable-demand products:** Explore systematic replenishment schedules.
- **High-variability products:** Review forecasts and inventory requirements more frequently.
- **Low-value products:** Consider simpler control procedures where operationally appropriate.
- **Revenue concentration:** Investigate dependence on major product categories.

These are recommendations based on classification results, not measured improvements in cost, sales, or service levels.

## How to Run

### Requirements

- Python 3.x
- Jupyter Notebook or JupyterLab

### Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn jupyter
