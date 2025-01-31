# Basic-Code-of-Python
# Basic Code of Python for beginners
# Key Steps:
		1. Import Libraries: Essential libraries for data analysis
		2. Load Data: Read CSV/Excel/other files using pandas
		3. Data Exploration:
			○ head(): View first rows
			○ info(): Data types and non-null counts
			○ describe(): Statistical summary
		4. Data Cleaning:
			○ Handle missing values
			○ Remove duplicates
			○ Fix data types
		5. Basic Analysis:
			○ Filtering
			○ Grouping
			○ Aggregation
		6. Visualization:
			○ Basic plots for data distribution

# Tips:
		○ Use df.shape to check data dimensions
		○ Use df.columns to see column names
		○ For datetime data: pd.to_datetime(df['date_column'])
		○ For sorting: df.sort_values('column_name')
	
	
	
	1. Import Necessary Libraries
		# For data manipulation and analysis
import pandas as pd 
		# For numerical operations
		import numpy as np   
		# For data visualization
		import matplotlib.pyplot as plt  
		 # For displaying plots in Jupyter Notebook
%matplotlib inline 
	
	2. Create Series and DataFrames (Pandas):
		○ Series: A one-dimensional array-like object that can hold any data type.
		# Create a Series (1D array-like object)
		series = pd.Series([1, 2, 3, 4])
print("Series:")
print(series)
		
		○ DataFrame: A two-dimensional, size-mutable, and heterogeneous tabular data structure.
		# Create a DataFrame (2D tabular data structure)
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
print("\nDataFrame:")
print(df)
	
	3. Load Data:
		○ Read CSV: Read a CSV file into a DataFrame.
		# Read a CSV file into a DataFrame
df = pd.read_csv('file.csv')  # Replace 'file.csv' with your file path
print("\nDataFrame from CSV:")
print(df.head())
		OR
df = pd.read_csv('file.csv')
		
	4. Data Inspection:
		○ Head(): Returns the first few rows.
		# View the first few rows
print("First 3 rows:")
print(df.head(3))
		
		○ Tail(): Returns the last few rows.
		# View the last few rows
print("\nLast 3 rows:")
print(df.tail(3))
		
		○ Describe(): Provides descriptive statistics for numeric columns.
		# Get descriptive statistics for numeric columns
print("\nDescriptive Statistics:")
print(df.describe())
		
		○ Info(): Displays information about the DataFrame.
		# Display information about the DataFrame
print("\nDataFrame Info:")
print(df.info())
	
	5. Descriptive Statistics:
		○ Summary Statistics:
		# Get summary statistics
print("\nSummary Statistics:")
print(df.describe())
		
		○ Specific Statistics:
		# Mean, median, standard deviation
		# Calculate mean, median, and standard deviation
print("Mean:", df['Column1'].mean())
print("Median:", df['Column1'].median())
print("Standard Deviation:", df['Column1'].std())
	
	6. Data cleaning:
		○ Handling Missing Values
		○ Detecting Missing Values:
		# Check for missing values
print("Missing Values:")
print(df.isnull().sum())
		
		○ Filling Missing Values:
		# Fill missing values with a specific value (e.g., 0)
df_filled = df.fillna(value=0)
print("\nDataFrame after Filling Missing Values:")
print(df_filled.head())
		
		○ Dropping Missing Values:
		# Drop rows with missing values
df_dropped = df.dropna()
print("\nDataFrame after Dropping Missing Values:")
print(df_dropped.head())
		
		○ Removing Duplicates
		df = df.drop_duplicates()
		
		○ Fixing Data Types
		# Convert columns to appropriate data types (replace 'column_name' and dtype)
		df['column_name'] = df['column_name'].astype('desired_dtype')  # Example: 'int', 'float', 'category', 'datetime64'
		# Convert date columns
		df['date_column'] = pd.to_datetime(df['date_column'], errors='coerce')
	
		○ Display cleaned data
		display(df.head())
	
	7. Headers and Column Names:
		○ Set Column Names:
		# Set new column names
