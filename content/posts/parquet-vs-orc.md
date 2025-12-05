---
title: "Parquet vs ORC — My Findings"
date: 2025-11-27T22:00:00+05:30
draft: false
tags: ["Spark", "Parquet", "ORC"]
categories: ["Articles"]
---

## Table Example

| Format  | Compression | Read Speed |
|---------|------------|------------|
| Parquet | Snappy     | Fast       |
| ORC     | Zlib       | Very Fast  |

## Code Snippet

```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("Demo").getOrCreate()
df = spark.read.parquet("data.parquet")
df.show()

graph LR
A[Raw Data] --> B[Parquet Files]
A --> C[ORC Files]
B --> D[Spark ETL]
C --> D
D --> E[Analytics]
