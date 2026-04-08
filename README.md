## 🐍 Python Code

**1. Import Libraries**
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import warnings
warnings.filterwarnings('ignore')
```

**2. KPI Calculations**
```python
total_sales = df['Sales'].sum()
avg_sales = df['Sales'].mean()
total_items_sold = df['Sales'].count()
avg_ratings = df['Rating'].mean()

print(f"Total Sales: {total_sales:,.0f}")
print(f"Avg Sales: {avg_sales:,.0f}")
print(f"Total Items Sold: {total_items_sold:,.0f}")
print(f"Avg Ratings: {avg_ratings:,.1f}")
```

**3. Sales by Fat Content**
```python
sales_by_fat = df.groupby('Item Fat Content')['Sales'].sum()
plt.pie(sales_by_fat, labels=sales_by_fat.index, 
        autopct='%1.1f%%', startangle=90)
plt.title('Total Sales by Fat Content')
plt.show()
```

**4. Sales by Item Type**
```python
sales_by_type = df.groupby('Item Type')['Sales'].sum()
               .sort_values(ascending=False)
plt.figure(figsize=(10, 6))
plt.bar(sales_by_type.index, sales_by_type.values)
plt.xticks(rotation=45)
plt.title('Sales by Item Type')
plt.show()
```

**5. Sales Trend by Year**
```python
sales_by_year = df.groupby('Outlet Establishment Year')
                ['Sales'].sum().sort_index()
plt.figure(figsize=(9, 5))
plt.plot(sales_by_year.index, sales_by_year.values, 
         marker='o', linestyle='-')
plt.title('Sales Trend by Outlet Establishment Year')
plt.show()
```
