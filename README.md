# AB_TESTING_COOKIE-CATS-

# Cookie Cats A/B Testing Project

This project aims to analyze and compare player engagement between two versions of the game "Cookie Cats." The company was experimenting with two different versions, referred to as **gate30** and **gate40**, to determine if the placement of a "gate" affects player retention and engagement. We perform an A/B test to understand if there is a statistically significant difference in engagement between these two versions.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Requirements](#requirements)
- [Installation](#installation)
- [Analysis Steps](#analysis-steps)
  - [1. Data Loading and Overview](#1-data-loading-and-overview)
  - [2. Descriptive Statistics](#2-descriptive-statistics)
  - [3. Hypothesis Formulation](#3-hypothesis-formulation)
  - [4. Assumption Testing](#4-assumption-testing)
  - [5. A/B Testing](#5-ab-testing)
- [Results](#results)
- [Conclusion](#conclusion)
- [License](#license)

## Project Overview

The purpose of this project is to conduct an A/B test comparing two different versions of a game level. The test seeks to answer the following question:
- **Does the placement of the gate (level block) in the game impact player engagement, as measured by the number of rounds played (`sum_gamerounds`)?**

The results will help determine if there is a statistically significant difference between the two versions and guide the company on which version to continue using.

## Dataset

The dataset `cookie_cats.csv` contains the following columns:

- `userid`: Unique identifier for each player
- `version`: The game version the player interacted with (either `gate_30` or `gate_40`)
- `sum_gamerounds`: Number of game rounds played by the player
- `retention_1`: Whether the player returned the day after installing the game
- `retention_7`: Whether the player returned seven days after installing the game

## Requirements

- Python 3.x
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/cookie-cats-ab-test.git
   cd cookie-cats-ab-test
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure the dataset `cookie_cats.csv` is placed in a folder named `Data` within the project directory.

## Analysis Steps

### 1. Data Loading and Overview
- Load the dataset and create a copy for analysis.
- Check the first and last few rows of the data to understand its structure.
- Display information about data types, shape, and any missing values.

### 2. Descriptive Statistics
- Calculate the count of unique users in each version group.
- Compare `sum_gamerounds` for both groups in terms of mean, maximum, and count.
- Visualize the data distribution for each version to get a sense of overall engagement.

### 3. Hypothesis Formulation
- **Null Hypothesis (H0)**: There is no statistically significant difference between the engagement levels of `gate_30` and `gate_40`.
- **Alternative Hypothesis (H1)**: There is a statistically significant difference between the engagement levels of `gate_30` and `gate_40`.

### 4. Assumption Testing
- **Normality Test**: Use the Shapiro-Wilk test to determine if the data follows a normal distribution for each group.
- **Variance Homogeneity Test**: Use Levene’s test to evaluate if the variances between the two groups are similar.

### 5. A/B Testing
- Based on the results of the normality test, we perform a **Mann-Whitney U Test** since the data is not normally distributed.
- Calculate and interpret the p-value to determine if there is a statistically significant difference between the two versions.

## Results

- **Normality Test**: The p-value indicates that the data is not normally distributed, so we proceed with a non-parametric test.
- **Variance Homogeneity**: The p-value from Levene’s test suggests that the variances between the two groups are similar.
- **A/B Test Result**: The Mann-Whitney U Test p-value is above 0.05, meaning we cannot reject the null hypothesis.

## Conclusion

The analysis shows no statistically significant difference in player engagement between `gate_30` and `gate_40` with 95% confidence. Therefore, the company can choose either version without impacting overall engagement significantly, as the observed difference is likely due to random chance.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
