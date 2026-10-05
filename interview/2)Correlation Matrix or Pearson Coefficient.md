- Q) What is correlation between columns or Correlation matrix or Pearson coefficient and How to visualize and draw conclusions

### Correlation (`corr(numeric_only=True)`)

- `corr()` calculates the correlation between **numerical columns only**.
- It ignores non-numeric columns and calculates correlation only among the numeric columns.
- `df.corr()` → does not work.`df.corr(numeric_only=True)` works
> **Correlation coefficient (Pearson coefficient):** A number between **-1 and +1** that measures the **strength and direction of a linear relationship** between two numerical variables.
> **Correlation Matrix:** A table showing the **Pearson correlation coefficient** between every pair of numerical columns.

|              | Age  | Salary | Experience |
|--------------|------|--------|------------|
| **Age**      | 1.00 | 0.99   | 1.00       |
| **Salary**   | 0.99 | 1.00   | 0.98       |
| **Experience** | 1.00 | 0.98   | 1.00       |


```text
-1                 0                 +1
│------------------│------------------│
strong negative    no linear          strong positive
                   relationship

Correlation: pearson co-eficient
- +1 → perfect positive linear relationship (directly propositional)
-  0 → no linear relationship (no relationship / less dependency)
- -1 → perfect negative linear relationship (inversely propositional)
- How columns are related with each other. How does one column affect other column linearly

- Strong positive correlation → +1

Y
↑
|                    ●
|                ●
|            ●
|        ●
|    ●
| ●
+--------------------------→ X

- As X increases, Y also increases
- Hours studied ↑  →  Marks ↑
- upward straight-line pattern
- Correlation is positive and strong → close to +1.


- Strong negative correlation → -1

Y
↑
| ●
|     ●
|         ●
|             ●
|                 ●
|                     ●
+--------------------------→ X

- As X increases, Y decreases
- Car age ↑  →  Car price ↓
- downward straight-line pattern
- Correlation is negative and strong → close to -1


- No linear correlation → 0

Y
↑
|       ●          ●
|  ●             ●
|          ●
|     ●               ●
|               ●
| ●       ●
+--------------------------→ X

- As X increases, Y doesn't consistently increase or decrease.
- Hours studied → Shoe size
- no clear straight-line pattern
- Correlation is close to 0 → little/no linear relationship
- Correlation matrix → A table showing the correlation coefficient between every pair of numerical columns.
- Can use heatmap to represent correlation matrix
- Feature Selection : A feature with low/zero correlation with the target can be considered as a candidate for removal, but correlation alone should not be used as the final decision because correlation measures only linear relationships. The feature may still have a non-linear relationship with the target and therefore could still be useful for prediction.
- If two features have very similar or identical correlation with the target and are also highly correlated with each other, they may be carrying almost the same information. In such cases, keeping one feature may be sufficient. For example, temp and atemp may contain highly similar information, so we can consider retaining one instead of both to reduce redundancy.
- https://www.youtube.com/watch?v=1fFVt4tQjRE
```

### Heatmap

A **heatmap is a data visualization that represents values in a matrix or grid using colors**, where different colors or color intensities make patterns, high/low values, or relationships easier to identify.

A heatmap does **not calculate the values**; it only **visualizes values that are already present in a matrix**.

- Categorical data → `crosstab()` → Count matrix → `heatmap()` → Visualize counts
- Numerical data → `corr()` → Correlation matrix → `heatmap()` → Visualize correlations

For example:
- `crosstab()` → creates a count/frequency matrix → heatmap visualizes it
- `corr()` → creates a correlation matrix → heatmap visualizes it

