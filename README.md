# mass_Deportation_impact-in-US

# 📊 Economic Impact of Mass Deportation in the U.S.

This project presents a Power BI dashboard analyzing the **job losses and economic consequences** of a mass deportation policy in the United States.
The analysis is based on estimates from the **Economic Policy Institute (EPI)** article:  
🔗 [Trump’s deportation agenda would destroy millions of jobs](https://www.epi.org/publication/trumps-deportation-agenda-will-destroy-millions-of-jobs-both-immigrants-and-u-s-born-workers-would-suffer-job-losses-particularly-in-construction-and-child-care/)

---

## 📌 Key Findings

- **Total Job Loss:** 16 million  
- **Immigrant Job Loss:** 7 million (≈56.34%)  
- **U.S.-Born Job Loss:** 5 million (≈43.66%)  
- **Construction Sector** is the most impacted sector, accounting for over **60% of immigrant-related job losses**.
- **Washington, Virginia, and Wisconsin** show the highest state-level job losses.
- **States like California and Texas** are highly dependent on immigrant labor.
- **Deportation Trends (2014–2024):**
  - Sharp drop in 2020–2021 during the pandemic.
  - Significant rebound by 2024, with over **320,000** deportations.

---

## 📊 Dashboard Overview

The Power BI dashboard includes:

- **KPI Cards**: Total, Immigrant, and U.S.-Born Job Losses  
- **Pie/Donut Charts**:
  - Immigrant vs. U.S.-Born Job Loss Share
  - Job Losses by Sector (Construction vs. Others)
- **Bar Charts**:
  - Job Loss by State
  - Deportation Count by Year (2014–2024)
- **Filled Map**: U.S. State-Level Deportation/Job Loss Visualization
- **Slicer**: Filter visuals by state 
- **Icon Visuals**: For visual appeal and emphasis on key themes

| **Measure Name**                 | **Description**                                                  | **Example DAX Formula**                                                                      |
| -------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `Construction_immigrant_jobloss` | Total job loss among **immigrants in construction sector**.      | `Construction_immigrant_jobloss = SUM(JobData[Immigrant_Construction_Loss])`                 |
| `Construction_U.Sborn_jobloss`   | Total job loss among **U.S.-born workers in construction**.      | `Construction_U.Sborn_jobloss = SUM(JobData[USBorn_Construction_Loss])`                      |
| `constructionsector`             | Total job loss in **construction sector (all groups)**.          | `constructionsector = [Construction_immigrant_jobloss] + [Construction_U.Sborn_jobloss]`     |
| `other_immigrant_jobloss`        | Immigrant job loss in **non-construction sectors**.              | `other_immigrant_jobloss = [overall_immigration_jobloss] - [Construction_immigrant_jobloss]` |
| `other_U.Sborn_jobloss`          | U.S.-born job loss in **non-construction sectors**.              | `other_U.Sborn_jobloss = [overall_U.Sborn_jobloss] - [Construction_U.Sborn_jobloss]`         |
| `othersectors`                   | Combined job losses in sectors **other than construction**.      | `othersectors = [other_immigrant_jobloss] + [other_U.Sborn_jobloss]`                         |
| `overall_immigration_jobloss`    | **Total immigrant job losses** across all sectors and states.    | `overall_immigration_jobloss = SUM(JobData[Total_Immigrant_Loss])`                           |
| `overall_U.Sborn_jobloss`        | **Total U.S.-born job losses** across all sectors and states.    | `overall_U.Sborn_jobloss = SUM(JobData[Total_USBorn_Loss])`                                  |
| `overallsectors`                 | **Total job loss** combining all workers in all sectors.         | `overallsectors = [constructionsector] + [othersectors]`                                     |
| `Total_construction`             | **Construction sector total loss** from all groups.              | `Total_construction = [Construction_immigrant_jobloss] + [Construction_U.Sborn_jobloss]`     |


