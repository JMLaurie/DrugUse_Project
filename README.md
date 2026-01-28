# Drug Use Analysis Project (INEG 2314 Honors Project)

## Project Overview
This honors project investigates the patterns of alcohol and marijuana use among individuals aged 18-21 years old. Using statistical analysis and data visualization techniques in R, the study examines whether usage rates and frequencies differ significantly across this age range for these two substances, both of which are illegal for individuals under 21 in the United States.

**Author:** Jake Laurie  
**Date:** October 24, 2023  
**Course:** INEG 2314

## Research Objective
The primary goal of this research is to use statistical analysis and visualizations to investigate the relationship between age (18-20 years old) and the usage patterns of alcohol and marijuana. The study aims to determine:

- Whether usage rates change significantly year-over-year during this three-year period
- If there are differences in usage patterns between alcohol and marijuana
- Whether frequency of use (days per year) follows similar patterns to overall usage rates

**Initial Hypothesis:** Usage would be similar across the three years for both substances, with comparable average usage rates between alcohol and marijuana.

## Dataset Description
The project utilizes the "drug-use-by-age.csv" dataset, which contains comprehensive information about substance use patterns across different age groups. The analysis focuses specifically on ages 18-21, examining:

- **Age groups:** 18, 19, 20, and 21 years old
- **Sample size (n):** Number of individuals surveyed in each age group
- **Alcohol use:** Percentage and frequency of alcohol consumption
- **Marijuana use:** Percentage and frequency of marijuana consumption
- **Frequency metrics:** Number of days per year each substance is used

## Methodology

### 1. Data Preparation
- Imported CSV dataset as a tibble using the `rio` package
- Filtered data to focus exclusively on ages 18-21
- Calculated absolute usage numbers by converting percentages to counts based on sample size
- Selected relevant variables: age, sample size, alcohol/marijuana use counts and frequencies

### 2. Statistical Analysis

#### Proportion Testing for Alcohol Use
Conducted two-proportion z-tests to compare alcohol usage rates between consecutive age years:
- **Ages 18 vs 19:** Compared 1,449 vs 1,436 users
- **Ages 19 vs 20:** Compared 1,436 vs 1,583 users  
- **Ages 20 vs 21:** Compared 1,583 vs 1,959 users

#### Proportion Testing for Marijuana Use
Conducted two-proportion z-tests to compare marijuana usage rates between consecutive age years:
- **Ages 18 vs 19:** Compared 832 vs 742 users
- **Ages 19 vs 20:** Compared 742 vs 772 users
- **Ages 20 vs 21:** Compared 772 vs 777 users

### 3. Exploratory Data Analysis
- Generated summary statistics using `summary()` and `describe()` functions
- Created bar plots to visualize usage distributions
- Examined distributions and patterns in the data

### 4. Data Visualization
- Created side-by-side bar charts comparing alcohol and marijuana frequency distributions
- Used `ggplot2` for professional visualization with custom color schemes
- Employed `gridExtra` to arrange multiple plots for comparison

## Key Findings

### Alcohol Usage Patterns
**Significant Year-Over-Year Increase:**
- All p-values were below α = 0.05, indicating statistically significant differences
- All confidence intervals were entirely negative, confirming that usage increases with each year
- Usage increases substantially and consistently from age 18 to 21
- **Distribution:** Alcohol frequency distribution is left-skewed, indicating higher usage among older individuals in the cohort

**Interpretation:** As individuals approach the legal drinking age of 21, alcohol consumption rates increase significantly each year. This suggests progressive adoption of drinking behaviors as young adults get closer to legal age.

### Marijuana Usage Patterns
**No Significant Year-Over-Year Change:**
- All p-values exceeded α = 0.05, indicating no statistically significant differences
- Confidence intervals all contained zero, suggesting stable usage rates
- Usage remains relatively constant across ages 18-21
- **Distribution:** Marijuana frequency distribution is uniform, showing consistent usage across all ages

**Interpretation:** Marijuana usage appears to reach its target demographic around age 18 and does not gain significant new users as individuals age toward 21. The stability suggests that marijuana use patterns are established early and remain constant.

### Frequency Analysis
The frequency data (days of use per year) mirrors the usage rate patterns:
- **Alcohol:** Frequency increases with age, matching the left-skewed usage distribution
- **Marijuana:** Frequency remains uniform across ages, consistent with stable usage rates

