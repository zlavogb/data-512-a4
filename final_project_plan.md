# Final project plan
# University of Washington, DATA 512, Autumn 2019
# Bianca Zlavog

## Introduction

My goal is to study how the base annual salary of public employees at institutions of higher education varies across different positions, institutions, states, and time. 
I aim to classify employees into a set of different job types among public institutions in Washington and California. I am interested in the relative magnitude and ranges of salaries across positions for public employees. I would also like to explore how employee salaries in different institutions, within the same state and different states, compare across similar positions. Finally, I hope to understand the trends in salaries across time, particularly over the last 5 years, and whether salaries have generally increased at a rate higher than inflation. I will compare the mean salaries across positions to the median state income levels. I also plan to adjust salaries to reflect the costs of living across different states. 

I believe this topic is interesting and relevant because many public employees' salaries are funded by taxpayers, and states have the legal obligation to make this information public. Per the [Washington State Fiscal Information site](http://fiscal.wa.gov/supporta.aspx), "state revenue and expenditure data [will] be made as open, transparent, and publicly accessible as is feasible with the goal of making government more accountable". Thanks to the public availability of this information, [cases of disproportionately high public employee salaries have come to light](https://latimesblogs.latimes.com/lanow/2010/07/bell-city-manager-might-highest-paid-in-nation-787637-a-year.html), to the backlash of the public. On the other hand, [issues of privacy arise](https://www.governing.com/news/state/gov-survey-disclosing-government-employee-salaries-troubles-public-officials.html) around the reporting of this data, because it includes publishing the names, salaries, and employer agencies of millions of people across the US. 

