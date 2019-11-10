# Final project plan

## Introduction

My goal is to study how the pay of public employees varies across different positions, institutions, states, and time. 
I aim to classify employees into a set of different job types, with a focus on public university staff, among public institutions in Washington and California. I am interested in the relative magnitude of salaries across positions for public employees, and the pay ranges across these positions. I would also like to explore how employee salaries in different institutions, within the same state and different states, compare across similar positions. Finally, I hope to understand the trends in salaries across time, particularly over the last 5 years, and whether salaries have generally increased at a rate higher than inflation. I will compare the mean salaries across positions to the median state income levels. I also plan to adjust salaries to reflect the costs of living across different states. 

I believe this topic is interesting and relevant because many public employees' salaries are funded by taxpayers, and states have the legal obligation to make this information public. According to the [Washington State Fiscal Information site](http://fiscal.wa.gov/supporta.aspx), "state revenue and expenditure data [will] be made as open, transparent, and publicly accessible as is feasible with the goal of making government more accountable". Thanks to the availability of this public information, [cases of disproportionately high public employee salaries have come to light](https://latimesblogs.latimes.com/lanow/2010/07/bell-city-manager-might-highest-paid-in-nation-787637-a-year.html), to the backlash of the public. On the other hand, [issues of privacy arise] (https://www.governing.com/news/state/gov-survey-disclosing-government-employee-salaries-troubles-public-officials.html) around the reporting of this information, because it includes publishing the names, salaries, and employer agencies of millions of people across the US. 

