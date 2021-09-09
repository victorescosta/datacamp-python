1 - Getting started in Python
=
---
- [ ] Dive into Python

Modules - Help to group together related tools in python (matplotlib, pandas, scikit-learn, scipy, nlkt)

- We must import modules if we want to use. First step
`import pandas as pd ` add an alias in a module, use `as` 
`from matplotlib import pyplot as plt` 
- There's standard alias for each module

---
- [ ] Creating variables

`name = bayes`
- variables must start with a letter (usually lowercase)
- after first letter, we can use letters, numbers, underscores
- no space or special characters
- are case sensitive
- invalid variable name (name-this, 42bayes)
- variables types (two of them, floats and strings)

Common string errors
- without quotes
- mixing quotes

---

- [ ] Fun with functions

``` 
import pandas as pd
from matplotlib import pyplot as plt

df = pd.read_csv('letter_frequency.csv')

plt.plot(df.letter_index, df.frequency, label='Ransom') // positional and keyword argument
plt.show()

```
- fuction is an action 

positional arguments:
- order matters
- inputs to a function

keyword argument:
- comes after positional argument
- start with the name of the argument then an equals sign
- followed by an argument

Common function erros:
- missing commas between arguments
- missing closed parenthesis

2 - Loading Data in pandas
=
---
- [ ] What is pandas?

- module for working with tabular data
- search for particular rows and columns
- loading tabular data from different resources
- calculate aggregate statistics
- combining data from different sources
- pandas and dataframe

```
import pandas as pd
df = pd.read_csv('ransom.csv') // csv into dataframe

print(df)

df.head() // head method. first 5 rows of a df.

print(df.head())

df.info()

print(df.info()) // rows, columns, data types
```


---
- [ ] Selecting columns

- Working with columns (all the values from a particular one)

why selecting columns?
- Use in calculation `credit_records.price.sum() // select the column price and give its sum`
- Plot data ` plt.plot(ransom['letter'], ransom['frequency']) // frequencies of each letter in the ransom note` 

Use column name string to select a column
`suspect = credit_records['suspect']` 
`print(suspect) // see all values from a particular column`

Letters, numbers and underscorde > dot notation

`price = credit_records.price // we dont use quotation marks`
`print(price)`

Common errors selecting columns:
- when column name contains special characters or space, you must use bracket and string notation
- forget to put quotation marks around the string `credit_report[location] // WRONG`
- Brackets NOT parenthesis (using dataframe as a function error)



---
- [ ] Selecting rows with logic

How to select specific rows

Logical statements in python

` question == solution `
True / False - Boolean
/> < >= <= !=

` credit_records.price > 20.00 ` see in that column if some of the output returns something greater than 20.00

` credit_records[credit_records.price > 20.00] ` selects only the rows whether the statement is true

` credit_records[credit_records.suspect == 'Ronald Fisher']` shows only rows contained the name of the suspect

3 - Plotting Data with matplotlib
=

- [ ] Creating line plots

- matplotlib

Transform dataframe into two-dimensional line plot

Importing matplot lib:
`from matplotlib import pyplot as plt`

create and display our line plot:

```
plt.plot(x_value, y_value)

plt.show()
```
function name / first positional argument / second positional argument
only .plot doesn't show anything, because you can do another modifications to later show in the .show

- Plot multiple lines:
```
plt.plot(data1.x_values,
		data1.y_values)

plt.plot(data2.x_values,
		data2.y_values)

plt.show()
```



- [ ] Adding text to plots

- Axes and title labes:
`plt.xlabel("Letter") horiXzontal Axis / use ylabel to vertYcal`
`plt.title("Title") // giving a title` 
They must be before *plt.show()*
  
  
  - Adding a legends:
  ```
  plt.plot(aditya.days,
  			aditya.cases,
			label="Aditya")

  plt.plot(deshaun.days,
  			deshaun.cases,
			label="Deshaun")
			
  plt.plot(mengfei.days,
  			mengfei.cases,
			label="mengfei")
  
  plt.legend()
  ```

- Adding arbitrary text:
```
plt.text(xcoord,
		ycoord,
		"Text Message")
		
plt.text(5,
		9,
		"Unusually low H frequency!")
``` 

- Modifying text
	- change font size ` plt.title("Plot title", fontsize=10)`
	- change font color ` plt.legend(color="green")` 
[colors allowed](https://en.wikipedia.org/wiki/Web_colors)



- [ ] Styling graphs

- Changing line color

```
plt.plot(x, y1, color="tomato")
plt.plot(x, y2, color="orange")
plt.plot(x, y3, color="goldenrod")
```
 
 - Changing line width
 ```
 plt.plot(x, y1, linewidth=1)
 plt.plot(x, y2, linewidth=2)
 plt.plot(x, y2, linewidth=3)
 
 default = 1
 ```

- Changing line style
``` 
plt.plot(x, y1, linestyle='-')
plt.plot(x, y2, linestyle='--')
plt.plot(x, y3, linestyle='-.')
plt.plot(x, y4, linestyle=':')
``` 

- Adding markers

```
plt.plot(x, y1, marker='x')
plt.plot(x, y2, marker='s')
plt.plot(x, y3, marker='o')
plt.plot(x, y4, marker='*')
plt.plot(x, y5, marker='h')
```

- Setting a style

```
plt.style.use('fivethirtyeight')
plt.style.use('ggplot')
plt.style.use('seaborn')
plt.style.use('default')
```



---

4 - Different Types of Plots
=
- [ ] Making a scatter plot

- Scatterplot allow us to see each point a data is
- Creating a scatter plot and label it `plt.scatter(df.age, df.height)`
```
plt.xlabel('Age(in months)')
plt.ylabel('Height (in inches)')

plt.show()
```

- Keywords arguments
```
plt.scatter(df.age, df.height,
		colo='green',
		marker='s')

```

- Changing marker transparency (small alpha, more transparent)
```
plt.scatter(df.x_data,
		df.y_data,
		aplha=0.1)
```
- [ ] Making a bar chart (visualizing categorical data)
- labels of each bar and heights of each bar (x axis is labeled by us and we only need to add ylabel). vertical and horizontal

```
plt.bar(df.precinct,
		df.pets_abducted)

plt.ylabel('Pet Abductions')
plt.show()

Horizontal bar chart:

plt.barh
```

- Adding error bars
```
plt.bar(df.precinct, df.pet_abductions,
		yerr=df.error)

plt.ylabel('Pet Abductions')
plt.show()
```

- Stacked bar charts
```
plt.bar(df.precinct, df.dog)

plt.bar(df.precinct, df.cat,
	bottom=df.dog)
	
plt.bar(df.precinct, df.dog)

```

Complete code:
```
plt.bar(df.precinct, df.dog,
	label='Dog')

plt.bar(df.precinct, df.cat,
	bottom=df.dog,
	label='Cat')
	
plt.legend()
plt.show()
``` 
- [ ] Making a histogram
  
  - Histogram with matplotlib
  ```
  plt.hist(gravel.mass)
  
  plt.show()
  ``` 
- Changing bins
```
plt.hist(data, bins=nbins)

plt.hist(gravel.mass, bins=40)
```
- Changing range (min max)

```
plt.hist(data,
		range=(xmin, xmax))
```

- Normalizing
```
plt.hist(male_weight, density=True)
plt.hist(female_weight, density=True)
```
---




