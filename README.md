# Analysis of Housing Prices with Regression Modeling

Welcome to the Analysis of Housing Prices project! This project aims to explore and model the factors influencing housing prices using a comprehensive dataset. Our goal is to identify key features that impact house prices and build predictive models to estimate these prices accurately.

## Table of Contents
- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Data Overview](#data-overview)
- [Data Exploration (EDA)](#data-exploration-eda)
- [Feature Engineering](#feature-engineering)
- [Model Building](#model-building)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction
*Ask a home buyer to describe their dream house, and they probably won’t begin with the height of the basement ceiling or the proximity to an east-west railroad. But this dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence. We are trying to answer the question: what features affect the price of a house?*

## Project Structure
1. **Data Exploration**
2. **Data Cleaning**
3. **Model Building**

## Data Overview
The dataset contains 1460 instances for both training and testing, with 81 attributes in total:
- **Quantitative** (36 attributes): e.g., 1stFlrSF, GarageArea, YearBuilt
- **Qualitative** (43 attributes): e.g., Alley, BldgType, Heating

## Data Exploration (EDA)
Exploratory Data Analysis (EDA) involves using summary statistics and graphical representations to uncover patterns, detect anomalies, test hypotheses, and verify assumptions.

### Key Findings:
1. **Missing Values**: Features like PoolQC, MiscFeature, and Alley have over 90% missing values and are excluded from the analysis.
2. **Correlation Analysis**: Strong correlations were found between several variables, such as GarageArea with GarageCars and YearBuilt with GarageYrBlt.

## Feature Engineering
Feature Engineering aims to enhance model accuracy by creating new features and transforming existing ones.

### Key Features:
1. **isRemodeledRecent**: Indicates if the house was remodeled recently.
2. **new_house_status**: Checks if the house was recently built.
3. **Average Rooms and Bathrooms**: Features to check the average number of rooms, garages, and bathrooms above ground.
4. **Location Features**: Features related to nearby transits and services.
5. **Area Features**: Features related to house area, porch area, and overall quality.
6. **Binary Transformation**: Numerical columns transformed to binary columns for faster training and improved accuracy.

## Model Building
The model building phase involves selecting the appropriate regression models, training them on the dataset, and evaluating their performance.

## Installation
### Prerequisites:
- Python 3.8 or higher
- Jupyter Notebook

### Step-by-Step Installation:
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/housing-price-analysis.git
    cd housing-price-analysis
    ```

2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage
1. Start the Jupyter Notebook:
    ```bash
    jupyter notebook
    ```

2. Open `main.ipynb` and follow the steps to perform data exploration, cleaning, and feature engineering.

3. Open `model_building.ipynb` to build and evaluate the models.

## Contributing
We welcome contributions to improve the project. Please fork the repository, create a new branch, and submit a pull request with your changes.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
