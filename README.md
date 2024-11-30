# Data Visualization with Python

This script demonstrates data visualization techniques using Python's powerful libraries: **Pandas**, **Matplotlib**, and **Seaborn**. The dataset used is the popular `tips.csv`, which contains information about restaurant tips.

---

## Features
- **Scatter Plots**: Visualize relationships between variables with optional enhancements like color and size.
- **Line Plots**: Track trends over time or sequential data.
- **Bar Charts**: Compare categories using bar heights.
- **Histograms**: Show the distribution of a numeric variable.
- **Seaborn Enhanced Visualizations**: Add advanced aesthetics to plots, such as KDE (Kernel Density Estimation) overlays and grouping by categorical variables.

---

## Dataset Overview
The `tips.csv` dataset includes:
- **Total Bill**: The total amount of the bill.
- **Tip**: The tip given by customers.
- **Sex**: Gender of the customer.
- **Smoker**: Indicates whether the customer was a smoker.
- **Day**: Day of the week.
- **Time**: Time of the meal (Lunch or Dinner).
- **Size**: Number of people in the group.

---

## Requirements
Install the required Python libraries using:
```bash
pip install pandas matplotlib seaborn numpy
```

---

## Visualizations

### 1. Scatter Plot (Basic)
Displays the relationship between **day** and **tip**:
```python
plt.scatter(data['day'], data['tip'])
```

---

### 2. Scatter Plot (Enhanced)
Enhanced scatter plot where:
- **Color** (`c`) represents the size of the group.
- **Size** (`s`) represents the total bill amount.
```python
plt.scatter(data['day'], data['tip'], c=data['size'], s=data['total_bill'])
```

---

### 3. Line Plot
Displays the **tips** and **group sizes** across all entries:
```python
plt.plot(data['tip'])
plt.plot(data['size'])
```

---

### 4. Bar Chart
Compares average tips across different days:
```python
plt.bar(data['day'], data['tip'])
```

---

### 5. Histogram
Visualizes the distribution of **total bills**:
```python
plt.hist(data['total_bill'])
```


---

### 6. Seaborn Line Plot
Tracks the relationship between **day** and **tip** with Seaborn's aesthetic enhancements:
```python
sns.lineplot(x='day', y='tip', data=data)
```


---

### 7. Seaborn Line Plot (Multiple Variables)
Plots all numeric variables except **total_bill**:
```python
sns.lineplot(data=data.drop(['total_bill'], axis=1))
```


---

### 8. Seaborn Bar Plot
Compares tips across days, grouped by gender:
```python
sns.barplot(x='day', y='tip', data=data, hue='sex')
```


---

### 9. Seaborn Histogram with KDE
Displays the distribution of **total_bill** with a KDE overlay, grouped by gender:
```python
sns.histplot(x='total_bill', data=data, kde=True, hue='sex')
```

