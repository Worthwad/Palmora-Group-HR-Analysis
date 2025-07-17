# Palmora-Group-HR-Analysis

## Project Overview
Analysis of HR Data to uncover gender disparities, pay gaps and compliance issues of Palmora Group, a project assigned by The Incubator Hub.

## Structure
- `data/`: Raw and processed datasets [Employee Data](https://github.com/Worthwad/Palmora-Group-HR-Analysis/commit/032ef9a058f9e79a1fab9edf38e0d5ba3f4bfa38); [Bonus Rule](https://github.com/Worthwad/Palmora-Group-HR-Analysis/commit/032ef9a058f9e79a1fab9edf38e0d5ba3f4bfa38)
- `notebooks/`: Data cleaning and EDA [Cleaned Dataset](https://github.com/Worthwad/Palmora-Group-HR-Analysis/commit/b669fdff0b9b64447f73cd02e7d92cecd0d61dad)
- `dashboards/`: Power BI dashboard (.pbix) [Palmora Group Dashboard](https://github.com/Worthwad/Palmora-Group-HR-Analysis/commit/8ebe6e4edfdb624db0bc93b7ee50565f47860a4a)
- `reports/`: Exported visuals [Report](https://github.com/Worthwad/Palmora-Group-HR-Analysis/commit/7911bb8eafda670fc8a1a89650d4db84da5dace1)
- `docs/`: Additional documentation [Documentation Analysis](https://github.com/Worthwad/Palmora-Group-HR-Analysis/commit/2dd1112bfc6df8da11f6b9abc7d61103cc1441a7)

### Performed Calculated Columns 

#### Task 1 - Salary Band 
    
    Salary Band =
    
    SWITCH(

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

#### Task 2 - Below Minimum Wage 

    Below Minimum Wage = CALCULATE(COUNTROWS('emp_data1'), 'emp_data1'[Salary] < 90000),

#### Task 3 - Above Minimum Wage

    Above Minimum Wage = CALCULATE(COUNTROWS('emp_data1'), 'emp_data1'[Salary] > 90000),

#### Task 4 - Bonus Amount

    Bonus Amount = 'emp_data1'[Salary] * 'emp_data1'[Bonus%],

#### Task 5 - Total Pay

    Total Pay = 'emp_data1'[Salary] + 'emp_data1'[Bonus Amount],

## Instructions
1. Download the datasets from `data/`.
2. Open `Palmoria_HR.pbix` in Power BI Desktop.
3. Review the dashboard and insights.

## Tools & Technologies Used
-    Microsoft Excel: Data Structuring
-    Power Query – for data transformation and cleaning
-    Data Analysis Expressions (DAX): Metrics Calculation
-    Power BI Desktop: Data Modeling, Visualization and Interactivity

## Dashboard Screenshots
[Palmora-Group-HR-Analysis Dashboard](https://github.com/Worthwad/Palmora-Group-HR-Analysis/commit/8ebe6e4edfdb624db0bc93b7ee50565f47860a4a)


-    
