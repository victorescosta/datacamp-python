1 - Getting started in python
=


Exercises
---

- [ ] Dive into Python

Ex00:

Q:

In the script editor, use an import statement to import statsmodels.

Add an as statement to alias statsmodels to sm.

Add an as statement to alias seaborn to sns.


A:

import statsmodels

import statsmodels as sm

import seaborn as sns

Ex 01:

Q:

# Fix the import of numpy to run without errors
import NumPy as np


A:

import numpy as np

What did you need to change to make the import run without errors?

Whitespace matters in Python, so spaces must be removed

Python is case-sensitive, so numpy must be all lowercase - CORRECT ANSWER

Python is case-sensitive, so IMPORT must be all uppercase


---
- [ ] Creating variables

Ex00:


Q:

Define a variable called bayes_age and set it equal to 4.0.

Display the variable bayes_age.


A:

# Fill in Bayes' age (4.0)
bayes_age = 4.0


# Display the variable bayes_age

print(bayes_age)

Ex01:

Q:

Define a variable called favorite_toy whose value is "Mr. Squeaky".

Define a variable called owner whose value is 'DataCamp'.

Show the values assigned to these variables.


A:

# Bayes' favorite toy
favorite_toy = "Mr. Squeaky"


# Bayes' owner
owner = 'DataCamp'


# Display variables
print(favorite_toy)
print(owner)

Ex02:

Q:

Correct the mistakes in the code so that it runs without producing syntax
errors.


A:

# One or more of the following lines contains an error
# Correct it so that it runs without producing syntax errors
birthday = "2017-07-14"
case_id = 'DATACAMP!123-456?'


Which of the following is not a valid variable name?

my_dog_bayes

BAYES42

3dogs - CORRECT ANSWER

this_is_a_very_long_variable_name_42


---
- [ ] Fun with functions

Ex00:


Q:

Use pd.read_csv to load data from a CSV file called ransom.csv. This file
represents the frequency of each letter in the ransom note for Bayes.

A:

# Import pandas
import pandas as pd


# Load the 'ransom.csv' into a DataFrame
r = pd.read_csv('ransom.csv')


# Display DataFrame
print(r)


Ex01:


Q:

Correct the code so that it runs without syntax errors


A:

# One or more of the following lines contains an error
# Correct it so that it runs without producing syntax errors

# Plot a graph
plt.plot(x_values, y_values)

# Display the graph
plt.show()

Ex02:

Q:

Create a variable called plate that represents the observed license plate:

the first three letters were FRQ, but the witness couldn't see the final 4

letters. Use asterisks (*) to represent missing letters.


A:

# Define plate to represent a plate beginning with FRQ
# Use * to represent the missing four letters
plate = 'FRQ****'


Ex03:


Q:

Call lookup_plate() using the variable plate.


A:

# Call the function lookup_plate()
lookup_plate(plate)


Ex04:


Q:

Calling lookup_plate() with the license plate FRQ**** produced too many results.

Luckily, lookup_plate() also accepts a keyword argument: color. Use the color of
the car ('Green') to get a smaller list.


A:

# Call lookup_plate() with the keyword argument for color
lookup_plate(plate, color='Green')

---

2 - Loading Data in pandas
=

---
- [ ] What is pandas?

Ex00:


Q:
Import the pandas module under the alias pd.

Load the CSV "credit_records.csv" into a DataFrame called credit_records.

Display the first five rows of credit_records using the .head() method.


A:
# Import pandas under the alias pd
import pandas as pd

# Load the CSV "credit_records.csv"
credit_records = pd.read_csv('credit_records.csv')

# Display the first five rows of credit_records using the .head() method
print(credit_records.head())

Ex01:

Q:
Use the .info() method to inspect the DataFrame credit_records

A:
# Use .info() to inspect the DataFrame credit_records
print(credit_records.info())

How many rows are in credit_records?

103

104 - CORRECT

5

64


---
- [ ] Selecting columns

Ex00:

Q:

Select the column item from credit_records using brackets and string notation.

Select the column item from credit_records using dot notation.


A:
# Select the column item from credit_records
# Use brackets and string notation
items = credit_records['item']

items = credit_records.item


# Display the results
print(items)


Ex01:


Q:

Correct the code so that it runs without errors.


A:
# One or more lines of code contain errors.
# Fix the errors so that the code runs.

# Select the location column in credit_records
location = credit_records['location']

# Select the item column in credit_records
items = credit_records.item

