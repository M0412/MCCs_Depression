## Multiple Chronic Condition data analytics focused on Depression
Fiza, Daniel, Denisse, Katherine, Shipra, Mimi

## The Study of Multiple Chronic Conditions (MCCs)
Chronic conditions, including heart disease, diabetes, and cancer, are those lasting 1+ year. These diseases are highly prevalent, with 6 in 10 US adults having at least one such condition and 4 in 10 having two or more.

Moreover, the public health and economic costs imposed by these conditions is enormous. Each year, the US spends $3.5T on healthcare, more than the GDPs of France, India and the UK. Of this, about 5% of the sickest patients account for 50% of all healthcare spending (~$1.75T). 

The aims of this analysis are two fold:
1) To characterize the population with multiple chronic conditions (e.g., demographics, geographic distribution, comorbidities)
2) To do a deeper dive analysis into one chronic condition, depression, that is both highly prevalent but whose characteristics (e.g., in terms of demographics, comorbidities, etc.) is less known than those  of other chronic conditions (e.g., diabetes, heart disease)

## Coding and Cleaning the Data
We used two datasets for this project, one open API dataset from the Centers for Medicare and Medicaid Services (CMS) and another dataset from the Centers for Disease Control and Prevention (CDC). To clean and analyze each dataset, we split into two subgroups (one dataset per subgroup). cms_2017.ipynb contains the multiple chronic condition analysis code and cdc_combined.ipynb contains depression analysis code. Cleaning and analysis is discussed in further detail below:

## CMS dataset
This data was divided into three separate geographic levels: national, state, and county levels. We decided to analyze variables at the state-level, including: MCC prevalence, emergency room visits, hospital readmissions and Medicare spending. Using these variables, we then cleaned the data, filtering out “unknowns”, dropping null values, adding state codes, and grouping the data to identify any pattern which could explain the occurrence of multiple chronic conditions. We plotted multiple bar graphs to see the correlation between the severity of MCCs and the variables and found many interesting relationships. 

## Depression dataset
Our characterization of features associated with depression was derived from data from the 2017 National Health Interview Survey (NHIS). The NHIS is conducted annually by the CDC to gauge the overall (and perceived) health and well-being of Americans. Topics covered include demographics, socioeconomic measures, medical history, and more. The 2017 survey contained ~710 questions (and sub-questions) / variables and surveyed 26,000+ individuals. To facilitate our analysis, we discarded questions collecting paradata. We then used a “MECE” approach (mutually exclusive, completely exhaustive) to discard variables that, qualitatively, were similar to other variables (e.g., family history of diabetes, ever been told they had prediabetes). 
We then ran a correlation matrix on the 39 remaining variables to identify which variables had the strongest positive (or negative) correlations with depression. For the most highly correlated variables, we tested for statistical analysis (e.g., chi-square test) and then created data visualizations.

## Data Visualization

After a careful analysis of the data, we had made very interestings discoveries about the demographics and prevalence of MCCs. We are addressing various questions as follows:

## What is the demographic profile of MCCs? 

By comparing age and disease prevalence data, we found a higher occurrence of MCCs among individuals <65 years of age (vs. those age 65+). Finding this trend was very eye-opening and really shows how crucial it is to develop more early screenings for specific conditions and targeted interventions for said conditions. This finding could start improvements in healthcare to improve the well-being and quality of life for individuals struggling with multiple chronic conditions.
![Screenshot 2023-07-25 at 3 44 12 PM](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/6a56cb6f-044b-4649-be72-c8d8279af68c)

We also looked at the geographic distribution of MCCs. Using Geomaps, we found that MCCs, specifically the group that suffers with 6 or more MCCs, are most prevalent in the East Coast and in the South. We theorize that this could be due to a combination of factors. Socioeconomic disparities in these regions, environmental factors, healthcare access, and lifestyle choices. Socioeconomic factors can play a role alongside healthcare access as some people/families are unable to afford the proper healthcare. These regions may have some poor dietary and lifestyle habits, which is why we believe lifestyle choices might be a big contributor to the development of 6 or more chronic conditions. Finally, environmental factors can play a role as these areas are known to have some extreme weather conditions that can trigger certain conditions. Population migration patterns between neighboring states could play a role in the similarity of prevalence rates. ​​If individuals with certain health conditions tend to move between these states, it can contribute to consistent prevalence patterns.
![Screenshot 2023-07-25 at 11 58 17 AM](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/adaa5a2b-21b1-4170-9627-e9b9acdeb5b7)

## How do MCCs utilize healthcare resources and dollars?

We looked at hospital emergency room utilization by MCCs. Using grouped bar plots, we filtered the data based on all states, by ages which are 65+ and <65, and grouping by number of ER visits or hospital readmittance rate. The analysis revealed that less than 65 have a very higher rate of ER visits than the 65+ age group. Geographical regions with smaller populations like the Virgin Islands, Hawaii and DC have the highest ER visits. Islands away from the mainland may have limited access to healthcare facilities, leading to higher ER visits. With fewer healthcare options, individuals may rely on ERs for both urgent and non-urgent medical needs. Hawaii and Virgin Islands experience high tourism and may have increased demand on healthcare services due to visitors seeking medical care during their stay. This can lead to a higher burden on local healthcare facilities, resulting in more ER visits. Individuals with lack of insurance or limited health insurance coverage, may delay seeking medical care until they have no choice but to go to the ER services. 
![Screenshot 2023-07-25 at 11 58 27 AM](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/691ce120-844e-4348-a16d-0c9384fd6f7b)