df.columns = ['Column1', 'Column2']
print("\nDataFrame with New Column Names:")
print(df.head())
		OR
df.columns = ['Column1', 'Column2']
		df = pd.DataFrame(data, columns = ['students', 'grade', 'location'])
	
		○ Change Column Names:
		# Rename specific columns
df_renamed = df.rename(columns={'Column1': 'NewA', 'Column2': 'NewB'})
print("\nDataFrame with Renamed Columns:")
print(df_renamed.head())
	
	8. whos function tells you the type and length of variable you created
		# Use `whos` to check variable types and sizes (only works in Jupyter Notebook)
whos
	
	9. Lists:
		○ Create a List: A list in Python can be converted to a Series or DataFrame.
		# Create a list
my_list = [1, 2, 3, 4]
print("List:", my_list)
		
		# Convert a list to a Pandas Series
series_from_list = pd.Series(my_list)
print("\nSeries from List:")
print(series_from_list)
		
		○ Convert to List: Convert a Series or DataFrame column to a list.
		# Convert a DataFrame column to a list
column_as_list = df['A'].tolist()
print("\nColumn 'A' as List:", column_as_list)
		
	10. Tuples
		# Create a tuple
my_tuple = (1, 2, 3, 4)
print("\nTuple:", my_tuple)
		
		# Convert a tuple to a Series
series_from_tuple = pd.Series(my_tuple)
print("\nSeries from Tuple:")
print(series_from_tuple)
	
	11. Dictionaries:
		○ Create a Dictionary: Often used to create DataFrames.
		# Create a dictionary
data = {'A': [1, 2, 3], 'B': [4, 5, 6]}
print("Dictionary:", data)
		
		# Convert a dictionary to a DataFrame
df_from_dict = pd.DataFrame(data)
print("\nDataFrame from Dictionary:")
print(df_from_dict)
	
	12. Adding/Changing Rows:
		○ Add a Row:
		# Add a new row to the DataFrame
df.loc[len(df)] = [7, 8]
print("\nDataFrame after Adding a Row:")
print(df)
	
		○ Change a Row:
		# Modify an existing row
df.loc[0] = [10, 11]
print("\nDataFrame after Changing a Row:")
print(df)
	
	13. Modifying Row Index:
		○ Set New Index:
		# Set a column as the new index
df.set_index('Column1', inplace=True)
print("\nDataFrame with New Index:")
print(df)
	
	14. Skipping Rows:
		○ Skip Rows While Reading CSV:
		# Skip the first 5 rows while reading a CSV file
df = pd.read_csv('file.csv', skiprows=5)
print("\nDataFrame after Skipping Rows:")
print(df.head())
	
	15. Subsetting Data:
		○ Subset Data (Rows and Columns):
		# Subset specific rows and columns
df_subset = df.loc[1:3, ['Column1', 'Column2']]
print("\nSubset of DataFrame:")
print(df_subset)
		
		○ Indexing:
		# Access specific elements using iloc (index-based) and loc (label-based)
print("Element at 1st row, 2nd column:", df.iloc[0, 1])
print("Column 'Column1':", df['Column1'])
		OR
# 1st row, 2nd column
		df.iloc[0, 1]  
		# Selects column 'A'
		df['A'] 
	
	16. Filtering Data:
		○ Filter with Condition:
		# Filter rows based on a condition
df_filtered = df[df['Column1'] > 2]
print("\nFiltered DataFrame:")
print(df_filtered)
	
	17. Sorting:
		○ Sort by Column:
		# Sort the DataFrame by a column
df_sorted = df.sort_values(by='Column1')
print("\nSorted DataFrame:")
print(df_sorted)
	
	18. concat()
	The concat() function is used to concatenate two or more pandas objects along a particular axis (rows or columns).
	# Concatenate two DataFrames along rows or columns
df1 = pd.DataFrame({'A': [1, 2, 3], 'B': ['X', 'Y', 'Z']})
df2 = pd.DataFrame({'A': [4, 5, 6], 'B': ['P', 'Q', 'R']})
	
	# axis=0 for rows
	result = pd.concat([df1, df2], axis=0) 
	
	# axis=1 for columns
	result = pd.concat([df1, df2], axis=0) 
	
	print("\nConcatenated DataFrame:")
