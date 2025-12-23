# Australian Internet Vacancy Trends Analysis

This folder contains notebooks and resources used to analyze occupational vacancy trends in Australia using the Internet Vacancy Index (IVI) data.

## Project Overview
The primary goal of this analysis is to visualize how job vacancies across different industries (categorized by ANZSCO codes) have fluctuated over time, specifically looking at the impact of the the rise of Generative AI.

## Contents
* `vacancy_trends_australia.ipynb`: The main analysis script containing data cleaning, aggregation, and visualization logic.
* `data/`: Contains the `internet_vacancies.csv` source file.

## Methodology

### 1. Data Cleaning
The raw IVI data often contains numeric values formatted as strings with commas (e.g., "1,200"). The notebook includes a cleaning pipeline that:
* Removes non-numeric characters (commas).
* Converts date-labeled columns into proper integer types for calculation.

### 2. National Aggregation
Since the source data is segmented by state and territory, the notebook aggregates these figures to provide a **National Total** for each ANZSCO occupation code. It also maintains a mapping of ANZSCO codes to human-readable titles.

### 3. Trend Visualization
A custom plotting function `plot_vacancies(code)` is provided. It generates line charts with specific timeline markers:
* **COVID-19 (March 2020):** To observe the initial dip and subsequent recovery in hiring.
* **ChatGPT/GPT-3.5 Launch (November 2022):** To monitor potential shifts in tech or administrative vacancy trends following the AI boom.

## How to Use
1.  **Install Dependencies:** Ensure you have `pandas` and `matplotlib` installed.
    ```bash
    pip install pandas matplotlib
    ```
2.  **Run the Notebook:** Open `vacancy_trends_australia.ipynb` in Jupyter or VS Code.
3.  **Compare Occupations:** Use the `plot_vacancies` function to compare different codes:
    ```python
    # Example: Plot ICT Professionals (Code 26)
    plot_vacancies("26") 
    
    # Example: Compare ICT Professionals with Business Professionals (Code 22)
    plot_vacancies("26", code_alt="22") 
    ```
    
## Example Visualizations

### 1. ICT professionals
![ICT-professionals](outputs/images/ICT%20Professionals.png)

### 2. ICT professionals vs Business, Finance and Human Resource Professionals
![ICT Professionals-vs-Business](outputs/images/ICT%20Professionals%20vs%20Business,%20Finance%20and%20Human%20Resource%20Professionals.png)

## Data Source
The data used in this notebook is based on the **Internet Vacancy Index (IVI)**, which is the main indicator of vacancies used by the Australian Government for labor market analysis.
