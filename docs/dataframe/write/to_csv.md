# Writing Spark DataFrames to CSVs

It's easy to write a Spark DataFrame to one or many CSVs.  This post will show you how to do both and explain the limitations of writing a dataset to a single file.

## Write Spark DataFrame to CSVs

Create a Spark DataFrame and then write it out to CSV files:

```python
data = [
  ("bob", "lob", 42),
  ("jose", "cuervo", 75),
  ("some", "person", 20),
]

df = spark.createDataFrame(data, ["first_name", "last_name", "age"])

df.write.format("csv").save("some_dir")
```

Here are the contents of `some_dir`:

XXX

Spark intentionally outputs DataFrames to multiple files.

Outputting a DataFrame to multiple files lets Spark write many files in parallel which is faster and scalable.  Writing to a single file is slower and can't scale to large datasets.



## Write Spark DataFrame to CSVs without headers



## Write Spark DataFrame to a single CSV