print(result)
	
	19. merge()
	The merge() function is used for merging two dataframes based on a common column (like SQL joins).
	# Merge two DataFrames based on a common column
df1 = pd.DataFrame({'key': ['A', 'B', 'C'], 'value': [1, 2, 3]})
df2 = pd.DataFrame({'key': ['B', 'C', 'D'], 'value2': [4, 5, 6]})
	For.# Merge on a common column 'key' 
	result = pd.merge(df1, df2, on='key', how='inner')  # how can be 'left', 'right', 'outer', 'inner'
print("\nMerged DataFrame:")
print(result)
	
	20. how
	The how parameter is used within the merge() function to specify the type of merge. Here are its options:
		○ 'left': Use only keys from left frame.
		○ 'right': Use only keys from right frame.
		○ 'outer': Use union of keys from both frames.
		○ 'inner': Use intersection of keys from both frames (default).
	# Example of how parameter in merge: 
	result = pd.merge(df1, df2, on='key', how='outer') # Merge with 'outer' join
	
	21. groupby()
	The groupby() function is used to group data based on one or more columns.
	# Group data by a column
grouped = df.groupby('Column1')
print("\nGrouped Data:")
for name, group in grouped:
    print(name)
    print(group)
	
	22. aggregate()
	The aggregate() function is used to apply one or more functions to the grouped data.
	# Aggregate grouped data
result = df.groupby('Column1').aggregate({'Column2': ['sum', 'mean']})
print("\nAggregated Data:")
print(result)
	
	23. transform()
	The transform() function is used to perform element-wise transformations on grouped data.
	import pandas as pd
	# Example DataFrame
df = pd.DataFrame({'A': ['foo', 'foo', 'bar', 'bar'], 'B': [1, 2, 3, 4]})
	# Group by 'A' and transform column 'B' with the sum of the group
result = df.groupby('A')['B'].transform('sum')
	
	24. Reshaping Operations
		○ stack(): Moves the columns of a DataFrame into the index, creating a Series with a hierarchical index. It compresses data to a long format.
		# Stack columns into rows
stacked = df.stack()
print("\nStacked DataFrame:")
print(stacked)
		
		○ unstack(): The reverse of stack(). Moves the innermost index level to the columns, expanding data to a wide format.
		# Unstack rows into columns
unstacked = stacked.unstack()
print("\nUnstacked DataFrame:")
print(unstacked)
	
		○ melt(): Converts a wide-format DataFrame into a long-format DataFrame by unpivoting selected columns.
		# Melt DataFrame to long format
melted = pd.melt(df, id_vars=['Column1'], var_name='Variable', value_name='Value')
print("\nMelted DataFrame:")
print(melted)
		
		○ pivot(): Converts a long-format DataFrame into a wide-format DataFrame by creating new columns based on unique values in a specified column.
		# Pivot DataFrame to wide format
pivoted = df.pivot(index='Column1', columns='Variable', values='Value')
print("\nPivoted DataFrame:")
print(pivoted)
	
	25. map():
		○ Apply Functions to Columns:
		# Apply a function to a column
