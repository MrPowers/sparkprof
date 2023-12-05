# Gentle introduction to Spark DataFrames

This section provides a gentle introduction to Spark DataFrames.

You will learn how to create DataFrames, perform basic operations, and some of the advantages offered by Spark.

## Create a SparkSession

You need to create a `SparkSession` to perform operations with Spark.

Some managed Spark service providers create the `SparkSession` for you so you can access it via the `spark` variable without creating it for yourself.

Here's how you can make a `SparkSession` yourself for localhost workflows:

```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.getOrCreate()
```

## Create a DataFrame

Here is how to create a Spark DataFrame with `first_name`, `last_name`, and `age` columns:

```python
data = [
  ("bob", "lob", 42),
  ("jose", "cuervo", 75),
  ("some", "person", 20),
]

df = spark.createDataFrame(data, ["first_name", "last_name", "age"])
```

The Spark DataFrame object is created with rows of data and the column names.

Display the contents of the DataFrame to make sure it's been properly created:

```python
df.show()

XXX
```

Now let's see how to perform operations on the DataFrame.

## Filter a DataFrame

Here is how to filter out all the rows in the DataFrame with an age less than 21 years old.

```python
from pyspark.dataframe import col

filtered_df = df.filter(col("age") < 21)
filtered_df.show()

XXX
```

Notice that the original `df` is unchanged, even after the filtering operation has been run:

```
df.show()

XXX
```

## Add column to a DataFrame

Now let's add a `full_name` column to the DataFrame that concatenates the `first_name` and `last_name` columns.

```
from pyspark.dataframe import concat_ws

res_df = df.withColumn("full_name", concat_ws(" ", col("first_name"), col("last_name")))

res_df=show()

XXX
```

The `withColumn` method makes it easy to add columns to the DataFrame.

## Query the DataFrame with SQL

You can also easily query the DataFrame with SQL.  Let's run the same filtering query as before, but with SQL:

```python
res_df = spark.sql("select * from {df} where age > 21", df=df)
```

```
res_df.show()

XXX
```

## Join a DataFrame

It's easy to join two DataFrames.  Let's create one DataFrame with `id` and `country` columns:

XX

Now create another DataFrame with `id` and `favorite_sport` columns:

XX

Join the two DataFrames and observe the result:

XX

## Write a DataFrame

Let's write the joined DataFrame as Parquet files.

```python
df.write.format("parquet").save("some_folder")
```

Persisting the DataFrame in storage allows it to be easily accessed at a later time.

## Conclusion

This guide showed you how to create a Spark DataFrame, run basic data operations (filtering, querying, joining) and how to write the DataFrame to storage.

Spark is powerful because it is great for small and large datasets.  The rest of this guide will explain the power of Spark for single-node, localhost workflows and for large data processing tasks for computation clusters.

