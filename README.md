# Palmora-Group-HR-Analysis

## Project Overview
Analysis of HR data to uncover gender disparities, pay gaps, and compliance issues.

## Structure
- `data/`: Raw and processed datasets
- `notebooks/`: Data cleaning and EDA
- `dashboards/`: Power BI dashboard (.pbix)
- `reports/`: Exported visuals
- `docs/`: Additional documentation

### Perform the Pivot Tables & Calculated Columns by Using Excel:

#### Task                Calculation
Salary Band              SWITCH(
                            TRUE(),
                            'emp_data1'[Salary] <= 20000, "$10-$20",
                            'emp_data1'[Salary] <= 30000, "$20-$30",
                            'emp_data1'[Salary] <= 40000, "$30-$40",
                            'emp_data1'[Salary] <= 50000, "$40-$50",
                            'emp_data1'[Salary] <= 60000, "$50-$60",
                            'emp_data1'[Salary] <= 70000, "$60-$70",
                            'emp_data1'[Salary] <= 80000, "$70-$80",
                            'emp_data1'[Salary] <= 90000, "$80-$90",
                            'emp_data1'[Salary] <= 100000, "$90-$100",
                            "$100+"
                            )
BelowMinWage          CALCULATE(COUNTROWS('emp_data1'), 'emp_data1'[Salary] < 90000)
AboveMinWage          CALCULATE(COUNTROWS('emp_data1'), 'emp_data1'[Salary] > 90000)
Bonus Amount          'emp_data1'[Salary] * 'emp_data1'[Bonus%]
Total Pay             'emp_data1'[Salary] + 'emp_data1'[Bonus Amount]

## Instructions
1. Download the datasets from `data/`.
2. Open `Palmoria_HR.pbix` in Power BI Desktop.
3. Review the dashboard and insights.