df['Column1'] = df['Column1'].map(lambda x: x * 2)
print("\nDataFrame after Mapping:")
print(df)
		# Example of map() in Python 
		def square(x): 
		        return x ** 2 
		        
		numbers = [1, 2, 3, 4, 5] 
		result = map(square, numbers) 
		
		# Convert the result to a list to see the output 
		result_list = list(result) print(result_list) 
		
		# Output: [1, 4, 9, 16, 25]
	
	26. apply():
		# Create a simple DataFrame 
		data = {'A': [1, 2, 3, 4], 'B': [5, 6, 7, 8]} 
		df = pd.DataFrame(data) 
		
		# Apply a function to each column 
		def add_one(x): 
		        return x + 1 
		
		result_df = df.apply(add_one) 
		
		print(result_df)
	
	27. lambda (or anonymous) function
		○ Addition
		add = lambda x, y: x + y 
		print(add(3, 5)) 
		# Output: 8
		
		○ Subtract
		subtract = lambda x, y: x - y 
		print(subtract(10, 3)) 
		# Output: 7
		
		○ Division
		divide = lambda x, y: x / y 
		print(divide(10, 2)) 
		# Output: 5.0
		
		○ Multiplication
		multiply = lambda x, y: x * y 
		print(multiply(3, 4)) 
		# Output: 12
		
		○ Power
		power = lambda x, n: x ** n 
		print(power(2, 3)) 
		# Output: 8
		2 στον κύβο
		
		○ Absolute value
		absolute = lambda x: abs(x) 
		print(absolute(-5)) 
		# Output: 5
		
		○ Complex calculations
		complex_calc = lambda x, y, z: (x ** 2 + y ** 2) / z 
		print(complex_calc(3, 4, 2)) 
		# Output: 12.5
		
		○ Square root or the sin() function from the math library
		sqrt = lambda x: math.sqrt(x) 
		print(sqrt(16)) 
		# Output: 4.0
	
	28. Basic visualisation
		○  Histogram
		df['numerical_column'].hist()
plt.title('Distribution of Numerical Column')
plt.show()
		
		○ Bar plot
		df['category_column'].value_counts().plot(kind='bar')
plt.title('Category Distribution')
plt.show()
		
		○ Scatter plot
		df.plot.scatter(x='column1', y='column2')
plt.title('Scatter Plot')
plt.show()
	
	29. Operations:
		○ Sum: Summing values in a Series or DataFrame.
df['A'].sum()
		
		○ Count: Counting non-null entries.
df['A'].count()
		
		○ Max / Min: Finding the maximum or minimum values.
df['A'].max(), df['A'].min()
		
		○ Calculating Percentages:
		To calculate the percentage of a number, you multiply the value by the percentage (as a decimal) and then divide by 100.
		Example:
		# Let's calculate 25% of 80
		number = 80
percentage = 25
result = (percentage / 100) * number
print(result) 
		# Output
		20.0

		To calculate a percentage of a number directly:
	
		# To find 25% of 80:
result = (25 / 100) * 80  
		#Output
		20.0
		
		If you want to find what percentage a number is of another number (e.g., What percentage is 20 of 80?):
		part = 20
whole = 80
percentage_of_whole = (part / whole) * 100
print(percentage_of_whole)  
		# Output
		25.0
	
		○ Rounding Numbers:
		You can use Python’s built-in round() function to round numbers to a specific number of decimal places.
		Example:
		# To round a number to 2 decimal places:
		number = 3.14159
rounded_number = round(number, 2)
print(rounded_number)  
		# Output
		3.14
		
		If you don’t specify the number of decimal places, it will round to the nearest integer:
		rounded_number = round(3.6)
print(rounded_number)  
		# Output
		4

		○ Floor and Ceiling Operations:
		Sometimes, you need to round a number down or up explicitly. You can use the math module for this.
		
		Floor (round down):
		import math
number = 3.7
floored = math.floor(number)
print(floored) 
		# Output
		3
		
		Ceiling (round up):
		import math
number = 3.2
ceiled = math.ceil(number)
print(ceiled)
		# Output
		4
		
		○ Percent Change:
		To calculate the percentage change between two values, you can use the following formula:
		((new_value - old_value) / old_value) * 100
		Example:
		old_value = 100
new_value = 120
percent_change = ((new_value - old_value) / old_value) * 100
print(percent_change) 
		# Output
		20.0
		
		○ Basic Arithmetic Operations:
		You can perform basic arithmetic like addition, subtraction, multiplication, and division in Python.
		
		Addition:
		sum_result = 5 + 3
print(sum_result)  
		# Output
		8
		
		Subtraction:
		diff_result = 5 - 3
print(diff_result)  
		# Output
		2
		
		Multiplication:
		prod_result = 5 * 3
print(prod_result)  
		# Output
		15
		
		Division:
		div_result = 5 / 3
