# Exploratory-Data-Analysis-Visualization-and-Descriptive-Statistics-using-R
## Overview

This project presents an exploratory analysis of the **Ghana Health and Socioeconomic Survey (GHSS)** dataset using R. The analysis covers data preparation, exploratory visualisation, descriptive statistics, inferential statistical testing, and geospatial analysis.

The cleaned dataset contains **12,000 observations and 42 variables**.

## Objectives

The analysis focuses on:

- Preparing and validating the GHSS dataset.
- Exploring categorical and continuous variables.
- Producing multiple statistical visualisations.
- Examining relationships between health and socioeconomic variables.
- Creating a choropleth map of mean fasting blood glucose across Ghanaian regions.
- Creating an interactive geospatial visualisation using respondent coordinates.
- Comparing respondents with and without hypertension using descriptive and inferential statistics.

## Tools and R Packages

The project uses R and the following packages:

- `tidyverse`
- `scales`
- `ggthemes`
- `ggridges`
- `treemapify`
- `patchwork`
- `sf`
- `geodata`
- `leaflet`
- `gtsummary`
- `flextable`
- `glue`

## Dataset

The analysis uses a GHSS dataset loaded from `ghss.csv`.

The dataset contains demographic, socioeconomic, healthcare, lifestyle, and health-related variables including:

- Region and district
- Residence
- Sex
- Age and age group
- Marital status
- Religion
- Education
- Occupation
- Work experience
- Household size
- Monthly income
- Health insurance
- Water source
- Healthcare utilisation and satisfaction
- Height, weight and BMI
- Blood pressure
- Fasting glucose
- Cholesterol
- Physical activity
- Smoking and alcohol use
- Diet and stress scores
- Sleep hours
- Hypertension
- Diabetes
- Overall health status

## Data Preparation

The analysis:

1. Loads the required R packages.
2. Reads `ghss.csv`.
3. Treats empty strings, `NA`, and `N/A` as missing values.
4. Checks the structure and dimensions of the dataset.
5. Converts selected variables to ordered factors where appropriate.
6. Establishes meaningful ordering for age groups, BMI categories, health status, education, and other categorical variables.

## Task 1: Data Visualisation

Five visualisations are used to explore different variable combinations.

### 1. Health Insurance Distribution

A lollipop chart examines the distribution of health insurance coverage.

**Key observation:** NHIS is the most common form of coverage, while a sizeable proportion of respondents have no insurance.

### 2. BMI Category by Sex

A grouped bar chart compares BMI categories across sex groups.

**Key observation:** Overweight and obesity are prevalent across both groups, with a comparatively higher proportion of obesity among female respondents.

### 3. Monthly Income Distribution

A density plot with a rug plot examines the distribution of monthly household income.

**Key observation:** Monthly income is strongly right-skewed. The reported median is approximately **GHS 1,359**, while the mean is approximately **GHS 1,869**, indicating that higher-income observations pull the mean upward.

### 4. BMI and Systolic Blood Pressure

A scatterplot with a LOESS trend examines the relationship between BMI and systolic blood pressure.

**Key observation:** The analysis indicates a positive, non-linear association between BMI and systolic blood pressure, although substantial variability remains at different BMI levels.

### 5. Fasting Glucose by Age Group

A ridge plot compares fasting glucose distributions across age groups.

**Key observation:** Older age groups, particularly the 50–59 and 60+ groups, show heavier right tails in fasting glucose distributions than younger groups.

## Task 2: Choropleth Map of Ghana

A regional choropleth map is used to visualise mean fasting blood glucose by administrative region.

The analysis calculates the mean fasting glucose for each of Ghana's 16 regions and joins the results to administrative boundaries obtained from GADM.

### Regional Findings

The reported regional means range from approximately **5.68 to 5.94 mmol/L**.