I also believe it will be interesting to identify any disparities and trends in pay between different types of positions and different institutions. [Legal disputes](https://caselaw.findlaw.com/wa-court-of-appeals/1126632.html) have arisen due to differences in pay among similar job classes in different state institutions. I believe this study will reflect on the fairness of employee salaries as reflected by disparities in pay. One known phenomenon is that the highest-paid Washington state employees are [university sports coaches, and are mostly men](https://patch.com/washington/across-wa/washingtons-millionaire-state-employees-are-men-mostly-coaches). 

It will be useful to understand whether employee salary increases over time have kept up with the pace of inflation. While some employers tie salary increases to inflation, overall, real wages across the country have been slow to increase. [According to one report](https://www.washingtonpost.com/business/2018/08/10/america-wage-growth-is-getting-wiped-out-entirely-by-inflation/), "cost of living was up 2.9 percent from July 2017 to July 2018, [...] an inflation rate that outstripped a 2.7 percent increase in wages over the same period." For Washington state employees, general wage adjustments over the past 5 years [have ranged from 0% to 3%](https://www.ofm.wa.gov/state-human-resources/workforce-data-planning/workforce-data-trends/compensation/wage-adjustments-and-salary-increases).

### Research questions
- Q1: What is the distribution of employee salaries, and what is the mean?
- Q2: Which types of jobs are the most highly paid, which receive the lowest pay, and what are the ranges in pay within job groups?
- Q3: Are salaries comparable for employees in similar jobs at different state universities?
- Q4: Are salary levels similar among job groups between different states, adjusting for relative price levels?
- Q5: Do increases in salaries across time keep up with the rate of inflation?

## Data used

- [Washington state employee salaries database](http://fiscal.wa.gov/Salaries.aspx). This dataset is available for download in XLSX format from the Washington states fiscal information site, produced by the Legislative Evaluation and Accountability Program Committee in collaboration with the Office of Financial Management.
This dataset contains information on all Washington state employees, the agency they work for, their job titles, and salary information from 2014 to 2018 expressed in nominal dollars. The dataset is published by the US government, and is publicly available information pursuant to [RCW 42.56.210](https://app.leg.wa.gov/RCW/default.aspx?cite=42.56.210). This dataset will be the main source of information to help answer my problem statement, because it contains the most locally relevant information. 

<details>
  <summary>Data Fields</summary>
	
| Variable      | Description |
| -----------   | ----------- |
| Agy           | Employer agency code |
| AgyTitle      | Employer agency name |
| Name          | Employee name, removed from hosted dataset |
| JobTitle      | Employee job title |
| Sal2014       | Salary in 2014 |
| Sal2015       | Salary in 2015 |
| Sal2016       | Salary in 2016 |
| Sal2017       | Salary in 2017 |
| Sal2018       | Salary in 2018 |
 
</details>


- [California state employee salary data](https://publicpay.ca.gov/Reports/RawExport.aspx). This data is available for download in zipped CSV format from the California state State Controller's Office, with a file for each agency and year.
These datasets contain names of all California state public employees, their employing agency, job title, and their salary information expressed in nominal dollars as well as value of benefits, from 2014 to 2018. A number of other fields are available which are not used in this analysis. This data is published by the US government, and is publicly available information pursuant to [California Government Code section 12463](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?lawCode=GOV&sectionNum=12463). This dataset will supplement my analysis on equality in salaries across different states.
																											
<details>
  <summary>Data Fields</summary>
	
| Variable      | Description |
| -----------   | ----------- |
| Year           | Calendar year of reported data |
| EmployerType      | Employer agency type |
| EmployerName          | Employer agency name |
| DepartmentOrSubdivision      | Employer department name  |
| Position       |  Employee job title |
| ElectedOfficial       |  Whether the employee was elected to their position |
| Judicial       | Whether the employee belongs to a judicial position |
| OtherPositions       | Any other job titles the employee held with the respective agency during the calendar year |
| MinPositionSalary       | Minimum annual salary for the position |
| MaxPositionSalary | Maximum annual salary for the position |
| ReportedBaseWage | Base salary, only applicable for data before 2011 |
| RegularPay | Base salary earned in the calendar year |
| OvertimePay | Overtime salary earned in the calendar year |
| LumpSumPay | One-time salary payments earned in the calendar year |
| OtherPay | Other salary earned in the calendar year |
| TotalWages | Total salary earned in the calendar year |
| DefinedBenefitPlanContribution | Employer contribution to benefit plan |
| EmployeesRetirementCostCovered | Employee contribution to benefit plan |
| DeferredCompensationPlan | Employer contribution to retirement plan |
| HealthDentalVision | Employer contribution to health plan |
| TotalRetirementAndHealthContribution | Total employer contribution to benefit plans |
| PensionFormula | Pension formula determining employee retirement benefits |
| EmployerURL | Web address of employer agency |
| EmployerPopulation | Population of employer agency |
| LastUpdatedDate | Date the employer's data was last updated |
| EmployerCounty | County that an employer is based in |
| SpecialDistrictActivities |  special district information |
| IncludesUnfundedLiability |  whether employer agency includes payments toward the unfunded liability of the employer sponsored retirement plan |
| SpecialDistrictType | special district information |

</details>

- [Bureau of Economic Analysis prices and inflation data](https://www.bea.gov/data/prices-inflation). I plan to use the [GDP Price Index](https://www.bea.gov/data/prices-inflation/gdp-price-index) data to convert all salary data expressed in nominal US dollars to 2018 real US dollars in order to allow comparison of salary levels across time accounting for inflation, and in addition I hope to use the [Regional Price Parities by State and Metro Area](https://www.bea.gov/data/prices-inflation/regional-price-parities-state-and-metro-area) data to produce comparisons of salary levels between different states accounting to differences in costs of living. These datasets contain economic indices that relate to relative price levels in the US across time and states, which will advance my goals per the problem statement by allowing me to produce comparable financial estimates. This data is published by the US government, and is therefore in the public domain.

- State median household income estimates for [Washington](https://www.ofm.wa.gov/sites/default/files/public/dataresearch/economy/median_household_income_estimates.pdf) and [California](), expressed in nominal dollars. This data is published by the US government, and is therefore in the public domain.

### Ethical considerations
My main ethical concern in using this data relates to the use of personally identifiable information, and the sensitive nature of salary data. To mitigate this concern, according to the [Washington state employee salaries dataset FAQ page](http://fiscal.wa.gov/SalaryDataFAQ.pdf), "employee names are withheld for victims of domestic violence and for employees whose jobs require confidentiality", and per [RCW 42.56.210](https://app.leg.wa.gov/RCW/default.aspx?cite=42.56.210), "information, the disclosure of which would violate personal privacy or vital governmental interests, can be deleted from the specific records sought". The Washington state employee salary datasets contain individuals' names, which I plan to remove from the data hosted in my repository in order to respect individuals' privacy, and because my analysis will not be focused on individual level data. In contrast, the California state employee salary files do not contain names of individuals.

Even though names may be removed, it may be possible for individuals to be identified within the dataset, as some combinations of job titles and institutions may be unique entries (for example, there can only be one President of the University of Washington in a given time period). 

It may also be possible for outliers to become evident throughout the course of this analysis, in cases where some individuals may be earning salaries much higher or lower than the mean for their job group or employer agency. While it may be possible to identify corrupt or unfair practices in this way, the privacy of individuals involved in this analysis may be breached as a result.

### Human-centered considerations
The main beneficiaries of this analysis are public employees at these agencies, as they will be able to compare their salaries to those of employees in similar capacities at their institution and other institutions. In addition, I believe this information can be used by state and university fiscal planning departments to inform standards of fair pay across institutions.

My analysis will not seek to explain differences in pay disparities, only to describe the observed trends. A related analysis would be to assess salaries by employee demographic information such as sex, race, and education level, which may inform drivers of pay disparities.

### Potential limitations of the data
- If someone began their employment partway through the calendar year, it is unclear whether their annual base salary is displayed in the data, or just the amount earned over the period they worked. If it is the latter, this will skew the data toward lower salaries and will be unlikely that these observations can be filtered out without additional information on employee start date.
- Some employees in the dataset (such as sports coaches) [are not paid directly by tax funds](http://fiscal.wa.gov/SalaryDataFAQ.pdf), but rather by funding raised by their department. This makes it harder to identify which employees' salaries are directly funded by taxpayers.
- In the Washington state data, student employees are subject to stricter privacy laws around salary information, so job groups such as teaching assistants [are not available in the data](http://fiscal.wa.gov/SalaryPersonnelIncluded.pdf).
- Unionized employees likely earn higher salaries than non-unionized employees, but employee union status is not available in this database, so it will be harder to parse out pay differences due to union status.
- There is no information available on part time or full time employee status, which is likely another driver of pay differences.
- Other limitations may arise as I begin working with the data.

## Methodology
### Analysis procedure
My first step will be to download all the data and compile it for use in my programming environment. For this assignment I will produce an R markdown notebook using the R programming language, and particularly the `data.table` and `ggplot2` packages. Next, I will clean the data, keeping only the variables of interest, keeping data on employees of higher-education institutions, and grouping together employees by job groups. Then, I can create aggregate metrics (means, medians, ranges) of salaries at the job, agency, and state level.

Next, I will apply economic techniques for adjusting the raw data expressed in nominal dollars to real 2018 dollars, using the US GDP deflator series provided by the BLS. This will allow comparisons of salaries across time adjusted for inflation. In the analysis of salaries across states, I will scale salaries using the BLS state price parities to account for differing price levels among states. These techniques will allow for an apples-to-apples comparison of salary information across states and time.

Finally, I will proceed to the analysis of the data through data mining and visualization. If time permits, I may also perform some statistical tests to check whether there are statistically significant differences in salaries among different groups.

### Figures
The primary means of communicating my findings will be through data visualizations. Some figures I plan to make are:
- histogram of employee salaries by state
- boxplots of salaries across positions within states
- line graphs showing time trends across positions within states, with lines for median state household income
- stacked bar charts showing number of employees by job group or by employer agency
- stacked bar charts showing total employee salaries disbursed by job group or by employer agency
- grouped bar charts showing salaries across positions among different university employer agencies

## Unknowns and dependencies

My only concerns relate to time constraints due to work and other personal commitments. Barring any unexpected events, I fully expect to be able to complete this project by the end of the quarter.
