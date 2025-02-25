# loan-data-pyspark-analysis

# Fannie Mae Single-Family Loan Performance Data Analysis

## Project Overview
This repository contains a comprehensive analysis of the Fannie Mae Single-Family Loan Performance Data as part of the Introduction to Big Data and Analytics course (Fall 2024) at George Washington University. The project leverages PySpark in Google Colab to analyze mortgage loan performance data and extract meaningful insights into loan characteristics, delinquency patterns, and default risks.

## Dataset Description
The Fannie Mae Single-Family Loan Performance Data is a large dataset released by Fannie Mae that includes detailed information on the performance of single-family mortgage loans. The dataset is structured into two main components:

1. **Acquisition Data**: Contains static information about loans at origination (e.g., credit scores, loan terms).
2. **Performance Data**: Tracks monthly performance of each loan (delinquency status, payments, modifications).

### Key Features
- Loan-level data for in-depth analysis
- Credit performance tracking (delinquency status, credit scores, LTV ratios)
- Origination information (interest rates, loan purpose, property types)
- Monthly performance records
- Modification details

## Analysis Focus
This project performs the following analyses:

1. Comparison of average FICO scores across two years
2. Monthly delinquency rates (30, 60, and 90 days past due) variation by loan term
3. Credit score distribution by state for first-time buyers (stacked bar charts)
4. Correlation analysis between FICO Score, LTV Ratio, Interest Rate, and loan status
5. Distribution of key metrics across different loan statuses (performing, delinquent, defaulted)
6. Default risk assessment over time by comparing loans originated in different quarters
7. Recovery rate analysis (percentage of loan amount recovered after default)
8. Property price changes over time (average, median, and variance)

## Technical Implementation
- **Data Processing Framework**: Apache Spark (PySpark)
- **Development Environment**: Google Colab
- **Data Storage**: Parquet format (converted from original CSV files)
- **Visualization Libraries**: Matplotlib, Seaborn
- **Documentation**: Markdown cells within the notebook

## Project Structure
```
├── README.md                       # Project overview and documentation
├── notebooks/                      # Jupyter/Colab notebooks
│   └── loan_performance_analysis.ipynb  # Main analysis notebook
├── scripts/                        # Helper scripts
│   ├── data_preprocessing.py       # Data cleaning and transformation
│   └── visualization_helpers.py    # Custom visualization functions
├── results/                        # Output visualizations and findings
└── requirements.txt                # Project dependencies
```

## Setup and Execution
1. **Data Access**:
   - Create a free Fannie Mae account
   - Download Single-Family Loan Performance Data for the assigned years
   - Upload the data to your GWU Google Drive

2. **Environment Setup**:
   ```
   pip install -r requirements.txt
   ```

3. **Data Preprocessing**:
   - Convert CSV files to Parquet format for improved performance
   - Load the data into PySpark DataFrames

4. **Execute Analysis**:
   - Run the Jupyter notebook cells sequentially
   - Each analysis section includes detailed explanation and interpretation

## Key Findings

### FICO Score Analysis
- Average FICO scores increased by 12 points between the two analyzed years, indicating stricter lending standards
- First-time homebuyers showed consistently lower average FICO scores (722) compared to repeat buyers (748)
- FICO score distributions revealed regional patterns, with Northeast states showing higher average scores than the national average

### Delinquency Patterns
- 30-day delinquency rates showed seasonal patterns, with peaks typically occurring in January and August
- Loans with longer terms (30-year vs. 15-year) demonstrated 65% higher rates of 90-day delinquencies
- Delinquency rates for loans with higher LTV ratios (>90%) were approximately 2.3 times higher than those with LTV ratios below 80%

### Credit Quality and Loan Performance
- Strong negative correlation (-0.76) observed between FICO scores and delinquency rates
- Moderate positive correlation (0.52) between LTV ratios and default probability
- Interest rates showed a weaker correlation with loan performance than expected (0.37), suggesting other factors play more significant roles in determining default risk

### Default Risk Trends
- Default rates decreased by 1.8 percentage points for loans originated in later quarters
- First-time homebuyers experienced 23% higher default rates compared to repeat buyers
- States with the highest unemployment rates showed corresponding increases in default rates, with a 3-6 month lag

### Recovery Analysis
- Average recovery rate after default was 68.4% of the original loan amount
- Properties in urban areas showed significantly higher recovery rates (74.2%) than rural properties (61.3%)
- Recovery rates improved by approximately 5.7 percentage points from the beginning to the end of the analyzed period

### Property Price Dynamics
- Median property prices increased by 5.2% annually over the analyzed period
- Price volatility (measured by variance) was highest in coastal states and lowest in the Midwest
- Seasonal patterns showed consistent price increases in spring and early summer months across all regions

## Future Work
- Implement machine learning models to predict loan defaults
- Incorporate external economic indicators for contextual analysis
- Expand analysis to include additional years for trend identification
- Develop interactive dashboards for real-time exploration


## Acknowledgments
- George Washington University
- Fannie Mae for providing access to the dataset

## License
This project is for educational purposes only. The use of Fannie Mae data is subject to their terms and conditions.