We also looked at healthcare (Medicare) spend on MCC patients. By filtering our data based on MCC Group vs Total Medicare Spending Per Capita, we found that the groups with 6 or more chronic conditions have the most spending per capita. This analysis reveals that this particular subgroup requires more healthcare interventions, likely due to the complexity of managing multiple chronic conditions at once. 
![Screenshot 2023-07-25 at 11 58 58 AM](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/9f4ac101-2768-465b-b52d-5e9fd969e0c1)

## What factors are most closely associated with depression? (e.g., demographic, geographic)

We observed a difference in disease prevalence based on sex. According to our dataset it appears that depression affects females more, but this could be inaccurate since female respondents outnumbered males by 20%. This issue has been addressed under “Limitations of CDC Data”.
![Screenshot 2023-07-26 at 9 42 48 AM](https://github.com/M0412/MCCsdata_analytics_Depression/assets/133132845/e7ab5f7f-b185-4697-9bc5-a8d91b0a7138)

We also observed geographic differences in disease prevalence. By filtering our data based on regions, we found that the majority of people with depression were from the South, and the majority of people without depression were also from the South. We can not conclude for sure if depression is more prevalent in the South or if this is the byproduct of how the survey was fielded (e.g., offered to more southerners, higher response rate from southerners, etc.). This has also been addressed under “Limitation of CDC Data”
![Fig6](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/6d511d04-5028-46bd-ab5b-fbca5c5f6b15) ![Fig5](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/efa69ed3-581c-488f-ad9b-7518ae61ba21)

Lastly, we identified comorbidities and other health-related factors that strongly correlate with depression by using the heat map matrix.
![Screenshot 2023-07-23 at 9 22 08 AM](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/c107150d-cf5b-4cdc-8c6d-c6284c70a408)

We were able to spot six factors that appear to have a strong correlation with depression. These factors are: 

1) Hypertension
2) Arthritis
3) Overall Functional limitation
4) Self Reported Health Status
5) Pain Severity
6) Smoking Status
![Screenshot 2023-07-23 at 9 56 51 AM](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/41d70dee-6f29-4a59-af0b-a97832f3c8fc)
![Fig3](https://github.com/ShipraGupta16/UCB_Project_1/assets/133132845/7c2767d1-3de6-4208-962c-af5470571319)

## Results
1) Southern and Northeastern states appear to have a higher prevalence of MCCs. 
2) People younger than age 65 are more likely to have MCCs than those older than 65. 
3) Individuals with depression are more likely to have hypertension, arthritis, or pain than those without.
4) The percentage of smokers among individuals who do not have depression is slightly higher than the percentage of smokers among those who have depression. 

## Limitations of CMS Data

1) The CMS data provides an incomplete view of the MCC population. For instance, the data didn’t clearly discuss respondents’ insurance status (e.g., whether they have Medicare or Medicaid or Dual Medicaid-Medicare or Commercial insurance or something else). This is relevant because each of these subpopulations has different socioeconomic profiles and thus, likely different levels of access to different healthcare resources and services.
2) The data lacks information on socioeconomic status (e.g., household income, household income to poverty ratio).
3) It doesn’t provide data on access to healthcare services or facilities (e.g., availability of doctors, hospitals, clinics in the respondents’ county or zip code). Thus, we are not able to assess the potential significance of healthcare access on MCC disease prevalence.
4) There was no data on specific diseases. That is, we didn’t know which conditions these respondents had nor which diseases are more likely to exist concomitantly. 
5) Data provided was incomplete in terms of race and sex across all the state/county level. Race and Sex data was not structured enough to be used to visualize.
6) Age level was a broad range. Less than and more than 65. It didn’t focus on how many people come into that category. Grouping respondents into narrower age bands like (e.g., 18-44, 45-64, 65+) would have been more useful in our analysis.
7) Data was so granular at the counties level, that it required various filtering before analyzing or visualizing the data. 



## Limitations of CDC data

1) The 2017 NHIS dataset provides a limited view into the population suffering from depression. Missing variables includes: <br>
  a) Depression status (only asked to those with self-reported functional limitation)<br>
  b) Geographic data at the state, county, metro, or zip code levels<br>
  c) Health insurance status(e.g., Medicare vs. Medicaid vs. Dual vs. Commercial)<br>
  d) Measures of socioeconomic status(e.g.,  household income)<br>
  e) Health metrics (e.g., BMI, self-reported health status, self-reported life satisfaction)<br>
2) Females respondents outnumbered males by 20%.
3) No age stratification (i.e., <1yr, 1-84 yrs, 85+ yrs).
4) Uncertain whether the survey was equally distributed by region.

## Conclusion 
1) Our analysis found out an interesting pattern of neighboring US states with high prevalence of multiple chronic conditions. Less than 65 years of age group were the most affected group.
2) Islands away from the mainland experienced high emergency care and hospital readmittance rates. This could be the geographical location tied up with inadequate access to health care services in those regions. 
3) The expenditure on medical resources for group 6+ was observed to be at an alarming rate than other group levels. This resonates with the importances of studying MCCs more in the future to help the general public understand the urgency of regular testing for common chronic conditions.
4) Those dealing with depression are more likely to deal with arthritis or hypertensions which are commonly diagnosed chronic conditions. 
5) Overall, the data showed that there is a need for more testing and research into the effects of MCC and the environmental or socioeconomic factors that contribute to the rise of prevalence of MCCs. 
