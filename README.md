# Brazil Traffic Incidents E.D.A.

## 1.Overview
This project encompasses an exploratory data analysis of Brazilian traffic accidents documented by the Brazilian Federal Police from 2007 to the present day. The data, stored in separate CSV files for each year, underwent a process of combination, cleaning, and validation to create a cohesive dataset. This unified dataset was then imported into Tableau for an in-depth analysis aimed at uncovering potential trends.

## 2. Motivation
I started this project due to its profound implications for public safety and societal welfare. Upon discovering this comprehensive dataset on Kaggle with data provided by the Brazilian Federal Police, I felt compelled to analyse it. The primary aim of this project is to uncover underlying trends, correlations, and potential causative factors within the data. Ultimately, the goal is to illuminate crucial insights beneficial to policymakers, law enforcement agencies, urban planners, and road maintenance institutions. By comprehending the dynamics of these accidents, our objective is to contribute to the formulation of proactive measures that can effectively mitigate risks, bolster road safety, and, most importantly, save lives. On a personal level, the prospect of utilizing data-driven insights to address societal challenges and elevate safety standards motivates me to delve deeper into this analysis. It's driven by my passion for leveraging data to create a tangible positive impact within our communities.

### About the dataset
The dataset is available for download [here](https://www.kaggle.com/datasets/tgomesjuliana/police-traffic-incidents). The user who shared this datasat has downloaded the data from the official website of the Brazilian Federal Police.

### Data Cleaning and Validation
Access the Jupyter Notebook containing all data cleaning and validation steps [here]

### Dashboard
Explore the interactive dashboard by clicking [here](https://public.tableau.com/app/profile/daniele.d.epiro/viz/BrazilTrafficIncidents/ExploringBrazilianTrafficIncidents)

## 3. Setting-up the project
After I have identified the dataset and the goals I just mentioned above, I finally breakdown the project into 4 steps:
* Review and explore the content of each .csv file:
   - Load each .csv file using pandas.
   - Inspect the structure, columns, and data types.
   - Check for missing values, outliers, or inconsistencies.
   

* Combine all .csv files into a single dataset.
   - Handle any conflicts or discrepancies in the data during the merging process.

* - Data cleaning and validation
   - Perform data cleaning operations like handling missing values, standardizing formats, and removing duplicates.
   - Validate the cleaned data to ensure accuracy and consistency.
   :

* Import the cleaned dataset into Tableau.
   - Explore data in Tableau
   - Create visualizations that address the project goals.
   - Design a dashboard that provides an intuitive and informative interface for end-users.

### Prerequisites
First a knowledge of the portuguese language is needed because values are obviously recorded in the official language of the country.
To run this project, ensure you have the following installed:
* Jupyter Notebook:
    - Used to execute Python scripts and interactively work with the code.
    - You can access Jupyter Notebook through Anaconda, a popular Python distribution.
    - If you don't have Anaconda installed, you can download it [here](https://www.anaconda.com/download).

* Tableau Public:
    - Utilized for data visualization purposes.
    - Tableau Public is a free tool that allows you to create and share interactive data visualizations.
    - You can download it [here](https://www.tableau.com/products/public/download).

 ## 4. Main Challenges 

* Encoding:
While loading the csv I had several warning and to efficiently load the data I used the following code:
* Combine the dataset
The latest records hade more field compared to the ones in the early years. For example UOP and Delegacia fields started to be recorded only in the last years and I decided to keep this fields because they can help understand which police station was controlling the area of the accidents. For the early years they were validated as missing value.
```Python
import pandas as pd
# correctly importing csv files
year_2007 = pd.read_csv('Dados_PRF_2007.csv', encoding='latin1', delimiter=';', dtype={'br': str, 'km': str})
``` 
* Combine the dataset
The latest records hade more field compared to the ones in the early years. For example UOP and Delegacia fields started to be recorded only in the last years and I decided to keep this fields because they can help understand which police station was controlling the area of the accidents. For the early years they were validated as missing value.

* Date field
The date field was not recorded uniformely along the years so I had to uniformatting the date field in order to have all records in this format dd/mm/yyyy.

* Some cities in different states had the same name
I have identified them and added the state name next to the name recorded in the state field to avoid wrong result when calculating the number of accidents that happened in a city

* Duplicates Record
There where some accidents recorded multiple time so I excluded all records where the same id, date and time where duplicates.  
 
* Duplicate ID
Some citizens(ID) where involved in more the one accident during these years

## 5. Finding and Insights

This analysis reveals a consistent reduction in the number of car accidents since 2013, with a projected stabilization at the 2023 level until 2025.

Surprisingly, São Paulo, despite its high population and traffic density, doesn't claim the top spot for the highest number of crashes. Instead, the city of Curitiba in Paraná emerges as the leader in reported accidents.
Further investigation identifies Minas Gerais as the state with the highest number of accidents, followed closely by Santa Catarina, Paraná, Rio Grande do Sul, and Rio de Janeiro. Notably, the analysis pinpoints BR 101 and BR 116 as the most perilous roads, indicating a concentration of accidents along these routes.

These insights shed light on shifting accident trends, surprising city-specific statistics, and the identification of specific states and roads as focal points for heightened vigilance and targeted interventions. The data underscores the necessity for tailored strategies aimed at reducing accidents and improving road safety in these identified regions and along critical routes

## 6. Conclusion

The insights derived from this report hold significant potential to benefit numerous stakeholders seeking a comprehensive understanding of car accidents' statistical trends in Brazil. By delving into the data, this analysis offers a valuable resource for law enforcement agencies and road maintenance institutions. The identification of hazardous road sections presents an opportunity to prioritize safety measures and undertake targeted improvements.

Moreover, understanding the root causes of these accidents enables governmental and non-governmental entities to develop tailored awareness campaigns. Pinpointing the primary reasons behind these incidents empowers authorities to craft effective initiatives that promote safe driving practices among motorists.

The dashboard's 'dangerous site identifier' stands out as a particularly valuable tool. It allows for the identification of specific kilometer ranges where accidents are most prevalent. This information serves as a pivotal resource, enabling stakeholders to focus their efforts on areas requiring immediate attention and intervention.