This correlation indicates that not only do more people start using alcohol as they age, but existing users also increase their frequency of use.

## Technologies and Tools Used

### R Programming Language
- **Core Language:** R for statistical computing and data analysis
- **Development Environment:** R Markdown for reproducible research

### R Packages
- **pacman:** Package management and loading
- **tidyverse:** Data manipulation and visualization ecosystem
- **rio:** Data import/export
- **psych:** Psychological statistics and descriptive analysis
- **ggplot2:** Advanced data visualization
- **gridExtra:** Multi-plot arrangements
- **corrplot:** Correlation visualizations
- **tsibble:** Time series data structures
- **lubridate:** Date/time manipulation

## Project Structure
```
DrugUse_Project/
├── code/
│   └── HonorsProject.Rmd      # Main R Markdown analysis file
├── data/
│   └── drug-use-by-age.csv    # Dataset containing drug usage by age
├── Output/
│   └── 2314_Honors_Final_Update_Laurie.pdf  # Final report PDF
└── README.md
```

## Conclusions

### Hypothesis Evaluation
The initial hypothesis was **incorrect**. Contrary to expectations:
- Alcohol and marijuana usage do **not** follow the same distribution patterns
- Alcohol usage increases significantly year-over-year
- Marijuana usage remains stable across the age range

### Key Insights
1. **Alcohol Use Increases with Age:** Each year from 18 to 21 shows statistically significant increases in both the number of users and frequency of use, likely driven by social factors and approaching legal drinking age.

2. **Marijuana Use Remains Stable:** Usage rates are established around age 18 and do not significantly change, suggesting different social dynamics and user adoption patterns compared to alcohol.

3. **Frequency Follows Usage:** The pattern of usage frequency mirrors the overall usage distribution for both substances, indicating that new user acquisition drives overall consumption patterns.

### Public Health Implications
To reduce underage substance use, interventions should focus on:
- **Prevention of new user adoption**, particularly during periods of significant growth (ages 18-21 for alcohol)
- **Age-specific strategies** recognizing that alcohol and marijuana have different usage trajectories
- **Early intervention** around age 18 when marijuana use patterns are established
- **Continued education** throughout ages 18-21 when alcohol use is increasing most rapidly

## How to Run the Analysis

1. **Install Required Packages:**
   ```r
   install.packages("pacman")
   pacman::p_load(pacman, corrplot, tidyverse, rio, psych, 
                  tsibble, lubridate, ggplot2, gridExtra)
   ```

2. **Set Working Directory:**
   ```r
   setwd("~/INEG 2314/")
   ```

3. **Run Analysis:**
   - Open `code/HonorsProject.Rmd` in RStudio
   - Knit the document to generate the PDF report
   - Or run code chunks interactively to explore the data

## Statistical Methods Summary

### Two-Proportion Z-Test
- **Purpose:** Compare proportions between two independent groups
- **Null Hypothesis (H₀):** No difference in proportions between age groups
- **Alternative Hypothesis (Hₐ):** Proportions differ between age groups
- **Significance Level:** α = 0.05
- **Decision Rule:** Reject H₀ if p-value < 0.05

### Descriptive Statistics
- Summary statistics (mean, median, standard deviation)
- Distribution analysis and visualization
- Frequency analysis across categorical variables

## Future Research Directions

1. **Longitudinal Analysis:** Track the same individuals over time rather than cross-sectional age comparisons
2. **Geographic Variation:** Examine regional differences in usage patterns
3. **Demographic Factors:** Incorporate gender, socioeconomic status, and education level
4. **Intervention Evaluation:** Study the effectiveness of prevention programs across different age groups
5. **Additional Substances:** Expand analysis to include other substances and prescription medications
6. **Social Factors:** Investigate peer influence, family dynamics, and environmental factors

## References

Dataset: Drug use by age (drug-use-by-age.csv)  
Statistical methods: Two-proportion z-tests with 95% confidence intervals  
Visualization: R ggplot2 package with custom styling

---

**Note:** This project was completed as part of the INEG 2314 Honors curriculum. All statistical analyses follow standard hypothesis testing procedures with appropriate significance levels and confidence intervals.
