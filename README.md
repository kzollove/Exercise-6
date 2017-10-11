# Exercise 6 - Data analysis with Pandas

In this week's exercise we will continue developing our skills using Pandas to analyze climate data.

After making your changes, you will need to upload your files to GitHub.
The answers to the questions in this week's exercise should be given by modifying the document in the requested places.

If you are uncertain about **the style of your code**, take a look at the **[PEP 8 - Style guide for Python code](https://www.python.org/dev/peps/pep-0008/)**.  

 - **Exercise 6 is due by the start of lecture on 18.10.**
 - Don't forget to check out the [hints for this week's exercise](https://geo-python.github.io/2017/lessons/L6/exercise-6-hints.html) if you're having trouble.
 - Scores on this exercise are out of 20 points.
 - There are altogether 4 problems that you should solve. The fifth problem is optional for more advanced students (does not affect grading)

# Data

For problems 1-3 in this exercise we will be using climate data from the Helsinki-Vantaa airport station.
For these problems, we have daily observations obtained from the [NOAA Global Historical Climatology Network](https://www.ncdc.noaa.gov/cdo-web/search?datasetid=GHCND).
The file was downloaded using the "Custom GHCN-Daily Text" output format, including the geographic location, precipitation (`PRCP`), average temperature (`TAVG`), maximum temperature (`TMAX`), and minimum temperature (`TMIN`).
The file for this problem is exactly as available from the NOAA website.
You should start by downloading [a copy of the data file](1091402.txt).
Note once again that temperatures in this dataset are given in degrees Fahrenheit, as noted in the [sample data file](ftp://ftp.ncdc.noaa.gov/pub/data/cdo/samples/GHCND_sample_pdf.pdf).
Additional information about the data format can be found in the [hints for Exercise 6](https://geo-python.github.io/2017/lessons/L6/exercise-6-hints.html).

# Problem 1 - Reading in a tricky data file (3 points)

You first task for this exercise is to read in the data file to a variable called `data`.
This should be done using the `read_csv()` function in Pandas, and the resulting DataFrame should have the following attributes:

  - The numerical values for rainfall and temperature read in as numbers
  - The second row of the datafile should be skipped, but the text labels for the columns should be from the first row
  - The no-data values should properly be converted to `NaN`

You can find hints about how to do these things in the [description of Exercise 5](https://github.com/Geo-Python-2017/Exercise-5) and the [hints for Exercise 6](https://geo-python.github.io/2017/lessons/L6/exercise-6-hints.html).

- How many non-NaN values are there for `TAVG`?
- What about for `TMIN`?
- How many days total are covered by this data file?
- When is the first observation?
- When is the last?

**For this problem**

1. Create a new script file called `temperature_anomalies.py`
2. Make sure the script can read in the data file
3. Have the script print out the requested values for the questions above to the screen
4. Upload a copy to your repository for this week's exercise.

# Problem 2 - Calculating monthly average temperatures (3 points)

For this problem our goal is to calculate monthly average temperature values in degrees Celsius from the daily values we have in the data file.
You can use the approaches taught during the Lesson 6 to solve this .
You can again consult the [hints for Exercise 6](https://geo-python.github.io/2017/lessons/L6/exercise-6-hints.html) if you are stuck.

For this problem modify your `temperature_anomalies.py` script to

1. Calculate the monthly average temperatures for the entire data file using the approaches taught during the lecture
2. Save the output to a new Pandas Series called `dataMonths`
3. Create a second Series called `dataMonthsC` that has the monthly temperatures in Celsius.
4. Merge the two data Series into a single Pandas DataFrame called `monthlyData` using the `pd.concat()` function (see the [documentation of Pandas](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.concat.html) or hints if needed).
4. Upload the updated script to your repository for this week's exercise.

## Problem 2.1 (optional)

You goal is to figure out how to use the datetime functionalities of Pandas shortly mentioned in the [Lesson 6 materials](https://geo-python.github.io/2017/lessons/L6/lessons/L6/pandas-analysis.html#string-manipulation-in-pandas.html).
You should find out how to create a DataTime index in Pandas and use the `DataFrame.resample()` function to directly calculate the mean monthly temperatures from the daily observation values.

# Problem 3 - Calculating temperature anomalies (4 points)

In this problem, you should now calculate the temperature anomalies to see how temperatures have been changing on average over the age range in the data file.
First, we need to calculate a reference temperature value, which is the average temperature 