print(div_result)  
		# Output
		1.6666666666666667
		
		If you need integer division (without the remainder):
		int_div_result = 5 // 3
print(int_div_result)
		# Output
		1
		
		Modulo (remainder of division):
		remainder = 5 % 3
print(remainder)  
		# Output
		2
		
		○ Working with Large Numbers:
		Python supports very large numbers natively, and you can perform operations on them without worrying about overflow.
		For example:
		large_number = 1000000000
small_number = 0.00000001
result = large_number * small_number
print(result) 
		# Output 
		0.01
		
		○ Absolute Value:
		To get the absolute value of a number (i.e., remove the negative sign if any):
		number = -3.14
absolute_value = abs(number)
print(absolute_value)  
		# Output 
		3.14

	19. Formatting function
		○ Basic Usage of .style.format():
		The .style.format() method allows you to apply formatting options to columns.
		Example: Format numerical values to 2 decimal places
		import pandas as pd
		# Creating a sample DataFrame
data = {'students': ['George', 'Sarah', 'John'],
        'grades': [87.654, 92.321, 78.910],
        'attendance': [88.3, 92.1, 80.5]}
		df = pd.DataFrame(data)
		# Formatting the 'grades' and 'attendance' columns to show 2 decimal places
df.style.format({
    'grades': '{:.2f}',   # Format 'grades' column to 2 decimal places
    'attendance': '{:.1f}'  # Format 'attendance' column to 1 decimal place
})
	
	• Formatting Percentages:
		You can also format values as percentages.
		Example: Format numeric values as percentages
		import pandas as pd
		# Creating a sample DataFrame
data = {'students': ['George', 'Sarah', 'John'],
        'completion_rate': [0.87, 0.92, 0.78]}
		df = pd.DataFrame(data)
		# Formatting 'completion_rate' column as percentages with 1 decimal place
df.style.format({
    'completion_rate': '{:.1%}'  # Format to percentage (1 decimal)
})
		
		○ Formatting Date Columns:
		If you have a column with dates, you can format the date representation as well.
		Example: Format date column
		import pandas as pd
		# Creating a sample DataFrame with a date column
data = {'students': ['George', 'Sarah', 'John'],
        'enrollment_date': ['2021-01-15', '2022-05-12', '2023-03-19']}
		df = pd.DataFrame(data)
		# Converting the 'enrollment_date' column to datetime
df['enrollment_date'] = pd.to_datetime(df['enrollment_date'])
		# Formatting the 'enrollment_date' column to display dates in 'MM-DD-YYYY' format
df.style.format({
    'enrollment_date': lambda t: t.strftime('%m-%d-%Y')  # Format date column
})
		
		○ Formatting Multiple Columns:
		You can format multiple columns in a DataFrame at once.
		Example: Format multiple columns with different formatting styles
		import pandas as pd
		# Creating a sample DataFrame
data = {'students': ['George', 'Sarah', 'John'],
        'grades': [87.654, 92.321, 78.910],
        'attendance': [88.3, 92.1, 80.5]}
		df = pd.DataFrame(data)
		# Formatting both 'grades' and 'attendance' columns
df.style.format({
    'grades': '{:.2f}',   # Format 'grades' to 2 decimal places
    'attendance': '{:.1f}'  # Format 'attendance' to 1 decimal place
})
		
		○ Using Custom Formatters:
		You can also create custom formatting functions to apply to columns.
		Example: Applying a custom function to format values
		import pandas as pd
		# Creating a sample DataFrame
data = {'students': ['George', 'Sarah', 'John'],
        'grades': [87.654, 92.321, 78.910]}
		df = pd.DataFrame(data)
		# Custom function to format grades (for example, show a grade as "A", "B", etc.)
def grade_formatter(x):
    if x >= 90:
        return 'A'
    elif x >= 80:
        return 'B'
    else:
        return 'C'
		# Applying the custom function to the 'grades' column
df.style.format({
    'grades': grade_formatter
})
![image](https://github.com/user-attachments/assets/8ab4318a-d8dd-4c4b-973a-a6a3c3aaa6a7)
