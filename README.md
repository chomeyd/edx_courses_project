# Exploratory Data Analysis(EDA) on the EdX 2013 Courses Data Set
## Purpose
The purpose of this project is to do an EDA on the dataset from https://public.tableau.com/en-us/s/resources?qt-overview_resources=1#qt-overview_resources. 
The data set is named **edX.org Academic Year 2012-2013**. This is done mainly to understand activities/vairaibles leading to registered users being certified.

## Analysis
### 1) Data cleaning
While exploring the data set column by column checking unique values, visualizing counts for these unique values and inspecting row, we learn the following;
1.	Columns last_event_DI to nforum_posts show course activity, drop rows where all a NaNs. Without any course activity a user won’t be certified.
2.	A number of columns are unnecessary for this EDA and will be deleted
3.	Age column has special characters to be turned to NaNs and also must parsed to numeric.
4.	3 more columns must be added; age_group, duration and duration_range.
5.	No duplicate rows were found.

Functions used include;
1.	**DataFrame.drop()** for droping rows or columns.
2.	**DataFrame['column_name'].unique()** to check unique values for columns.
3.	**sns.countplot(y='column_name', data=df)**; to visualize value counts.
4.	**DataFrame.duplicated().sum()** to check if there any duplicated rows.

### 2) Dealing with missing data
There is evidence of existence of missing values and they printed printed out using **print(df.isnull().sum())** to see number in each column and plotted using 
**missingno.matrix(DataFrame)**. The missing values for string data types were thereafter replaced with “other” and numeric data types with the median of the 
variable grouped by *course_id* and *certified*.

### 3) Visualistions and Data Stories
This part of the analysis looked into;
* Plots of distibutions by count of *Age*, *duration*, *Course Long Title*, *gender* and *LoE_DI*
* Plots of average *nevents*, *ndays_act*, *nplay_video*, *nchapters*, *nforum_posts*, *duration* and *LoE_DI* for those who are certified and those who are not.
* Tables of different activity types for those who are certified and those who are not grouping by different variables e.g Age, Course title etc.
* Corrrelations between different activities and grades.

## Findings
*Registered users mainly consist of
**	Age group between 20 and 30 years
**	Duration of course between 20 to 30 days
**	Both Introduction to computer science courses.
**	Males.
**	And mostly had level of education as a bachelor’s.
*	30 to 50 year olds get the highest marks on average
* Users doing the Health in numbers course got the highest marks on average
*	Education level does matter. Doctorate holders get the highest marks followed by Masters holders.
* It is interesting to find the 2 courses with the least active days counts and events had the longest average duration in days. The ancient Greek hero 
and Introduction to computer science 1.
* We see that Introduction to computer science and programming course had the most certified users.
* Most certified users are Bachelor’s holders
* Users who got certified did far more events, active days, chapters, forum posts and video plays. 
* There is no clear correlations between grades and activities.



