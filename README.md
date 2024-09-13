# Consumer Habits Analysis
**Course:** Introduction to Machine Learning
**Deadline:** May 8, 2024, 23:59  
**Total Points:** 30

## Objective
The aim of the task is to statistically analyze data contained in the file `dane_projekt1.csv`. These are simulated data that describe a fragment of the survey results on the consumer habits of residents in the fictional land of Bajtocja, conducted on a representative sample. The dataset may contain random errors.

### Variables Description:
- **id**: Observation identifier (contains no additional information)
- **waga**: Respondent's weight (in kg)
- **wzrost**: Respondent's height (in cm)
- **plec**: Gender on the respondent's identity document (1 – “female”, 2 – “male”)
- **dzieci**: Number of children dependent on the respondent (in persons)
- **wiek**: Respondent's age (in years)
- **dochod**: Declared respondent income for the given month (in "bajtalary")
- **oszczednosci**: Declared respondent savings for the given month (in "bajtalary", negative values mean expenses exceeded income)
- **jednoos**: Household status (1 – “single-person household”, 0 – “multi-person household”)
- **miejsce**: Size of the town the respondent lives in (1 – “up to 10,000 inhabitants”, 2 – “10,000 to 100,000 inhabitants”, 3 – “over 100,000 inhabitants”)
- **wydatki_zyw**: Declared food expenses for the given month (in "bajtalary")

The outcome should be a report in a Jupyter Notebook (.ipynb). The report and comments must be sufficient for understanding and reproducing your steps without reading your code. Any significant data modifications (e.g., removing records, introducing new variables) must be justified and described.

## Task Breakdown:

### Task 1: Data Loading and Initial Overview
- Load the data, explore it, and provide a summary in 2-3 sentences.
- **Supporting questions:**
  - How many observations are there? Discuss the structure of the dataset: How many quantitative variables and how many qualitative variables are there? Are there any missing data? (1 point)
  - Present and comment on relevant frequency tables or descriptive statistics for the variables (consider variable types). (1 point)
  - Present and comment (where relevant) on the distributions of variables, especially comparing them visually with the normal distribution (e.g., using histograms, Q-Q plots, etc.). (2 points)

### Task 2: Analyzing Relationships Between Variables
- Check for dependencies between variables. Calculate and display the appropriate correlation coefficient between quantitative variables using a heatmap. Also, examine the relationships between qualitative variables.
- Comment on the results, paying particular attention to statistical significance. (3 points)

### Task 3: Data Visualization
- Summarize the data using at least three different plots and comment on each.
- **Basic set of plots:**
  - Scatter plots for all quantitative variables relative to the variable `wydatki_zyw` (food expenses).
  - Boxplot for one chosen quantitative variable divided by the respondents’ place of residence.
  - Stacked bar chart for respondents’ gender and whether they live in a single-person household.
  
Each of these three basic plots is worth 1 point: 0.25 points for the plot itself, and 0.75 points for the commentary in the context of exploratory analysis. Additional plots can earn up to 1 extra point. (3 points total)

### Task 4: Confidence Intervals for Age
- Calculate two-sided confidence intervals with a confidence level of 99% (1 - α = 0.99) for the variable `wiek` (age) for the following distribution parameters:
  - Mean and standard deviation
  - Quartiles 1, 2, and 3
- Provide the assumptions used and comment on whether they seem justified. (2 points: 0.25 points for the mean, 0.25 points for the variance, 0.75 points for quartiles, 0.75 points for stating and commenting on the assumptions)

### Task 5: Wealth Classification and Food Expenditure Analysis
- Sociologists in Bajtocja divide society into four wealth classes:
  - Lower class (income below the 25th percentile of income distribution)
  - Middle class (income equal to or above the 25th percentile but below the 75th percentile)
  - Upper-middle class (income equal to or above the 75th percentile but below the 90th percentile)
  - Upper class (income equal to or above the 90th percentile)
  
Discuss and compare the variation in food expenditures across these wealth classes. (2 points: 0.5 points for creating the wealth classes, 1 point for calculating the correct measure of variation, 0.5 points for discussion and interpretation)

### Task 6: Statistical Hypothesis Testing
Answer the following research questions using the most appropriate statistical tests with a significance level of α = 0.01:
1. Do women have higher savings than men?
2. Is a lower proportion of food expenses relative to income correlated with higher savings?
3. Is the average weight of women in the sample greater than 56 kg?
4. Verify an additional (sensible) hypothesis about conformity to a specific parametric distribution for a selected variable (e.g., "Variable A follows a Poisson distribution with parameter 1").

For each test, state the null and alternative hypotheses, justify the test used, conduct the test, and provide a conclusion. (4 points: 1 point per test)

### Task 7: Food Expenditure Modeling
Conduct an analysis of food expenditure using the available variables. Assume a significance level of α = 0.01. Follow these steps:
- Estimate an initial model containing all the original variables (except for `id`) and a constant, where `wydatki_zyw` is the dependent variable. Make sure to properly encode categorical variables. (0.5 points)
- Comment on the R-squared, overall significance, and individual significance tests in the initial model. (1 point)
- Check if the initial model meets the assumptions of the Classical Linear Regression Model (CLRM). Pay particular attention to linearity, homoscedasticity, lack of autocorrelation, and the distribution of residuals. (2 points)
- Investigate multicollinearity in the initial model. (0.5 points)
- Analyze outliers in the initial model. If any suspicious observations are found, decide and justify what to do with them. (1 point)
- Improve the model to satisfy as many CLRM assumptions as possible. Describe the steps taken to obtain the “best” model. (4 points)
- Provide a quantitative interpretation of two individually significant coefficients in the “best” model (excluding the constant). (1 point)
- What are the descriptive characteristics of individuals whose predicted food expenditures are in the top 10% of your “best” model? Discuss. (2 points)
