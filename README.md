# California Redistricting Analysis: Quantifying the Impact of AB 604 on Partisan Bias

## Project Overview
This project investigates the potential shifts in California's political landscape following the proposed adoption of the **AB 604** congressional district map. By leveraging granular precinct-level data from the 2024 General Election, I developed a custom data pipeline to simulate how election outcomes would change under the 2025 proposed boundaries. 

The core objective was to determine the fairness of the legislative map using industry-standard metrics, specifically analyzing whether redistricting mitigates or exacerbates partisan skew.

## Research Questions
* **Primary Objective:** Analyze whether the adoption of the AB 604 district map leads to a quantifiable increase in partisan advantage relative to the 2024 status quo.
* **Impact Assessment:** Measure the magnitude of the shift in representative fairness using the Efficiency Gap and Mean-Median Score.

## Data Infrastructure
The analysis integrates multiple high-fidelity datasets to ensure geographic and statistical accuracy:
* **2024 General Election Results:** Precinct-level Statement of Vote (SOV) data.
* **Geographic Data:** Shapefiles for the 2024 precincts and the proposed AB 604 district boundaries.
* **Candidate Data:** District-level candidate records for the 2024 election cycle.

## Methodology
The project follows a rigorous four-stage analytical framework:

### 1. Data Cleaning & Normalization
* Processed raw datasets to handle non-standard characters, comma-delimited strings, and missing values.
* Implemented regex-based filtering to isolate House (CNG) Republican and Democratic vote totals from broader election results.
* Performed uniqueness validation and type-checking across 2,000+ precincts to ensure 100% data integrity.

### 2. Spatial Re-allocation (Pro-rata Weighting)
* Engineered a sophisticated spatial join logic to map 2024 precincts to 2025 districts.
* Applied a pro-rata population weighting method to accurately distribute votes from precincts split across new district lines, ensuring statistical precision.

### 3. Quantitative Metric Calculation
I utilized two primary metrics to evaluate gerrymandering:
* **Efficiency Gap (EG):** Quantifies the difference in "wasted votes" between parties to detect systemic bias.
* **Mean-Median Score:** Assesses the difference between average vote share and the median district's vote share to identify partisan skew.

### 4. Exploratory Data Analysis (EDA)
* Identified congressional districts with the narrowest margins and investigated turnout variance across precincts.
* Analyzed "blowout" precincts to understand the depth of partisan concentration.

## Key Insights
* **Partisan Bias Reduction:** The analysis revealed a significant drop in the Efficiency Gap from **0.283** (current 2024 map) to **0.179** (proposed AB 604 map).
* **Fairness Implications:** The decrease in the Efficiency Gap suggests that the AB 604 plan would lead to a more representative and competitive electoral environment, reducing wasted votes by approximately 36.7%.
* **Repeatable Pipeline:** Successfully established a robust method for aligning historical voting data with future geographic boundaries.

## Technical Stack
* **Language:** R
* **Libraries:** `tidyverse`, `dplyr`, `stringr`, `readr`, `janitor`
* **Format:** Quarto / Markdown

---
## ⚠️ Copyright and Intellectual Property Notice
**All rights reserved.**
The source code, data processing logic, and analytical methodologies contained in this repository are the sole intellectual property of **Hex Wu**. 
* **Strict Prohibition:** Under no circumstances may any part of this code or research be copied, redistributed, adapted, or used for any purpose (including academic, commercial, or personal) without explicit written permission from the author.
* **Integrity Warning:** This repository is for portfolio demonstration purposes only. Any unauthorized use or plagiarism of this work will be pursued to the fullest extent of institutional and legal policies.