- Upper West: 5.94
- Ahafo: 5.93
- North East: 5.88
- Western: 5.87
- Upper East: 5.87
- Oti: 5.84
- Western North: 5.84
- Central: 5.83
- Volta: 5.82
- Eastern: 5.79
- Bono: 5.74
- Savannah: 5.71
- Ashanti: 5.70
- Northern: 5.69
- Bono East: 5.69
- Greater Accra: 5.68

The map provides a spatial overview of regional variation in mean fasting glucose.

## Task 3: Interactive Geospatial Visualisation

A Leaflet map is created using respondent latitude and longitude coordinates.

The interactive map provides information including:

- Sex
- Age
- Health status
- Region
- Health insurance

Markers are colour-coded according to health status.

### Advantages of the Interactive Map

Compared with the static choropleth, the interactive map allows users to:

1. Inspect individual-level observations.
2. Explore within-region variation.
3. Identify potential spatial clustering.
4. Zoom into geographic areas.
5. Relate health observations to geographic infrastructure and context.

## Task 4: Descriptive and Inferential Statistics

### Research Question

> Do respondents diagnosed with hypertension differ significantly from non-hypertensive respondents in terms of age, monthly income, BMI, and physical activity behaviour?

The analysis compares respondents according to hypertension status.

### Variables

**Grouping variable**

- Hypertension

**Categorical variables**

- Physical activity
- Health insurance

**Continuous variables**

- Age
- BMI

### Descriptive Findings

The analysis reports the following differences:

| Variable | Hypertension: Yes | Hypertension: No |
|---|---:|---:|
| Mean age | 41.9 years | 34.5 years |
| Mean BMI | 27.9 kg/m² | 26.7 kg/m² |
| Physically active | 51.1% | 53.1% |
| NHIS coverage | 76% | 76% |

### Statistical Tests

Different statistical tests are selected based on variable type and distribution:

| Variable | Test | Purpose |
|---|---|---|
| Age | Independent samples t-test | Compare mean age between groups |
| BMI | Wilcoxon rank-sum test | Compare BMI distributions between groups |
| Physical activity | Pearson chi-square test | Compare proportions between groups |
| Health insurance | Pearson chi-square test | Compare insurance categories between groups |

### Inferential Findings

The reported results indicate statistically significant differences for:

- **Age:** p < 0.001
- **BMI:** p < 0.001

The analysis also reports a statistically significant association between physical activity and hypertension status.

The health insurance comparison has a reported p-value of approximately **0.970**, indicating no statistically significant association in the presented results.

## Key Findings

Overall, the analysis identifies several notable patterns:

1. NHIS is the dominant health insurance type.
2. Overweight and obesity are common across the analysed groups.
3. Monthly household income is strongly right-skewed.
4. Higher BMI is associated with higher systolic blood pressure in the sample.
5. Older age groups show distributions with higher fasting glucose values.
6. Mean fasting glucose varies across Ghana's regions.
7. Respondents with hypertension are older and have higher mean BMI than respondents without hypertension.
8. Physical activity levels differ between hypertension groups.
9. Health insurance distribution is broadly similar between respondents with and without hypertension.

## Practical Implications

The findings suggest that public health interventions could place emphasis on:

- Weight management.
- Physical activity.
- Hypertension prevention.
- Diabetes prevention.
- Age-targeted health promotion.
- Regionally informed health interventions.


## Reproducibility

To reproduce the analysis:

1. Install R.
2. Install the required packages.
3. Place the authorised `ghss.csv` dataset in the project directory.
4. Open the R Markdown analysis file.
5. Run or knit the analysis to HTML.

## Conclusion

This project demonstrates an end-to-end exploratory data analysis workflow using R, combining statistical summaries, modern visualisation techniques, geospatial analysis, interactive mapping, and inferential statistics.

The analysis highlights relationships among demographic, socioeconomic, lifestyle, and health variables within the GHSS dataset and demonstrates how visual and statistical methods can be combined to communicate meaningful patterns in health data.
