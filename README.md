# Optimization AirFrance

Optimizing passenger seating for group cohesion, aircraft balance, and special needs is crucial for both customer satisfaction and operational efficiency. 

## Contents

- [Requirements](#requirements)
- [Objectives](#objectives)
- [Constraints](#constraints)
- [Overview of the Data](#overview-of-the-data)
- [Data Structure](#data-structure)
- [Methodology](#methodology)
- [Results](#results)

## Requirements

This project uses the Gurobi Optimizer. If you have a license and want to reproduce the project, we recommend using Anaconda and installing Gurobi in Anaconda:

Open the Anaconda terminal (Anaconda Prompt) and navigate (using the cd command) to the Gurobi installation directory (the directory containing the setup.py file).

Run the command:

```bash
python setup.py install --user
```
Finally, check that you have the requirements for the project

```bash
python pip install -r requirements.txt
```

## Objectives

- **General Objective:** Propose a seating strategy that maximizes customer satisfaction and operational performance while adhering to a set of constraints.
- **Customer Satisfaction:** Ensure that groups of passengers are seated together to enhance their travel experience. Moreover,passengers in transit should be seated towards the front of the aircraft to facilitate quick connections.
- **Operational Performance:** Facilitate on-time departures and minimize the risk of missed connections.
- **Seat Selection Flexibility:** Offer a wide range of seating options to customers, accommodating their preferences and needs.

## Constraints

To achieve the objectives, the following constraints must be respected:

- **Maximum one passenger per seat**
- **Each passenger gets exactly one seat**
- **The central aisle is left free**
- **Aircraft centering** : The seating arrangement must maintain the aircraft's balance for safety and operational efficiency.
- **Passengers with reduced mobility** : Passengers with reduced mobility must be accommodated appropriately, ensuring their comfort and accessibility.

## Overview of the Data

The project analyzes flight instances over various dates, utilizing datasets that capture essential passenger information. 

The analysis of flight instances from October 21st to November 7th reveals a diverse range of scenarios on the Paris to Nice route. During these dates, we observed instances ranging from planes with low and moderate occupancy on October 21st and October 22nd to a significant increase in passenger volume on October 23rd, attributed to a large group leading to a fully occupied aircraft. 

Furthermore, October 24th showcased a highly filled plane, emphasizing fluctuations in passenger demand. The subsequent instances on October 30th, November 5th, and November 7th focused on passengers with reduced mobility, highlighting a specific aspect of travel dynamics

### Data Structure

The datasets include the following columns:

| Column           | Description                                   |
|------------------|-----------------------------------------------|
| **Numéro du groupe** | Group number associated with passengers      |
| **Femmes**           | Number of women in the group                  |
| **Hommes**           | Number of men in the group                    |
| **WCHR**             | Number of passengers using wheelchairs        |
| **TransitTime**      | Transit time for each passenger in the group  |

## Methodology

1. **Data Collection:** Gather data from various flight instances to understand passenger demographics and needs.
2. **Model Development:** Create a static model for initial seating arrangements, followed by a dynamic model allowing passenger seat selection.
3. **Optimization Algorithm:** Implement algorithms to optimize seating based on defined objectives and constraints.

## Results

The project aims to present visualizations and metrics that demonstrate the effectiveness of the seating optimization strategies, highlighting improvements in passenger satisfaction and operational efficiency. These metrics can be found in Assets/Report.

Our evaluation methods gave satisfying results regarding transit time and the conservation of groups. However some cases need to be analysed more precisely, particularly the case of big groups.

Furthermore, the dynamic model provides satisfying results as well, and is offering the passengers the right of choice and including wheelchair passengers in the analysis, satisfying all the restrictions, which is a great improvement. This constitutes a great added value for Air France by showing its customers its flexibility.

We also had the opportunity to implement early registration, and obtained plausible results, which respect all the previously mentioned constraints. On the other hand, in future analyses, the test of the dynamic model and global satisfaction could be made including all possible dates, which would add positively for Air France

## Conclusion

In conclusion, this study provides valuable insights into the complexities of passenger seating optimization in commercial aircraft, emphasizing the importance of balancing passenger satisfaction, safety standards, and operational efficiency. By addressing these key aspects, airlines like Air France can enhance the overall travel experience for passengers while meeting regulatory requirements and industry standards.


