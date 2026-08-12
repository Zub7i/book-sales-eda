# 📚 Global Book Sales & Ratings Analysis

## 📌 Overview
An Exploratory Data Analysis (EDA) of global book sales, revenue performance, author rating tiers, and historical publishing trends from 1900 through 2020. This project analyzes price-demand dynamics, top publisher revenue drivers, and author performance using Python.

---

## 🛠️ Tools & Libraries Used
* **Python**
* **Pandas** — Data manipulation and aggregation
* **Matplotlib & Seaborn** — Data visualization and plotting

---

## 📊 Key Insights & Findings

### 1. Price Elasticity & Demand
* Lower-priced books ($15 or less) account for the vast majority of high-volume sales. High unit sales (>20,000 units) are almost exclusively concentrated in this lower price range.

### 2. Language & Publisher Distribution
* **Language Concentration:** Standard English (`eng`) and US English (`en-US`) dominate the dataset, accounting for **95.2%** of all titles combined.
* **Top Publisher Revenue:** **Penguin Group (USA) LLC** generated the highest overall publisher revenue (~$191,581), followed by **Random House LLC** (~$174,956) and **Amazon Digital Services, Inc.** (~$141,768).

### 3. Historical Sales Trajectory (1900–2020)
* **1900–1970s:** Sales volume remained low and flat, typically under 100,000 units per year.
* **1980s–1990s:** Sales volume began a steady upward trend, crossing 200,000 units annually.
* **Post-2000 Peak:** Growth accelerated sharply, reaching an **all-time peak exceeding 750,000 units sold around 2012**, alongside higher year-over-year sales volatility.

### 4. Author Rating Tiers
* **Excellent Tier:** Delivers the highest overall sales performance, with both the highest median unit sales and a wide upper quartile distribution.
* **Intermediate Tier:** Maintains a modest baseline median, but features a dense cluster of extreme upper-bound outliers driving massive sales.

---

## 🏆 Top 5 Publishers by Revenue

| Rank | Publisher | Total Revenue ($) |
| :---: | :--- | :---: |
| 1 | **Penguin Group (USA) LLC** | 191,581.10 |
| 2 | **Random House LLC** | 174,956.24 |
| 3 | **Amazon Digital Services, Inc.** | 141,767.77 |
| 4 | **HarperCollins Publishers** | 121,769.81 |
| 5 | **Hachette Book Group** | 107,410.97 |

---

## 💻 Sample Code Snippets

```python
import matplotlib.pyplot as plt
import seaborn as sns

# 1. Historical Sales Trend Line Chart
yearly_sales = df.groupby("Publishing Year")["units sold"].sum()

plt.figure(figsize=(10, 5))
yearly_sales.plot(kind="line", marker="x")
plt.xlabel("Publishing Year")
plt.ylabel("Total Units Sold")
plt.title("Total Units Sold Over The Years")
plt.grid(True, linestyle="--", alpha=0.5)
plt.show()

# 2. Author Rating Tier Performance Boxplot
sns.boxplot(x="Author_Rating", y="units sold", data=df)
plt.title("Box Plot of Units Sold for Each Author Rating")
plt.show()
