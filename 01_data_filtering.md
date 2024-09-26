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

**2. Find all the largest cities in Vietnam**
```py
vietnam = df[df["Country"]== "Vietnam"]
print("Largest Cities in Vietnam", vietnam)
```

**3. Find Cities in China that are growing in population in 2024 (positive growth)**
```py
china_growing_cities = df[(df["Country"]== "China") & (df["Growth Rate"] > 0)]
print("Growing Cities in China", china_growing_cities)
```

**4. Calculate the total population of the largest cities in India**
```py
# Method 1
cities_india = df[df["Country"]== "India"]
total_pop = cities_india["Population (2024)"].sum()
print("Sum of largest in India =", total_pop)

# Method 2
cities_india = df[df["Country"]== "India"] ["Population (2024)"].sum()
print("Sum of largest in India =", cities_india)
```

**5. Find cities experiencing a population decline and calculate their growth median**
```py
decline_median = df[df["Growth Rate"] < 0] ["Growth Rate"].median()
print("Decline Median Cities =", decline_median)
```

**6. Find the growing cities in China and calculate the minimum population they had in 2023**
```py
min_pop_china = df[(df["Country"] == "China") & (df["Growth Rate"] > 0)] ["Population (2023)"].min()
print("Min. Pop. in China in 2023 =", min_pop_china)
```
---