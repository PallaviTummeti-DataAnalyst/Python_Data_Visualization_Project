# Students Performance Analysis

## Overview
This project analyzes student performance data based on various demographic factors. The analysis includes visualizations of scores across different categories and inserts filtered data into a SQL database.

## Project Structure

The project is divided into three main tasks, each contained in its own code block within a Jupyter Notebook.

### Tasks
1. **Plot Scores vs. Race/Ethnicity**
   - A boxplot visualizing math, reading, and writing scores across different race/ethnicity groups.

2. **Plot Scores vs. Parental Level of Education**
   - A bar plot displaying the scores for math, reading, and writing against the parental level of education.

3. **Data Filtering and SQL Insertion**
   - Filters the dataset for female students in group A who completed a test preparation course and inserts relevant scores into a SQL Server database.

## Steps to Create the Plot
### Requirement 1: Plot Scores vs. Race/Ethnicity

1. **Import Libraries**:
   - Import the necessary libraries: `pandas` for data manipulation and `matplotlib.pyplot` for plotting.

2. **Load the Dataset**:
   - Load the dataset from a specified file path using `pd.read_csv()`. This reads the CSV file into a pandas DataFrame.

3. **Set Up the Plot**:
   - Create a new figure with a specified size using `plt.figure()`.

4. **Group Data by Race/Ethnicity**:
   - Group the data by the `race/ethnicity` column and calculate the mean scores for `math score`, `reading score`, and `writing score` for each group using `groupby()` and `mean()`.

5. **Create a Bar Plot**:
   - Use the `plot()` method with `kind='bar'` to create a bar chart that displays the average scores for each race/ethnicity group.

6. **Label the Axes and Title**:
   - Label the x-axis as "Race/Ethnicity" and the y-axis as "Average Score". Add a title to the plot to describe its contents.

7. **Display the Plot**:
   - Use `plt.show()` to display the generated bar plot.


### Requirement 2: Plot Scores vs. Parental Level of Education

1. **Import Libraries**:
   - Import the necessary libraries: `pandas` for data manipulation and `matplotlib.pyplot` for plotting.

2. **Load the Dataset**:
   - Load the dataset from a specified file path using `pd.read_csv()`. This reads the CSV file into a pandas DataFrame.

3. **Set Up the Plot**:
   - Create a new figure with a specified size using `plt.figure()`.

4. **Group Data by Parental Level of Education**:
   - Group the data by the `parental level of education` column and calculate the mean scores for `math score`, `reading score`, and `writing score` for each group using `groupby()` and `mean()`.

5. **Create a Bar Plot**:
   - Use the `plot()` method with `kind='bar'` to create a bar chart that displays the average scores for each parental education level.

6. **Label the Axes and Title**:
   - Label the x-axis as "Parental Level of Education" and the y-axis as "Average Score". Add a title to the plot to describe its contents.

7. **Rotate x-axis Labels**:
   - Rotate the x-axis labels by 90 degrees for better readability using `plt.xticks(rotation=90, ha='right')`.

8. **Display the Plot**:
   - Use `plt.show()` to display the generated bar plot.

### Requirement 3: Filter Data and Insert into SQL Server

1. **Import Libraries**:
   - Import the necessary libraries: `pandas` for data manipulation and `pyodbc` for connecting to SQL Server.

2. **Load the Dataset**:
   - Load the dataset from a specified file path using `pd.read_csv()`. This reads the CSV file into a pandas DataFrame.

3. **Filter the Data**:
   - Filter the DataFrame to include only female students from group A who have completed a test preparation course using logical conditions.

4. **Establish Database Connection**:
   - Create a connection to the SQL Server database using `pyodbc.connect()`. Include the driver, server name, database name, and trusted connection settings.

5. **Create SQL Table**:
   - Use the cursor object to execute a SQL command that creates a new table named `FemaleGroupACompletedTest` with appropriate column types for gender, race/ethnicity, test preparation course, and scores.

6. **Insert Filtered Data**:
   - Iterate over the filtered DataFrame using `iterrows()` to access each row.
   - For each row, execute an `INSERT` statement to add the data to the SQL table.

7. **Commit the Transaction**:
   - After all rows are inserted, call `conn.commit()` to save the changes to the database.

8. **Close the Database Connection**:
   - It’s a good practice to close the connection to the database once all operations are complete.
