# Data Filtering

***- There are six scenarios in which [dataset](https://www.kaggle.com/datasets/ibrarhussain123/world-largest-cities-by-population-2024) was filtered by applying different conditions using pandas.***

```py
# Import library
import pandas as pd

# Creata a dataframe
df = pd.read_csv("data.csv")

# General data info
print(df.info())
print(df.head())
print(df.tail())
print(df.describe())
```

## Scenarios

**1. Find cities with a population greater than 20 million**

```py
large_cities = df[df["Population (2024)"] > 20000000]
print("Cities > 20 Million:", large_cities)
```