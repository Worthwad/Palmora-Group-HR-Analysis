**Data Cleaning in Power Query Editor**

\-	Click Transform Data.

\-	Remove rows where:

&nbsp;		Salary is blank or null → Salary != null

&nbsp;		Department is NULL → Department != null



&nbsp;		Steps in Power Query to Filter Out NULL Departments

&nbsp;		1.	Open Power Query Editor:

&nbsp;			o	In Power BI, go to the Home tab.

&nbsp;			o	Click on Transform Data → this opens Power Query Editor.

&nbsp;		2.	Locate the Department column:

&nbsp;			o	Scroll to the column named Department.

&nbsp;		3.	Filter Out NULL Values:

&nbsp;			o	Click the small dropdown arrow on the Department column header.

&nbsp;			o	Uncheck (null) from the filter list.

&nbsp;			o	Click OK.



\-	Replace blank or null values in Gender with "Undisclosed".

\-	Apply numeric format to the Salary column.





**Import Bonus Rules Table**

Load the second dataset (Bonus Rules).

This have two columns: Rating and Bonus%.



**Salary Band Analysis**



Create Salary Band Column

In Power Query or DAX:



Salary Band = 

SWITCH(

&nbsp;   TRUE(),

&nbsp;   'emp\_data1'\[Salary] <= 20000, "$10-$20",

&nbsp;   'emp\_data1'\[Salary] <= 30000, "$20-$30",

&nbsp;   'emp\_data1'\[Salary] <= 40000, "$30-$40",

&nbsp;   'emp\_data1'\[Salary] <= 50000, "$40-$50",

&nbsp;   'emp\_data1'\[Salary] <= 60000, "$50-$60",

&nbsp;   'emp\_data1'\[Salary] <= 70000, "$60-$70",

&nbsp;   'emp\_data1'\[Salary] <= 80000, "$70-$80",

&nbsp;   'emp\_data1'\[Salary] <= 90000, "$80-$90",

&nbsp;   'emp\_data1'\[Salary] <= 100000, "$90-$100",

&nbsp;   "$100+"

)





**Minimum Wage \& Above Minimum Wage Check**



BelowMinWage =

CALCULATE(COUNTROWS('emp\_data1'), 'emp\_data1'\[Salary] < 90000)



AboveMinWage =

CALCULATE(COUNTROWS('emp\_data1'), 'emp\_data1'\[Salary] > 90000)





**Bonus Allocation**



Merge Rating with Bonus Table by using Merge Queries in Power Query:

\-	Join HR (emp\_data1) Table with Bonus Rule Table using Rating

\-	Expand Bonus % into main table



**Calculating of Bonus Amount and Total Pay**



Bonus Amount = 'emp\_data1'\[Salary] \* 'emp\_data1'\[Bonus%]



Total Pay = 'emp\_data1'\[Salary] + 'emp\_data1'\[Bonus Amount]

