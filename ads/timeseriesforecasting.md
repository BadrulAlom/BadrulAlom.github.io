---
layout: default
---

# Time series forecasting in PySpark

Nov 2018

I have been playing around with time-series forecasting problems using PySpark & Databricks and here are some useful bits of code I wanted to document:

## Data Preparation

Preparing the data for time series problems is always the most painful part. There isn't yet a reliable time-series library that one can use in PySpark that does what Pandas can do.

<b> To load data from Azure BLOB in PySpark data frame</b>
<code>
storage_account_path = "fs.azure.sas.FolderName.ResourceGroup.blob.core.windows.net"
sas_token = "?sv=2018-03-28&ss=bfqt&srtXXXXXXXXXXXX3D"
spark.conf.set(storage_account_path,sas_token)
tmp = spark.read.format(file_type).options(header='true', quote='"', delimiter=fileDelimiter,ignoreLeadingWhiteSpace='true',inferSchema='true').load(file_location)</code>

<b> Forcing data to be of a certain data type</b>

You might find there's no need to do this, PySpark is generally good at detecting the correct data types but here are some examples if you do need to do it:
<code>
df= df.withColumn(amountCol, df[amountCol].cast(DoubleType()))

df= df.withColumn(transactionDateCol, df[transactionDateCol].cast(TimestampType()))
</code>

<b> Group by and Filtering</b>

The following aggregates the min and max transaction dates, and sums up the amount.

<code>tmp=df.groupBy('GroupByFld').agg(fn.min('adjTransactionDate').alias('minTransactionDate'),fn.max('AdjTransactionDate').alias('maxTransactionDate'),fn.sum('Amount').alias('Amount'))
</code>

The following selects data where GroupByFld = 1 or 2

<code>
tmp=tmp.filter((tmp['GroupByFld']== 1) | (tmp['GroupByFld'] == 2))
</code>