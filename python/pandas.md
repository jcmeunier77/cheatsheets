# Pandas basics

### Basic methods:

```Python
df.head() # Show the first few rows of a DataFrame.
df.tail() # Show the last few rows of a DataFrame.


df.shape # Get the dimention (x, y) of a Dataframe (like Numpy).
df.columns.tolist() # Get a list of the Dataframe's columns.


# Summary statistics of the Series/Dataframe provided.
df.describe()
# count: Count number of non-NA/null observations.
# max: Maximum of the values in the object.
# min: Minimum of the values in the object.
# mean: Mean of the values.
# std: Standard deviation of the observations.

# The following return the same as df.describe, and can be applied on all dataframe, or on a column:
df.max()
df['column'].max()
df['value'].idxmax() # Return the index of the max value in a column.

df.min()
df['column'].min()
df['column'].idxmin() # Return the index of the min value in a column.

df.mean()
df['column'].mean()

# Useful: Shows how many times each item appears in the column.
df['column'].value_counts()
```

### Accessing values - iloc:

**iloc** is definitely one of the most important functions. Generally, you want to use it whenever you have the integer index of a certain row (or a list of integer indexes) that you want to access.

```Python
# Best practice: pass a list to iloc.
df.iloc[[144]] # Return the row @ index 144.

# Using basic method to access specific values:
df.iloc[ [df['column1'].idxmax()] ]['column2'] # We retrieve the row index of 'column1's maximum value, to access its corresponding 'column2'.
# Note: the type of returned value is: "pandas.core.series.Series".

```