# Display results
print(location)

Ex02:

Q:

Inspect the DataFrame mpr using info()

A:
# Use info() to inspect mpr
print(mpr.info())

Q:

Correct the mistakes in the code so that it runs without errors.

A:

# The following code contains one or more errors
# Correct the mistakes in the code so that it runs without errors

# Select column "Dog Name" from mpr
name = mpr['Dog Name']

# Select column "Missing?" from mpr
is_missing = mpr['Missing?']

# Display the columns
print(name)

print(is_missing)


Q:

Why did this code generate an error?

name = mpr.Dog Name


A:

We need to remove the space in Dog Name.

If a column name has capital letters, then it needs to be in brackets and
string notation. - WRONG. Capital letters can use this type of notation

If a column name contains a space, then it needs to be in brackets and string
notation. - CORRECT


---
- [ ] Selecting rows with logic

Ex00:

Q:
The variable height_inches represents the height of a suspect. Is height_inches
greater than 70 inches?


The variable plate1 represents a license plate number of a suspect. Is it equal
to FRQ123?


The variable fur_color represents the color of Bayes' fur. Check that fur_color
is not equal to "brown".



A:
# Is height_inches greater than 70 inches?
print(height_inches > 70)
# Is plate1 equal to "FRQ123"?
print(plate1 == "FRQ123")
# Is fur_color not equal to "brown"?
print(fur_color != "brown")

Ex01:

A:

Select the dogs where Age is greater than 2.

Select the dogs whose Status is equal to Still Missing.

Select all dogs whose Dog Breed is not equal to Poodle.


Q:
# Select the dogs where Age is greater than 2
greater_than_2 = mpr[mpr.Age > 2]

print(greater_than_2)


# Select the dogs whose Status is equal to Still Missing
still_missing = mpr[mpr.Status == 'Still Missing']

print(still_missing)


# Select all dogs whose Dog Breed is not equal to Poodle
not_poodle = mpr[mpr['Dog Breed'] != 'Poodle']

print(not_poodle)


Ex02:


Q:

Select rows of credit_records such that the column location is equal to 'Pet
Paradise'.


A:
# Select purchases from 'Pet Paradise'
purchase = credit_records[credit_records.location == 'Pet Paradise']

# Display
print(purchase)

Q:
Which suspects purchased pet supplies before the kidnapping?

A:
Fred Frequentist and Ronald Aylmer Fisher

Gertrude Cox and Kirstine Smith

Fred Frequentist and Gertrude Cox - CORRECT

Ronald Aylmer Fisher and Kirstine Smith

---
3 - Plotting data with matplotlib
=

- [ ] Creating line plots

Ex00:

Q:
From matplotlib, import the module pyplot under the alias plt
Plot Officer Deshaun's hours worked using the columns day_of_week and
hours_worked from deshaun.
Display the plot.


A:
# From matplotlib, import pyplot under the alias plt

from matplotlib import pyplot as plt
# Plot Officer Deshaun's hours_worked vs. day_of_week


plt.plot(deshaun.day_of_week, deshaun.hours_worked)


# Display Deshaun's plot


plt.show()

Ex01:

Q:


Plot Officer Aditya's time worked with day_of_week on the x-axis and
hours_worked on the y-axis.

Plot Officer Mengfei's time worked with day_of_week on the x-axis and
hours_worked on the y-axis.


A:

# Plot Officer Deshaun's hours_worked vs. day_of_week

plt.plot(deshaun.day_of_week, deshaun.hours_worked)


# Plot Officer Aditya's hours_worked vs. day_of_week

plt.plot(aditya.day_of_week, aditya.hours_worked)


# Plot Officer Mengfei's hours_worked vs. day_of_week

plt.plot(mengfei.day_of_week, mengfei.hours_worked)


# Display all three line plots

plt.show()

One of the officers was removed from the investigation on Wednesday because of
an emergency at a different station house. That office did not return on
Thursday or Friday. Which color line represents that officer?

blue

green

orange   - CORRECT


- [ ] Adding text to plots

Ex00:

Q:
Using the keyword label, label Deshaun's plot as "Deshaun".
Add labels to Mengfei's ("Mengfei") and Aditya's ("Aditya") plots.
Nothing is displaying yet! Add a command to make the legend display.


A:

# Add a label to Deshaun's plot

plt.plot(deshaun.day_of_week, deshaun.hours_worked, label="Deshaun")


# Officer Aditya

