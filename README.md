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
* California Statewide Special Election (<https://www.sos.ca.gov/elections/upcoming-elections/statewide-special-nov-4-2025>): official website for the election from the CA Secretary of State.
* Statewide Database Precinct Data (<https://statewidedatabase.org/d20/g24.html>): source of precinct-level data from the 2024 General Election.
* 2024 Election Geographic Data (<https://statewidedatabase.org/d20/g24_geo_conv.html>): source of shapefiles for precinct maps from 2024 General Election.
* Proposed Congressional Map (<https://aelc.assembly.ca.gov/proposed-congressional-map>): source of shapefiles for district map proposed in AB 604.


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

### 5. Interactive Analytics Dashboard

<img width="743" height="782" alt="Screenshot 2026-01-08 at 17 08 06" src="https://github.com/user-attachments/assets/56b82541-2cf8-4439-b747-287a73a620c1" />

* **Architected** an interactive decision-support tool using **Quarto** and the **Brite theme** to visualize redistricting impacts.
* **Deployed** automated Value Boxes to track real-time shifts in **Mean-Median Difference** and **Efficiency Gap**.
* **Engineered** dynamic choropleth maps using `sf` to translate complex spatial data into intuitive geographic insights.
* **Implemented** a side-by-side comparative layout to contrast Democrats' House Share between 2024 and AB 604 maps.
* **Optimized** performance by pre-processing large geographic shapefiles with `rmapshaper` for seamless browser rendering.


## Technical Stack
* **Language:** R
* **Libraries:** `tidyverse`, `dplyr`, `stringr`, `readr`, `janitor`
* **Format:** Quarto / Markdown

## Academic Integrity & Honor Code
**Note on Code Availability:**
In accordance with the **UC Berkeley Honor Code** and to maintain academic integrity for the course (Lab 4 Project), the source code for data cleaning and map generation is **not publicly available** in this repository to prevent plagiarism. 

## Contact
- **Author**: Hex Wu
- **Email**: [hex@berkeley.edu](mailto:hex@berkeley.edu)
- **Portfolio**: [hexVerse Portfolio](https://hexverse.framer.media)
