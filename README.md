Data Analysis Portfolio mini-Project

Extreme Poverty, Child Malnutrition and Under-5 Mortality – Global Relationships using World Bank Indicators

1. Project Overview
   
Objective


This project examines the relationships between extreme poverty, child malnutrition (prevalence of underweight children under 5), and under-5 mortality rates across countries. The main goal is to quantify how strongly poverty and malnutrition predict child survival and to visualize high-burden countries.

Data Source

World Bank Open Data 

Key indicators: 

-  Poverty headcount ratio at $2.15 a day (2017 PPP)
  
- Prevalence of underweight, weight for age (% of children under 5)
  
-  Mortality rate, under-5 (per 1,000 live births)

Tools & methods 

- R programming language (4.5.2)
  
- Packages: tidyverse (dplyr, ggplot2, readr)

Methods

-  data cleaning, descriptive statistics, Pearson correlation analysis, multiple linear regression, scatter plots with trend lines


Dataset size after cleaning

≈132 countries with complete data for all three variables

2. Exploratory Data Analysis
   
2.1 Summary of statistics for selected variables

The data shows strong right-skewness in poverty and malnutrition, with a small number of countries experiencing very high burdens. Under-5 mortality ranges widely (2.3–117 per 1,000), highlighting global inequality in child survival.

2.2 Correlation analysis

Extreme poverty shows the strongest association with under-5 child mortality (r = 0.76), followed by child malnutrition (r = 0.67). Both factors are moderately correlated with each other (r = 0.56), suggesting they capture partly overlapping but also distinct dimensions of child health risk.


3. Visualisations
   
  <img width="486" height="279" alt="image" src="https://github.com/user-attachments/assets/f424d61e-f1e4-46c4-a0b0-c90d91204eba" />
  
 
 Figure 1 – Extreme Poverty vs Under-5 Mortality (with high-burden country labels)

 Key insight
- Strong linear association (r ≈ 0.76). Countries with extreme poverty often show under-5 mortality rates of 80–120 per 1,000 live births. 
- High-burden examples include Nigeria, Somalia, Sierra Leone, Central African Republic, Guinea, Mali, Angola, Mozambique, Niger and others.
- This visualization emphasizes that reducing extreme poverty remains one of the most powerful ways to accelerate progress toward SDG 3.2 (ending preventable child deaths by 2030).

<img width="452" height="279" alt="image" src="https://github.com/user-attachments/assets/83d07509-3b4d-461a-9319-5fd6b2284805" />

Figure 2. Child Malnutrition vs Under-5 Mortality 

Key insight
- Clear positive relationship (r ≈ 0.67). Higher prevalence of underweight children is strongly associated with elevated child mortality.
- This visualisation highlights malnutrition as a major preventable driver of child deaths, reinforcing the importance of nutrition interventions in high-burden countries.


<img width="452" height="279" alt="image" src="https://github.com/user-attachments/assets/43d362ea-08ec-4836-8bf3-d15ea90d656e" />


Figure 3: Poverty and under-five mortality 

Key insight
- There is a strong linear association (Pearson correlation ≈ 0.76) between higher levels of extreme poverty and higher child mortality.  
- Low-poverty countries cluster tightly near the bottom-left (mortality < 20 per 1,000), while high-poverty countries show much wider dispersion in the top-right, reflecting additional risk factors (e.g., malnutrition, conflict, weak health systems).
- This visualisation underscores why reducing extreme poverty remains one of the most powerful levers for improving child survival globally.

<img width="452" height="279" alt="image" src="https://github.com/user-attachments/assets/bc2160e8-4997-4d69-9984-19eedb9ad982" />

Figure 4: Poverty vs Malnutrition (coloured by Under-5 Mortality) 
Key insight
- The most severe child mortality outcomes (dark red/brown points) cluster where both poverty and malnutrition are high. 
- Low-poverty countries tend to have both low malnutrition and low mortality.
- Higher poverty is generally associated with higher malnutrition, but the relationship is moderate (correlation ≈ 0.56) and shows considerable scatter.  
- The most striking pattern: countries with both high poverty and high malnutrition (top-right region) almost always have the highest child mortality rates (dark red/brown points).  
- Low-poverty countries (left side) cluster at low malnutrition and low mortality (green/light points), even when malnutrition varies somewhat.  
- This visualisation suggests that malnutrition amplifies the impact of poverty on child survival — the worst outcomes occur when both risk factors are elevated together.


4. Regression Analysis

Multiple Linear Regression

Model

Under-5 Mortality Rate (per 1,000) = β₀ + β₁ × Poverty (%) + β₂ × Malnutrition (%) + ε

Model fit
R² = 0.660 | Adjusted R² = 0.655
→ Poverty and malnutrition together explain 66% of the variation in under-5 mortality
F (2, 129) = 125.2, p < 2.2 × 10⁻¹⁶ → highly significant

Interpretation  

- Controlling for malnutrition, a 1 percentage point increase in extreme poverty is associated with +0.75 deaths per 1,000 live births (95% CI: 0.58–0.91).  
- Controlling for poverty, a 1 percentage point increase in child malnutrition is associated with +1.15 deaths per 1,000 live births (95% CI: 0.75–1.54).
→ Malnutrition has a slightly larger estimated per-unit effect than poverty.


5. Key Findings & Conclusion

-  Extreme poverty is the single strongest predictor of under-5 child mortality (the strongest correlation and robust regression coefficient).  
-  Child malnutrition has a substantial independent effect beyond poverty.  
- The combination of high poverty and high malnutrition produces the worst child survival outcomes.  
-  Reducing extreme poverty and improving child nutrition remain two of the most powerful levers for achieving SDG 3.2 (end preventable child deaths by 2030).

6. Limitations of the project
   
The dataset contains a significant number of missing values, which prevents the inclusion of all countries in this analysis. I focused exclusively on complete cases, but this might have excluded important data that could impact the findings. Since the data collected is cross-sectional, it is not possible to establish cause-and-effect relationships. This project considered two independent variables but did not account for other potential confounders due to a lack of sufficient data. Furthermore, the collected data was not suitable for comprehensive analysis since only one data point per country was gathered for each indicator. This study used a small sample size, which may impact the power of statistical tests. Despite these limitations, this project makes a valuable contribution to the existing literature by exploring the relationship between poverty, malnutrition, and the under-five mortality rate.

Personal reflection

This project strengthened my skills in data cleaning, statistical modelling (correlation & regression), visualisation with ggplot2, and clear communication of findings. It also deepened my understanding of global health inequalities and the importance of evidence-based policy.

References 

1.	World Health Organization and United Nations Children's Fund, Levels and trends in child malnutrition: key findings of the 2020 edition. UNICEF/WHO/World Bank Group joint child malnutrition estimates. 2020: World Health Organisation.
2.	Ritchie, H, “Half of all child deaths are linked to malnutrition" Published online at OurWorldinData.org. . 2024.
3.	World Health Organization. Children: improving survival and well-being. 2020  [cited 2024 25/10/2024].
4.	World Health Organization. Child mortality (under 5 years). 2022  [cited 2024 27/10/2024]; Available from: https://www.who.int/news-room/fact-sheets/detail/levels-and-trends-in-child-under-5-mortality-in-2020#:~:text=The%20total%20number%20of%20under,1990%20to%2037%20in%202020.




