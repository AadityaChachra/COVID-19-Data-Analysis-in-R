# **Data Visualization and Analytics with Open-Source COVID-19 Data**

## **📌 Project Overview**
This project aims to analyze and visualize the COVID-19 dataset using **R programming language**. The dataset is obtained from [Our World in Data](https://covid.ourworldindata.org/data/owid-covid-data.csv) and provides insights into global COVID-19 trends, including cases, deaths, and vaccinations.

## **📊 Features & Analysis**
- **Data Cleaning & Preprocessing**: Handling missing values and selecting relevant features.
- **Trend Analysis**: Visualizing COVID-19 cases and deaths over time.
- **Geospatial Analysis**: Mapping country-wise COVID-19 impact.
- **Vaccination Trends**: Analyzing global vaccination rates.
- **Interactive Plots**: Using `ggplot2` and `plotly` for better user interaction.

## **📂 Dataset**
- **Source**: [Our World in Data COVID-19 Dataset](https://covid.ourworldindata.org/data/owid-covid-data.csv)
- **File Name**: `owid-covid-data.csv`
- **Main Columns Used**:
  - `date`: Date of observation
  - `location`: Country/Region name
  - `total_cases`: Cumulative COVID-19 cases
  - `total_deaths`: Cumulative COVID-19 deaths
  - `total_vaccinations`: Total vaccination doses administered
  - `population`: Country's population

## **🚀 Getting Started**

### **1️⃣ Upload CSV File in Google Colab**
Before running the analysis, upload the dataset manually:
```python
from google.colab import files
uploaded = files.upload()
```

### **2️⃣ Install Required Libraries in R**
Run the following commands in an **R** cell in Google Colab:
```r
install.packages(c("ggplot2", "dplyr", "plotly", "RColorBrewer"), dependencies=FALSE)
```

### **3️⃣ Load the Dataset & Perform Analysis**
Run the main R script:
```r
# Load libraries
library(ggplot2)
library(dplyr)
library(plotly)
library(RColorBrewer)

# Load dataset
file_path <- "/content/owid-covid-data.csv"
data <- read.csv(file_path)

# Convert date column to Date format
data$date <- as.Date(data$date)

# Visualizing Global COVID-19 Cases Over Time
g1 <- ggplot(data, aes(x=date, y=total_cases, group=location, color=location)) +
  geom_line(alpha=0.5) +
  labs(title="Global COVID-19 Cases Over Time", x="Date", y="Total Cases") +
  theme_minimal()
ggplotly(g1)
```

## **📈 Visualizations**
- **COVID-19 cases over time (line graph)**
- **Total deaths vs. total cases (scatter plot)**
- **Vaccination progress per country (bar chart)**
- **World heatmap of COVID-19 impact**

## **📝 Project Structure**
```
📂 covid19_data_viz
│-- 📜 README.md  (Project documentation)
│-- 📊 owid-covid-data.csv  (Dataset)
│-- 📜 covid_analysis.R  (R script for analysis)
```

## **👨‍💻 Author**
- **Name**: Aaditya Chachra

## **📜 License**
This project is open-source and available under the **MIT License**.