I also believe it will be interesting to identify any disparities and trends in pay between different types of positions and different institutions. [Legal disputes](https://caselaw.findlaw.com/wa-court-of-appeals/1126632.html) have arisen due to differences in pay among similar job classes in different state institutions. I believe this study will reflect on the fairness of employee salaries and shed light on inequity as reflected by pay disparities. One known phenomenon is that the highest-paid Washington state employees are [university sports coaches, and are mostly men] (https://patch.com/washington/across-wa/washingtons-millionaire-state-employees-are-men-mostly-coaches). 

It will also be useful to understand whether employee salary increases over time have kept up with the pace of inflation. While some employers tie employee salary increases to inflation, overall, real wages across the country have been slow to increase. [According to one report](https://www.washingtonpost.com/business/2018/08/10/america-wage-growth-is-getting-wiped-out-entirely-by-inflation/), "cost of living was up 2.9 percent from July 2017 to July 2018, [...] an inflation rate that outstripped a 2.7 percent increase in wages over the same period." For Washington state employees, general wage adjustments over the past 5 years [have ranged from 0% to 3%](https://www.ofm.wa.gov/state-human-resources/workforce-data-planning/workforce-data-trends/compensation/wage-adjustments-and-salary-increases).

# Research questions
- Which types of jobs are the most highly paid, which receive the lowest pay, and what are the ranges in pay within job groups?
- What is the distribution of public employee salaries, and what is the mean?
- Are salaries comparable for employees in similar jobs at different state universities? If not, why might this be?
- Do increases in salaries across time keep up with the rate of inflation?
- Are salary levels similar among similar job groups among different states, adjusting for relative price levels?

## Data used

- [Washington state employee salaries database](http://fiscal.wa.gov/Salaries.aspx). 
This dataset contains information on all Washington state employees, the agency they work for, their job titles, and salary information from 2014 to 2018 expressed in nominal dollars. The dataset is published by the US government, and is publicly available information pursuant to [RCW 42.56.210](https://app.leg.wa.gov/RCW/default.aspx?cite=42.56.210). This dataset will be the main source of information to help answer my problem statement, because it contains the most locally relevant information. 

- [California state employee salary data](https://publicpay.ca.gov/Reports/RawExport.aspx).
These datasets contain names of all California state public employees, their employing agency, job title, and their salary information expressed in nominal dollars as well as value of benefits, from 2009 to 2018. This data is published by the US government, and is publicly available information pursuant to [California Government Code section 12463](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?lawCode=GOV&sectionNum=12463). This dataset will inform my analysis on equity in salaries across different states. Similarly to the Washington state data, the ethical issues raised by this dataset mainly relate to privacy. 

- [Bureau of Economic Analysis prices and inflation data](https://www.bea.gov/data/prices-inflation). I plan to use the [GDP Price Index](https://www.bea.gov/data/prices-inflation/gdp-price-index) data to convert all salary data expressed in nominal US dollars to 2018 real US dollars in order to allow comparison of salary levels across time accounting for inflation, and in addition I hope to use the [Regional Price Parities by State and Metro Area](https://www.bea.gov/data/prices-inflation/regional-price-parities-state-and-metro-area) data to produce comparisons of salary levels between different states accounting to differences in costs of living. These datasets contain economic indices that relate to relative price levels in the US across time and states, which will advance my goals per the problem statement by allowing me to produce comparable financial estimates. This data is published by the US government, and is therefore in the public domain.

- State median household income estimates for [Washington](https://www.ofm.wa.gov/sites/default/files/public/dataresearch/economy/median_household_income_estimates.pdf) and [California](), expressed in nominal dollars. This data is published by the US government, and is therefore in the public domain.

# Ethical considerations
My main ethical concern in using this data pertains to the use of personally identifiable information, and the sensitive nature of salary data. The employee salary datasets contain individual's names, and I plan to remove these fields from the data hosted in my repository in order to respect individuals' privacy, as my analysis will not be focused on individual level data. Even though individual names may be removed, it may be possible for individuals to be identified within the dataset, as some combinations of job titles and institutions may be unique entries (for example, there is only one individual who is president of the University of Washington). To mitigate this concern, according to the [Washington state employee salaries dataset FAQ page](http://fiscal.wa.gov/SalaryDataFAQ.pdf), "employee names are withheld for victims of domestic violence and for employees whose jobs require confidentiality", and per [RCW 42.56.210](https://app.leg.wa.gov/RCW/default.aspx?cite=42.56.210), "information, the disclosure of which would violate personal privacy or vital governmental interests, can be deleted from the specific records sought".
It may also be possible for outliers to become evident throughout the course of this analysis, in cases where some individuals may be earning salaries much higher or lower than the mean for their job group or employer agency. It may be possible to identify corrupt or unfair practices in this way, which may harm the individuals involved.
My analyses will be performed on aggregated data, without reference to individuals, so I believe this analysis will not harm or disadvantage particular people, and will provide a benefit to employees as a whole.

# HC considerations
I believe the main beneficiaries of this analysis will be public employees at these agencies, as they will be able to compare their salaries to those of employees in similar capacities at their institution and other institutions. In addition, I believe this information can be used by state and university fiscal planning departments to inform standards of fair pay across institutions.
My analysis will not seek to explain differences in pay disparities, only to describe the observed trends. A related and useful analysis would be to assess salaries by employee demographic information such as sex or race, which may inform drivers of pay disparities.

# Potential limitations of the data

## Methodology
# Analysis procedure
My first step will be to download all the data and compile it for use in my programming environment. Next, I will clean the data, keeping only the fields of interest and grouping together employees by job groups. Once this is done, I can create aggregate metrics of salaries at the job, agency, and state level.

Next, I will apply economic techniques for adjusting the raw data expressed in nominal dollars to bring all values into real 2018 dollars using the US GDP deflator series provided by the BLS. This will allow comparisons of salaries in a common currency base year which is adjusted for inflation. I will also adjust salaries using the BLS price parities to account for price levels differing among states. These techniques will allow for an apples-to-apples comparison of salary information across states and time.

Finally, I will proceed to the analysis of the data through data mining and visualization. If time permits, I may also perform some statistical tests to check whether there are statistically significant differences among different groups.

# Figures
The primary means of communicating my findings will be through data visualizations. Some figures I plan to make are:
- boxplots of salaries across positions within states
- line graphs showing time trends across positions within states, with lines for median state household income
- stacked bar charts showing total employee salaries disbursed by job group or by employer
- grouped bar charts showing salaries across positions among different university employers

## Unknowns and dependencies

My only concerns relate to time constraints due to work and other personal commitments, as well as my health during the flu season. Barring any unexpected events, I fully expect to be able to complete this project by the end of the quarter.
