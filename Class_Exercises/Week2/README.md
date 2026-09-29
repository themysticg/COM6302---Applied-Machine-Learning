# Week 2 Data Analysis Lab

This exercise introduces exploratory data analysis for machine learning using a small dataset of student study hours and test scores. The notebook demonstrates how to load and inspect data, calculate descriptive statistics, check data quality, and communicate patterns with several chart types.

## Files

- [Open the completed Jupyter notebook](week2_data_analysis.ipynb)
- [View the student scores dataset](../../student_scores.csv)
- [Return to the module repository](../../README.md)

## Learning objectives

By completing this exercise, I learned how to:

- load a CSV dataset with pandas;
- preview and inspect a dataset;
- calculate descriptive statistics;
- identify missing values;
- create histograms, bar charts, line plots, and scatter plots;
- calculate and interpret a correlation coefficient; and
- distinguish correlation from causation.

## Dataset

The dataset contains eight student records and three columns:

| Column | Description |
| --- | --- |
| `Student` | Numerical identifier for each student |
| `Study Hours` | Number of hours studied |
| `Test Score` | Test result on a 0-100 scale |

Example records:

| Student | Study Hours | Test Score |
| ---: | ---: | ---: |
| 1 | 1.5 | 35 |
| 2 | 2.0 | 40 |
| 3 | 3.0 | 50 |
| 4 | 4.5 | 70 |
| 5 | 5.0 | 80 |

## Environment and libraries

The notebook was developed with Python and the following libraries:

- [pandas](https://pandas.pydata.org/) for loading and exploring the data;
- [Matplotlib](https://matplotlib.org/) for the histogram, bar chart, and line plot; and
- [Seaborn](https://seaborn.pydata.org/) for the scatter plot.

Install the required packages with:

```bash
python -m pip install pandas matplotlib seaborn
```

## Running the notebook

1. Clone or download the repository.
2. Open a terminal in the repository root.
3. Start JupyterLab:

   ```bash
   jupyter lab
   ```

4. Open [`Class_Exercises/Week2/week2_data_analysis.ipynb`](week2_data_analysis.ipynb).
5. Select a Python kernel containing pandas, Matplotlib, and Seaborn.
6. Choose **Kernel > Restart Kernel and Run All Cells**.

The notebook loads the dataset with this relative path:

```python
data = pd.read_csv("../../student_scores.csv")
```

The folder structure must therefore remain:

```text
COM6302 - Applied Machine Learning/
|-- student_scores.csv
`-- Class_Exercises/
    `-- Week2/
        |-- README.md
        `-- week2_data_analysis.ipynb
```

## Analysis workflow

### 1. Load and preview the data

The dataset is loaded with `pandas.read_csv()`, and `data.head()` confirms that the expected columns and values are available.

### 2. Explore the data

The notebook uses:

```python
data.describe()
data.isnull().sum()
```

The dataset contains eight observations and no missing values.

### 3. Visualise the data

Four visualisations are included:

1. **Histogram** - shows the distribution of study hours.
2. **Bar chart** - compares the test score achieved by each student.
3. **Line plot** - shows how test scores change as study hours increase.
4. **Scatter plot** - displays the relationship between study hours and test scores.

### 4. Measure correlation

The Pearson correlation is calculated with:

```python
correlation = data["Study Hours"].corr(data["Test Score"])
```

The resulting coefficient is approximately **0.986**, indicating a very strong positive linear relationship in this dataset.

## Key findings

- Study time ranges from **1.5 to 8 hours**.
- Test scores range from **35 to 99**.
- The mean study time is **4.625 hours**.
- The mean test score is **69.875**.
- Students with more study hours generally have higher test scores in this sample.
- The study-hours and test-score correlation is approximately **0.986**.
- No missing values were identified.

## Interpretation and limitations

The visualisations and correlation coefficient show a strong positive association between study hours and test scores. This means that higher study hours occur alongside higher test scores in the supplied data.

The result should be interpreted cautiously. The dataset contains only eight observations, so it may not represent a wider student population. Correlation also does not establish causation: other factors, such as prior knowledge, teaching quality, sleep, or assessment difficulty, could affect test performance.

## Possible extensions

Future development could include:

- fitting a simple linear-regression model;
- reporting the regression equation and R-squared value;
- predicting a score for a selected number of study hours;
- evaluating a model with a larger training and test dataset; and
- investigating additional variables that may influence performance.

## Conclusion

This exercise provides a foundation for exploratory data analysis in machine learning. It demonstrates that understanding data quality, summary statistics, distributions, and variable relationships is an essential step before building predictive models.