plt.plot(aditya.day_of_week, aditya.hours_worked, label="Aditya")


# Officer Mengfei

plt.plot(mengfei.day_of_week, mengfei.hours_worked, label="Mengfei")

# Add a command to make the legend display

plt.legend()


# Display plot

plt.show()


One of the officers did not start working on the case until Wednesday. Which
officer?


Deshaun

Aditya

Mengfei  - CORRECT ANSWER


Ex01:

Q:

Add a descriptive title to the chart.

Add a label for the y-axis.

A:

# Lines

plt.plot(deshaun.day_of_week, deshaun.hours_worked, label='Deshaun')

plt.plot(aditya.day_of_week, aditya.hours_worked, label='Aditya')

plt.plot(mengfei.day_of_week, mengfei.hours_worked, label='Mengfei')


# Add a title

plt.title("Official's hours worked")


# Add y-axis label

plt.ylabel("Hours worked")


# Legend

plt.legend()

# Display plot

plt.show()


Ex02:

Q:
Place the annotation "Missing June data" at the point (2.5, 80)

A:
# Create plot

plt.plot(six_months.month, six_months.hours_worked)


# Add annotation "Missing June data" at (2.5, 80)

plt.text(2.5, 80, "Missing June data")


# Display graph

plt.show()

- [ ] Styling graphs

Ex00:

Q:


Change the color of Phoenix to "DarkCyan".

Make the Los Angeles line dotted.

Add square markers to Philadelphia.

A:

# Change the color of Phoenix to `"DarkCyan"`

plt.plot(data["Year"], data["Phoenix Police Dept"], label="Phoenix", color="DarkCyan")


# Make the Los Angeles line dotted

plt.plot(data["Year"], data["Los Angeles Police Dept"], label="Los Angeles", linestyle=':')


# Add square markers to Philedelphia

plt.plot(data["Year"], data["Philadelphia Police Dept"], label="Philadelphia", marker='s')


Ex01:

Q:

Change the plotting style to "fivethirtyeight".

Change the plotting style to "ggplot".

View all styles by typing print(plt.style.available) in the console

Pick one of those styles and see what it looks like

A:
# Change the style to fivethirtyeight / ggplot / another style

plt.style.use('fivethirtyeight')  // ggplot / another style


# Plot lines

plt.plot(data["Year"], data["Phoenix Police Dept"], label="Phoenix")

plt.plot(data["Year"], data["Los Angeles Police Dept"], label="Los Angeles")

plt.plot(data["Year"], data["Philadelphia Police Dept"], label="Philadelphia")


# Add a legend

plt.legend()


# Display the plot

plt.show()


Ex02:

Q:


Plot the letter frequencies from the ransom note. The x-values should be ransom
letter. The y-values should be ransom.frequency. The label should be the string
'Ransom'. The line should be dotted and gray.

A:

# x should be ransom.letter and y should be ransom.frequency
plt.plot(ransom.letter, ransom.frequency,
	# Label should be "Ransom"
	label="Ransom",
	# Plot the ransom letter as a dotted gray line
	linestyle=':', color='gray')

# Display the plot
plt.show()

Q:

Plot a line for the data in suspect1. Use a keyword argument to label that line
'Fred Frequentist'). // also suspect2 with Gertrude Cox

A:

# Plot each line
plt.plot(ransom.letter, ransom.frequency,
		label='Ransom', linestyle=':', color='gray')

# X-values should be suspect1.letter
# Y-values should be suspect1.frequency
# Label should be "Fred Frequentist"
plt.plot(suspect1.letter, suspect1.frequency, label="Fred Frequentist")

# Display the plot
plt.show()

Q:
Label the x-axis (Letter) and the y-axis (Frequency), and add a legend.

A:

# Plot each line
plt.plot(ransom.letter, ransom.frequency,
		label='Ransom', linestyle=':', color='gray')
plt.plot(suspect1.letter, suspect1.frequency, label='Fred Frequentist')
plt.plot(suspect2.letter, suspect2.frequency, label='Gertrude Cox')

# Add x- and y-labels
plt.xlabel("Letter")
plt.ylabel("Frequency")

# Add a legend
plt.legend()

# Display plot
plt.show()

4 - Different types of plots
=

- [ ] Making a scatter plot

Ex00:

Q:

A:



- [ ] Making a bar chart

Ex00:

Q:

A:

- [ ] Making a histogram

Ex00:

Q:

A:









---
