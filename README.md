

---

# Zomato Dataset Analysis

This project focuses on analyzing a dataset of restaurants from Zomato. The dataset provides insights into various features like online ordering availability, restaurant ratings, approximate cost, and more. The analysis includes graphical visualizations to better understand the data.

## Project Structure

- **zomato_data.csv**: The dataset file used for analysis.
- **analysis.ipynb**: The Jupyter Notebook containing the complete analysis code.
- **README.md**: This file, providing an overview of the project and how to run it.

## Requirements

To run the analysis, you will need the following Python libraries:
- `pandas`: For data manipulation and analysis.
- `matplotlib`: For creating plots and visualizations.
- `seaborn`: For advanced data visualizations.

### Installing Dependencies

You can install the required libraries via pip:

```bash
pip install pandas matplotlib seaborn
```

## Dataset Overview

The dataset used in this project includes the following columns:

- **name**: Name of the restaurant.
- **online_order**: Indicates if the restaurant provides an online order option (Yes/No).
- **book_table**: Specifies if table booking is available (Yes/No).
- **rate**: Average rating of the restaurant (out of 5).
- **votes**: Number of customer votes the restaurant has received.
- **approx_cost(for two people)**: Approximate dining cost for two people.
- **listed_in(type)**: Category or type of restaurant (e.g., Buffet, Cafes, Dining, etc.).

## Analysis and Visualizations

The analysis is performed using `pandas` for data processing, and `matplotlib` & `seaborn` for creating visualizations. Key aspects of the analysis include:

### 1. Online Order Availability

The following code analyzes how many restaurants offer online ordering and visualizes it:

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
df = pd.read_csv('zomato_data.csv')

# Count of restaurants offering online orders
online_order_count = df['online_order'].value_counts()

# Plot the result
plt.figure(figsize=(8, 5))
sns.barplot(x=online_order_count.index, y=online_order_count.values, palette='coolwarm')
plt.title('Restaurants Offering Online Orders')
plt.xlabel('Online Order Availability')
plt.ylabel('Count of Restaurants')
plt.show()
```

### 2. Restaurant Ratings Distribution

You can also analyze the distribution of restaurant ratings using the following code:

```python
# Distribution of ratings
plt.figure(figsize=(8, 5))
sns.histplot(df['rate'].dropna(), bins=20, kde=True, color='blue')
plt.title('Distribution of Restaurant Ratings')
plt.xlabel('Ratings')
plt.ylabel('Frequency')
plt.show()
```

### 3. Approximate Cost Analysis

This code helps to analyze the approximate cost for two people in different restaurant types:

```python
# Analyzing the approximate cost
plt.figure(figsize=(10, 6))
sns.boxplot(x='listed_in(type)', y='approx_cost(for two people)', data=df, palette='Set2')
plt.xticks(rotation=45)
plt.title('Approximate Cost for Two People by Restaurant Type')
plt.xlabel('Restaurant Type')
plt.ylabel('Approximate Cost (for two people)')
plt.show()
```

## Running the Analysis

Follow these steps to run the analysis:

1. **Clone the repository or download the project files.**
   
   ```bash
   git clone <repository-link>
   ```

2. **Install the required Python libraries.**
   
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Jupyter Notebook.**
   
   Open the Jupyter Notebook (`analysis.ipynb`) and run the cells to perform the analysis and generate the visualizations.

## Visualizations

Here’s an example of the visualization generated for online order availability:

![Online Order Availability](online_order_chart.png)

This shows how many restaurants provide the option to order online, with a clear breakdown between "Yes" and "No" responses.

## Conclusion

This analysis helps us better understand the trends in restaurant services (online ordering, ratings, cost), using data from Zomato. The visualizations provide an intuitive grasp of these patterns and can help in making informed decisions for both consumers and businesses.

## License

This project is open-source and is available under the MIT License. Feel free to use, modify, and share it as per your needs.

---

### Instructions:
- Save this content as `README.md` in your project directory.
- Replace any placeholders like `<repository-link>` with actual links if necessary.
- If you have saved any plots (e.g., `online_order_chart.png`), make sure they are included in the project folder and linked correctly.

This file provides clear instructions on project structure, installation, dataset overview, and running the analysis with examples.
