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

For problems 1 and 2 in this exercise we will be using climate data from the Helsinki-Vantaa airport station.
For these problems, we have daily observations obtained from the [NOAA Global Historical Climatology Network](https://www.ncdc.noaa.gov/cdo-web/search?datasetid=GHCND).
The file was downloaded using the "Custom GHCN-Daily Text" output format, including the geographic location, precipitation (`PRCP`), average temperature (`TAVG`), maximum temperature (`TMAX`), and minimum temperature (`TMIN`).
The file for this problem is exactly as available from the NOAA website.
You should start by downloading [a copy of the data file](1091402.txt).
Note once again that temperatures in this dataset are given in degrees Fahrenheit, as noted in the [sample data file](ftp://ftp.ncdc.noaa.gov/pub/data/cdo/samples/GHCND_sample_pdf.pdf).
Additional information about the data format can be found in the [hints for Exercise 6](https://geo-python.github.io/2017/lessons/L6/exercise-6-hints.html).

# Problem 1 - Reading in a tricky data file



df = pd.read_csv('1091402.txt', sep='\s+', skiprows=[1], na_values='-9999', index_col='DATE', parse_dates=True)
df['2017-01-01':'2017-02-01']['TAVG'].mean()

# Problem 2 - Calculating temperature anomalies (5 pts)


