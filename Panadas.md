# Pandas

•	Import pandas as pd
Functions used so far in Pandas
Series
1. s1 = pd.Series(list)-> This used to convert any list/dict/tuple into a series, a single row/column of values
2. s1[0]-> Indexing the series to get the values
3. s1 = pd.Series(list, index=[Index Values]) -> We can set the index intially during creation
4. s1 = s1.set_axis(NewIndex)-> We can chenge the index value
5. s1 = pd.Series(list, dtype=float)-> We can also change the data type of the series
6. s1 = pd.Series(list, name='Name_X')-> Naming the series
7. S4 = s2*s3 -> Arithmetic operation on the array, if the number of element doesn't match then the corresponding row will have NaN


1. pd.read_csv('Filepath with file with extension') -> Reads the csv file
2. pd.DataFrame(File/Series/list/Dict) -> Converts the data into a pandas DataFrame
3. data['col'].max() -> Gives the Max value in that column of a DtaFrame
4. data['col'].min() -> Gives the Min value in that column of a DtaFrame
5. data['col'].describe() -> Gives summary of whole data frame, Max, Min, SD, count
6. data['Col'] -> Gives the content of that column / data[['Col1', 'Col2']] -> Gives the content of the specifed columns.
7. data.index -> Gives the list/range of index values in a DataFrame
8. data.columns -> Gives the list of columns in a DataFrame
9. data.dtypes -> Gives the list of column's Data Type in a DataFrame
10. data.set_index('col', inplace=True) -> Set's the specified column as an index what can be used for analysis, inplace refres to permanent replacement of the changes made.
11. data.reset_index(inplace=True) -> Resets the original numerical value as an index.
12. pd.read_csv('File', header=X) -> We can select the required row of a CSV as a Header
13. pd.read_csv('File', header=None, prefix='Col') -> If we don't what any row to be header we can use it, OP will have Col1, Col2 ... as header.
14. pd.read_csv('File', names=['new col name1','new col name2','new col name3']) -> names - To create a custom headers
15. pd.read_csv('File', skiprows=X) -> Skips the specified number of Rows
16. pd.read_csv('File', nrows=X) -> Read/get only nrows
17. pd.read_csv('File', index_col=X) -> Makes the specified column(index number from 0) as index of the data frame.
18. pd.read_csv('File', usecol=[X]) -> imports only Selected column(index number from 0) to the data frame.
19. pd.read_csv('File', na_values=[x1, x2]) -> replaces the specified values as NaN
20. pd.read_csv('File', na_values={Col1: x1, Col2:x2}) -> replaces the specified values as NaN from specified columns
21. pd.read_csv('File', parse_dates=['Col with Date']) -> Converts the date column in string format to DateTime format
22. pd.read_csv('File', dtype={'Col1':'float' ) -> Converts the specified column's data type as mentioned
21. data.to_csv('Filename.csv', index=False) -> Index will be absent in the output file
22. data.to_csv('Filename.csv', columns=['col1', 'col2' ...]) -> only selected columns will be present in the csv file
23. data.to_csv('Filename.csv', converters={old_value: New_value}) -> Converts the specified value with the new value
24. data.to_csv('Filename.csv', header=['Header1','Header2','Header3'..'HeaderN' ] -> Adds the given value as the header
24. pd.read_excel('Filename.xlsx', sheet_name = 'Sheetname') ->Reads the excel file from speified sheetname.
25. data.to_excel('Filename.xlsx', sheet_name='sheet name', startcol=X, startrow=X) -> Creates a file ith given file name, sheet name and specified row and col number.

26. fillna function
26.a. data.fillna(value=X, inplace=True) -> Replace the NaN value with the specified Value
26.b. data.fillna(value={'col1':X, 'col2':Y, 'col3':Z},inplace=True) -> Replace the NaN value of given column with the specified Value
26.c. data.fillna(method='ffill',inplace=True) -> Fills the below NaN value with above non-NaN value
26.d. data.fillna(method='bfill',inplace=True) -> Fills the above NaN value with below non-NaN value
26.e. A = data.fillna(method='ffill', axis='columns')-> Fills the right NaN value with left non-NaN value
26.f. A = data.fillna(method='bfill',axis='columns')-> Fills the left NaN value with right non-NaN value
26.g. data.fillna(method='ffill', inplace=True, limit=2 )-> Fills the NaN value permanently and replaces only the limited number of NaN values.
27. data.interpolate(method='linear', inplace=True) -> Fill the NaN value with appropriate values my doing calculation. Works only with numerical data.


28. DropNa Function
28.a data.dropna(inplace=True) -> Removes the Rows with NaN values permanently
28.b data.dropna(subset=['Col_x'], inplace=True) -> We can specify w.r.t which column we should remove row with Nan
28.c data.dropna(how='all', inplace=True) -> Drops if all the values of a row is NaN
28.d data.dropna(how='any', inplace=True) -> Drops if any one of the values of a row is NaN
28.e data.dropna(axis='index', inplace=True) -> Drops the Column if it contans NaN
28.f data.dropna(thresh=3,axis='index' ,inplace=True) -> Drops the Column if it contans specified(threshold) number of NaN in a column

reindex function
1. df = df.reindex(df['col']) or df = df.reindex(Series) -> Sets the specified column as Index.

replace Function
1. data.replace(-99999, np.NaN, inplace=True)  -> df.replace(old, new) -> Replaces old value with new value
2. data.replace([-99999, '0'], np.NaN, inplace=True)   -> df.replace([old1,old2], new) -> Replaces old values with new value
3. data.replace({-99999:np.NaN, '0':'Sunny'}, inplace=True)  -> df.replace({old1:new1, old2:new2}) -> Replaces specific old values with specific new value.
4. data.replace({'temperature':-99999,'windspeed':-99999,'event':'0'}, np.nan, inplace=True)   -> .replace({col1:old, col2: old}, new) -> Replaces specific old values of specified column with specific new value.
5. data.replace({'temperature':'[A-Za-z]','windspeed':'[A-Za-z]'} ,'',regex=True, inplace=True)   -> add the units to the temp and windspeed and use regex to remove those units -> Removes the Alphabetic values using regression.
6. data.replace(['Rain','Sunny','Snow'],['R', 'Su', 'Sn'], inplace=True) -> .replace([o1, o2, o3, o4],[n1, n2, n3, n4]) -> Replaces specified list of values with new values in the order specified.
7. data.replace('old_value', method='ffill') -> replaces the specified value with the previous value
8. data.replace('old_value', method='bfill') -> replaces the specified value with the below value
9. df.replace('old_value',method='bfill', limit=1) -> we can limit the number of replacements for the method to be replaced.

Display Data
1. df.head() -> Displays the starting 5 Row values
2. df.head(X) -> Displays the mentioned number of rows from starting.
3. df.tail() -> Displays the ending 5 Row values
4. df.tail(X) -> Displays the mentioned number of rows from ending.
5. df[X:Y] -> Displays the mentioned row (Slicing) starting X, till Y

Sort function
1. df.sort_index(axis=0, ascending=False) -> sorts by index values
2. df.sort_index(axis=1, ascending=False) -> sorts by column headers
3. df.sort_values(by='Col_name', ascending=True) -> sorts by values of particualr column

loc function - Takes the column name as parameter
1a. df.loc[0, 'Col_name'] -> for retreiving single value
1b. df.iloc[[0,3],:] -> for retreiving single row, 
1c. df.loc[[0,3], ['Name', 'Gender']] -> for retreiving a particual shape
2. df.loc[0, 'Col_name'] = 'new_value' -> Modifies the data

iloc function - Takes the number(column's number) as parameter
1. df.iloc[0, 3] -> for retrieving data single value
1b. df.iloc[[0,3],:] -> for retreiving single row, 
1c. df.loc[[0,3], [1, 3]] -> for retreiving a particual shape

2. df.iloc[0, 4] = 'new_value' -> Modifies the data


GroupBy functions
1. data.groupby(col) -> Groups the other columns w.r.t the mentioned column, Default method of grouping other column is summing.
2. for i, j in groupData
   printi
   print j                                                          iterate and print the groups
3. groupdata.get_group('Col's - Value') -> Gives the grouping of the specified column value
4. gd.max() -> Max value of the group
5. gd.min() -> Min value of the group
6. gd.desccribe() -> Describes the group by count, max, min SD..etc
7. %matplotlib inline 
    gd.plot()

concat function
1. pd.concat([df1, df2...]) -> Appends the DataFrame one below the another.
2. pd.concat([df1, df2...], ignore_index=True) -> Ignores the indexes of dataframes and gives new index starting from 0
3. ndf = pd.concat([df1, df2], keys=['Key1', 'Key2']) -> keys function. Creates a subset for the data frame, 
can check using loc function (ndf.loc['Key1']
4. ndf = pd.concat([df1, df2], axis=1) -> Adds/Appends the DataFrame one next to another
5. ndf = pd.concat([df1, seriesdf], axis=1) -> merge series to df 
6. A = pd.concat([df1, df2], join='outer', axis=1) -> Based on the index value it joins the 2 dataframes
* Note it take the system generated index for Joining so its not a appropriate method to join if the order of both df are different
* So if we have proper column as index value then we can use join function.

merge function
1a. A = pd.merge(df1, df2, on='col1') -> Using pd function on = which column megring has to be performed.
1b. data = df1.merge(df2, on='col1') -> Merging on existing dataframe on = which column megring has to be performed.
2. data =df1.merge(df2, on='city', how='left') -> how function along with inner/outer/left/right aredifferent joins
3. data = df1.merge(df2, on='city', how='outer',indicator=True) -> indicator function to display type of merge on that row
4. data = df1.merge(df2, on='city', suffixes=('_week1', '_week2')) -> suffixes function, used when same column present in both df and need to differentiate

pivot function - This function doesn't allow duplicate values
1. newdf = df.pivot(index='date', columns='city') -> by giving index and columns to transform the original df
2. newdf = df.pivot(index='date', columns='city', values='temperature')-> by giving the values argument we can get the values of that column only
3. newdf = df2.pivot(index='date', columns=['city', 'Country'], values='temperature') -> by giving more than one values in columns we can get level by level information.

pivot table - This function does allow duplicate values and aggregates it.
1. newdf = df1.pivot_table(index='date', columns='city', aggfunc='count') -> by giving index and columns to transform the original df, aggfunc can be used to obtaining the tyoe of aggregation(sum, count, mean)
2. newdf = df1.pivot_table(index='date', columns='city', aggfunc='count', margins=True) -> margin function is used for getting subtotal
3. df1['date'] = pd.to_datetime(df1['date'])
newdf = df1.pivot_table(index=pd.Grouper(key='date', freq='M'),columns='city', aggfunc='count') -> convert a date column into datetime series coulmn and apply grouper function on it as a index. Grouper function groups the data based on the frequency mentioned.

melt - this is similar to unpivot function of PowerQuery
1. newdf = pd.melt(df, id_vars='day') -> this converts the other columns into rows except the specified variable, 
2. newdf = pd.melt(df, id_vars='day', value_name='Count', var_name='City') -> the value and variable name can be given as an argument.

stacking - method used for transforming one particular row(header) into a column. Used when there are multiple header (level)
1. newdf = df1.stack(1)
2. A = newdf.unstack()


Crosstab - Creating a table from source table based on the categorical value. It default gives the count of the specified column.
1. newdf = pd.crosstab(df['Sex'], df['Handedness']) -> based on the order it takes the row and column
2. newdf = pd.crosstab(df['Sex'], df['Handedness'], margins=True) -> margin function gives the sub total of the row and column 
3. newdf = pd.crosstab([df['Sex'], df['Nationality']], df['Handedness'], margins=True) -> we can pass multiple columns for row/column
4. newdf = pd.crosstab(df['Sex'], df['Nationality'], margins=True, normalize=True) -> we can get the percentage of the grand total
5. newdf = pd.crosstab(df['Sex'], df['Handedness'], margins=True, values=df['Age'], aggfunc='mean') -> we can also pass what the value should be, average/max/min of some other column

Timeseiries
1. df = pd.read_csv('TimeSeries_aapl.csv', parse_dates=['Date'], index_col=['Date']) -> Convert the date column into timestamp dtype, make the date column as index
Timeseiries - Resampling
1. df['Close'].resample('M').max() -> By defining the freq for the specief column and the type of Aggregate function we can resample the data.
2. %matplotlib inline
a. df['Close'].resample('M').max().plot(kind='line') -> we can also plot the grap for the resampled data using magic inline
b. df['Close'].resample('Q').max().plot(kind='bar') -> we can also plot the grap for the resampled data using magic inline
Date Range
1. rng = pd.date_range(starts='6/1/2017', end='6/30/2017', freq='B') -> Create a range of dates, with specified frequency
2. df.set_index(rng, inplace=True) -> sets the created range as index
3. %matplotlib inline
df['Close'].plot() -> plot the graph for the given column vs index
5. df.asfreq('D', method='bfill') -> we can generate the data for the blank dates/weeks/hours(D/W/H) and method can be pad - Forward fill/bfill - backward fill
6. st_rng = pd.date_range('1/1/2017', periods=60, freq='B') -> we can get the dates only using start date and specifying the numbers required with the frequency.
7. pd.Series(np.random.randint(20, 248, len(st_rng)), name='Rate', index=st_rng) -> By using the random dates set it as a index for randomly genrated number.
8. dates = pd.date_range('09/01/2023', '09/15/2023') -> Gives the range of dates
9. dates = pd.DatetimeIndex(dates) -> Converts the dates into Index which can be used for timeseries analysis.


Create custom holiday calender
1. from pandas.tseries.offsets import CustomBusinessDay -> Import the required function 
2. egypt_week = 'Sun Mon Tue Wed Thu'
cus = CustomBusinessDay(weekmask =egypt_week ) -> Create the custom weekdays
3. pd.date_range('10/1/2023', periods=30, freq=cus) -> use the custom weekdays in time series

Period Function
1. A = pd.Period('2024') -> Gives a default frequency of Anual (Period('2024', 'A-DEC'))
2. A.freq -> Gives the type of frequency (Deafult - <YearEnd: month=12>)
3. We can perform any time related function like start time/end time/leap year/day/month..etc
4. Wecan also do arithmatic operation on it

1. A.asfreq('M', how='S') -> This function is used to change the type of frequency i.e from Quarter to Month basis or Days to Week basis (S-> Start, E-> End where as 'D' = Days, 'M' = Month, 'B'=Business Days, 'H'=Hourly)

period_range function
1. a = pd.period_range('2017', '2019', freq='Q') -> Similar to date_range function it gives the range of dates based on specified freq, advantage here is we can give only year/year-month/year-month-date
2. a = pd.period_range('2017', periods=10, freq='D') ->If we don't know the end date we can mention the number of period required
3. sample = pd.Series(np.random.random(len(a)), index=a) -> We can also use the period range as the index
4. period_df = times_df.to_period(freq='Q') -> Converts the time stamp to period with required frequency

1. df.insert(2, column='Col_Name',value=list/other column) -> This function is used to inser any column into data frame at the mentioned position starts from 0
2. df.insert(6, column='New_Col', value=df['Col1'][1:7]) -> Copies the column or part of column
3. df.pop('Col') -> removes the specified column from dataframe
4. df.drop(columns=['Col1', 'Col3'], inplace=True) -> removes the specified columns from dataframe


Duplicates
1.	DataFrame.drop_duplicates(subset=None, *, keep='first', inplace=False, ignore_index=False)[source] -> Drops the duplicate values
2.	df.duplicated() -> Gives rows which are duplicate or not in True/False format
3.	df.dupliacted(keep=’last’) -> Will consider the 1st occurrence has duplicate not the last occurring one
4.	df.duplicated(keep=False) -> Will show all the duplicated row as true