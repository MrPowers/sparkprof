# Creating Spark DataFrames from CSVs

You can create a Spark DataFrame from one or many CSV files.

This page shows you how to read CSV files into a Spark DataFrame and explains the limitations of the CSV file format.

You will learn why it is often wise to convert from CSV to another file format that's better for analytical workflows.

## Read a single CSV file into a Spark DataFrame

Suppose you have the following `data/students.csv` file:

XXX

You can read this CSV into a Spark DataFrame as follows:

```
df = spark.read.format("csv").option("header", True).load("data/students.csv")
```

Print the contents of the DataFrame to make sure it was properly read:

```
df.show()

XXX
```

It's also easy to read multiple CSV files into a DataFrame.

## Read multiple CSVs files into a Spark DataFrame

Suppose you have a `data/orders` folder with multiple CSV files as follows:

```
data/orders/
  file1.csv
  file2.csv
  files3.csv
```

Here's how to read all of the CSV files into a Spark DataFrame:

```
df = spark.read.format("csv").option("header", True).load("data/orders")
```

Print the contents of the DataFrame to make sure it was properly read:

```
df.show()

XXX
```

Spark reads all of the files in a folder.

## Read CSV files without headers

You can also read CSV files without headers by manually specifying the schema of the underlying data.

Suppose you have a CSV file as follows:

```
TODO
```

Here's how to read this CSV file into a Spark DataFrame and manually specify the column names.

```python
schema = StructType([
  StructField("first_name", StringType(), true),
  StructField("last_name", StringType(), true),
  StructField("age", IntegerType(), true),
])
df = spark.read.format("csv").schema(schema).option("header", True).load("data/orders")
```

Here's the Spark DataFrame:

```
df.show()

XXX
```

## Manually specify schema when reading CSV files

You can also manually specify the schema when reading CSV files that have headers.

This is useful if you would like to use different column names or different column types than what Spark infers.

Suppose you have the following CSV file with a header row:

XXX

Here's how to manually specify the schema, even though a header row exists.

XXX


## Limitations of CSV files

* CSV files are easily corruptible
* CSV files aren't standard
* Row-oriented nature of CSV files can lead to bad query performance
* Hard to compress


## Limitations of CSV data lakes



## CSV alternatives




