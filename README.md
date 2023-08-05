# data-visualization-week-17-core-assignment-1---Resampling-Datetime-Data


***

## Assignment Feedback:

<image src = feedback.png >

***

## (Core) Resampling Datetime Data

For this assignment, you will be working with a modified version of [weather data from London from Kaggle](https://www.kaggle.com/datasets/emmanuelfwerr/london-weather-data).

The assignment is split into 2 parts:

- Part 1: Load the data and create a datetime index

- Part 2: Answer 2 Questions using visualizations and the correct frequency data

## Part 1) Load the data and make a datetime index.

- Use the modified version of the data provided here:
   - Share URL: https://docs.google.com/spreadsheets/d/1J2hEGA1-ZOdXOc1Go2AjB7xShq-nAvIDpBz_XRZscHU/edit?usp=sharing
   - Raw URL:
      - https://docs.google.com/spreadsheets/d/e/2PACX-1vT_jChgNsQbHbg4TGepzIqk8XC9DTIKmyyxb1upo5cfZCgbfIUQc2ZC0YMzuU5uApP140Ob49KBjdqh/pub?gid=1198589591&single=true&output=csv

You must first load the data and create a datetime index.

1. Convert the date column to datetime dtype.
2. Set the date column as the index.
3. Filter out only the required data:
  - Keep only data from the year 2000 or later.
  - Keep only the following features:
    - precipitation
    - mean_temp
    - min_temp
    - max_temp
    - snow_depth
4. Impute any missing values.
    - Think about each feature and what imputation method makes sense. You may not be able to use the same method for every feature!

## Part 2) Answer the Questions with Visualizations (Using the Correct Frequency)

- For each of the following questions, make a new copy of the dataframe resampled to the correct frequency for the question.

- Plot the feature that the question is asking about.
   - If there is a specific time period, plot only that time period.

Note: you may want to make a temporary DataFrame that you will use to answer this question only.

### Q1: What month had the most precipitation between 2000 through 2010?

- Resample the data as Monthly frequency.
- Find the date and corresponding value for the max precipitation.
- Plot the feature and time period that corresponds to the question.
   - Make sure to meet the "Visualization Requirements" below!
- Determine the date and value for the most precipitation (the max precipitation).
- Add a vertical line at this date with a label that says the date (using date format: "April 2000") and the max precipitation value.
   - Make sure to add a legend so that your label is visible.

#### Visualization Issue Workaround

- NOTE: Pandas' .plot method currently has a bug with 4-digit year axis labels. The tick labels misbehave when being formatted with matplotlib and will produce a mostly-blank axis with 1 year labeled, like the screenshot below:


- To get around this issue, first, create your fig and ax using plt.subplots()


    - Now you may use pandas .plot method to plot this figure by adding the argument "ax=ax" to .plot().

       > fig, ax = plt.subplots(figsize=(12,3))
       > 
       > df.plot(ax=ax)
       
#### Q1 Visualization Requirements
- Use a combination of pandas, matplotlib tick formatters, tick locators, and the fig.autofmt_xdate method to:
   - Create a wide figure (e.g. figsize=(12,3))
     - With the title "Precipitation for 2000-2010"
     - With a ylabel of "Inches"
   - Customize the major xaxis ticks to:
     - Have major xaxis ticks every 1 year.
     - Use 4-digit years for the labels
     - Rotate the major ticks' labels 90 degrees.
   - Customize the minor xaxis ticks to:
     - Have minor xaxis ticks every 3 months
     - Do not label the minor ticks.

### Q2: Which year between 2000-2020 had the coolest average temperature?

- Resample the data as Yearly frequency.

- Plot the feature and time period that corresponds to the question.
   - Make sure to meet the "Visualization Requirements" below!
- Determine the date and value for the lowest mean temp.
- Add a vertical line at this date with a label that says the date (using date format: "2000") and the lowest mean temperature value.



#### Q2 Visualization Requirements
- Use a combination of pandas, matplotlib tick formatters, tick locators, and the fig.autofmt_xdate method to:
   - Create a wide figure (e.g. figsize=(12,3))
      - With the title "Average Temperature"
      - With a ylabel of "Degrees"
   - Customize the major xaxis ticks to:
      - Have major xaxis ticks every 5 years.
      - Use 4-digit years for the labels
      - Rotate the major ticks' labels 90 degrees.
   - Customize the minor xaxis ticks to:
      - Have minor xaxis ticks every 1 year
      - Do not label the minor ticks.


Submit the link to the notebook in your GitHub repository.