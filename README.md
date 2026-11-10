# Student Spending Habits

Exploratory and descriptive analysis of how 1,000 university students spend their money across ten categories, and whether spending changes with gender, year of study or major.

Completed as coursework for my BComHons in Information Systems at the University of Johannesburg, 2024.

![Average monthly spend by category](images/average_spend_by_category.png)

## Question

Where does a student's money go each month, and do spending habits differ between groups of students?

## Dataset

- **File:** `student_spending.csv`
- **Size:** 1,000 students × 17 columns (after cleaning)
- **Demographics:** age, gender, year in school, major, preferred payment method
- **Income:** monthly income, financial aid
- **Spending categories:** tuition, housing, food, transportation, books and supplies, entertainment, personal care, technology, health and wellness, miscellaneous

## Approach

1. **Cleaning:** dropped an unused index column, then checked for missing values (none), duplicates (none) and outliers using the IQR method (none). Converted text columns to the `category` type to save memory.
2. **Descriptive statistics:** summary statistics for numeric and categorical columns, plus mean, median and mode for monthly income, financial aid and entertainment.
3. **Distributions:** histograms for every spending category, and count plots for gender, year in school, major and payment method.
4. **Dispersion:** range, variance, standard deviation, quartiles, IQR, kurtosis and a boxplot for books and supplies.
5. **Group comparisons:** created a `total_monthly_expenses` column and compared average totals and per-category spend by gender, year in school and major.

## Key findings

**Tuition dominates the budget.** It makes up 72% of average monthly spending, followed by housing at 11%. All the other categories together account for the remaining 17%.

| Group | Highest average total spend | Lowest average total spend |
|---|---|---|
| Gender | Male: 6,341 | Female: 6,279 |
| Year in school | Junior: 6,377 | Senior: 6,273 |
| Major | Psychology: 6,455 | Engineering: 6,234 |

- The most common payment method is a mobile payment app (350 students), ahead of cards and cash.
- Freshmen in engineering, computer science and biology spend the most on books and supplies. Among psychology students, juniors spend the most.
- Average monthly income is about 1,021 and average financial aid about 505, both far below average spending. This suggests most students rely on other funding, such as family support or loans, which the dataset doesn't capture.

![Books and supplies spend by major and year](images/books_supplies_by_major_and_year.jpg)

## Reflection and next steps

- The differences between groups are small. Psychology students spend only about 3.5% more than engineering students, so a significance test such as ANOVA would show whether any of these gaps are real.
- Mean and median are almost identical for income, financial aid and entertainment, and kurtosis for books and supplies is −1.2. Together these suggest the distributions are closer to flat (uniform) than skewed, which is worth checking before modelling.
- Next I'd look at spending as a share of income per student, and at whether payment method relates to spending on entertainment and technology.
- I also compared doing this analysis in Excel and in Python. Python made the tables and charts much quicker to build.

## How to run

```bash
git clone https://github.com/NJNteso/student-spending-habits.git
cd student-spending-habits
pip install -r requirements.txt
jupyter notebook student_spending_analysis.ipynb
```

Note: the interactive Plotly charts don't render in GitHub's notebook preview. Run the notebook locally to see them.

## Tools

Python · pandas · NumPy · Matplotlib · seaborn · Plotly

---

**Nyakallo Joy Nteso** · Data & Business Analyst · [GitHub](https://github.com/NJNteso)
