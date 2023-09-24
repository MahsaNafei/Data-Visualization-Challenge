# Data-Visualization-Challenge
Data Visualization
# Pymaceuticals Inc.
---

## Analysis

-The code offers a thorough examination of the mouse research dataset, including data cleaning, statistical analysis, data visualization, and summary statistics.
-It aids in the visualization of the tumor volume distribution for particular medication regimens and the identification of potential outliers.
-For mice given Capomulin treatment, the correlation and regression analysis indicates a somewhat positive association between mouse weight and tumor volume, with an R-squared value indicating that almost 70% of the variability in tumor volume may be attributed to mouse weight.



## Data Sources

The analysis utilizes two CSV files:

- `Mouse_metadata.csv`: Contains metadata about the mice in the study.
- `Study_results.csv`: Contains data on the study results, including tumor volume measurements.

## Data Processing

Data Loading:

-The analysis script begins by importing necessary Python libraries, including matplotlib.pyplot, pandas, scipy.stats, numpy, and scipy.stats.linregress.
-It also defines the file paths for two CSV files: Mouse_metadata.csv and Study_results.csv.

Data Reading and Merging:

-The script reads the data from the CSV files using pd.read_csv() to create two DataFrames: mouse_metadata and study_results.
-The data from these two DataFrames are merged into a single DataFrame called combined_data using the pd.merge() function. This merging is based on the "Mouse ID" column, ensuring that data from both files is aligned for analysis.

Duplicate Data Handling:

-The analysis identifies potential data quality issues related to duplicate entries for the same mouse at the same timepoint.
-Duplicate data for the mouse with ID "g989" is detected by checking for duplicated rows based on the "Mouse ID" and "Timepoint" columns. These duplicates are stored in a variable called duplicated_id.
-A separate DataFrame, duplicated_data, is created to count the number of duplicate entries for each mouse and timepoint combination.
-The script then isolates the specific mouse IDs (duplicated_id) that have more than one entry, indicating duplicate data.


Data Cleaning:

-The analysis provides an optional step to get all the data for the duplicate mouse ID ("g989") using boolean indexing. -This data is stored in the duplicate_g989 DataFrame.
-To create a clean dataset for further analysis, a new DataFrame named clean_df is generated by excluding rows with mouse IDs found in duplicated_id. This ensures that data from mice with potential data quality issues is removed.

Data Summary Statistics:

-The script calculates summary statistics for tumor volume measurements for each drug regimen in the cleaned dataset. -The statistics include mean, median, variance, standard deviation, and standard error of the mean (SEM) for tumor volumes grouped by drug regimen.
-These summary statistics are stored in the summary_df DataFrame.
-Alternative Summary Statistics (Aggregation), the script calculates the same summary statistics using the aggregation method, which produces the results for all statistics in a single line. This is stored in the summary_agg_df DataFrame.

Data Visualization:

-Bar charts are generated to visualize the total number of observations (Mouse ID/Timepoints) for each drug regimen using both Pandas and Matplotlib's Pyplot.
-A pie chart is created to illustrate the distribution of female versus male mice using both Pandas and Matplotlib.

Quartiles, Outliers, and Boxplots:

-The script calculates the final tumor volume of each mouse for four specific treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin.
-Quartiles, potential outliers, and boxplots are used to visualize the distribution of tumor volumes for each treatment regimen. Outliers are determined using the IQR method.

Line and Scatter Plots:

-A line plot is generated to visualize the change in tumor volume over time for a single mouse ("l509") treated with Capomulin.
-A scatter plot is created to visualize the relationship between mouse weight and the average observed tumor volume for the entire Capomulin regimen.

Correlation and Regression:

-Correlation analysis is performed to quantify the relationship between mouse weight and average tumor volume for mice treated with Capomulin.
-A linear regression analysis is conducted to fit a regression line to the scatter plot, allowing for a better understanding of how changes in mouse weight impact tumor volume.
-The correlation coefficient (r-value) and the coefficient of determination (r-squared) are calculated and displayed on the plot.

## Instructions

To use this script:

1. Ensure you have the following CSV files in the same directory as the script:
   - `Mouse_metadata.csv`
   - `Study_results.csv`

2. Run the script using Python.

3. The analysis results, including visualizations and statistical summaries, will be displayed.