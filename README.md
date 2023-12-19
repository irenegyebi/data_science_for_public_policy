# Examining the relationship between H1-B Visa Policies and Occupational Employment Trends in USA.
---


![nextsource.com(March 5, 2021/Kyle Torti
)](https://www.nextsource.com/wp-content/uploads/2021/03/h1b-visa.jpg)

### Problem Statement <a id='pb'></a>

The technology sector in the United States relies heavily on high-skilled foreign workers to fill talent gaps, particularly in science, technology, engineering and math (STEM) occupations. The H1-B visa program allows U.S. companies to temporarily employ foreign workers in specialty occupations. However, the H1-B visa cap limits the number of foreign workers that can be hired each year. At the same time, employment in many STEM occupations has fluctuated over the past decade. This raises important policy questions about the relationship between H1-B visa policies and the supply of high-skilled workers in the U.S.

This project aims to investigate and understand the complex relationship between H1-B visa policies and occupational employment patterns using HI-B disclosure data (2011-2022) from [the Office of Foreign Labor Certification](https://www.dol.gov/agencies/eta/foreign-labor/performance)**(OFLC)** and Occupational and Wage Statistics data from the [Bureau of Labor Statistics](https://www.bls.gov/oes/tables.htm)(BLS). Examining these historical datasets would provide insights into how visa policies aimed at supplying skilled technical talent relate to changing labor market demands.


### Background <a id='bg'></a>


The United States has historically attracted a significant number of highly skilled immigrants in Science, Technology, Engineering, and Mathematics (STEM) fields through the H1-B visa program. The H1-B visa program, administered by the U.S. Citizenship and Immigration Services (USCIS), allows U.S. employers to hire foreign workers in specialized occupations, often filling gaps in the domestic labor force and contributing to the innovation and competitiveness of the U.S. economy. However, the program has undergone various policy shifts and reforms aimed at protecting the interests of American workers, addressing skills shortages, and maintaining national security. These policy changes including alterations in visa allocation methods, wage requirements, and limitations on visa duration, among others, have the potential to impact occupational employment trends.

The **objective** of this project is to:
1. Examine historical policy changes and regulations in the H1-B visa program, and how they have impacted the utilization of H1B visas?
   
2. Identify H1B occupational employment trends in terms of job growth, wages, and demand for labor in the United States?

3. Identify trends in the utilization of H1-B visas by Employers.

This project can provide valuable insights for job seekers in STEM-related industries, contributing to informed decision-making in an ever-evolving labor market.


### Dataset Description <a id='dd'></a>

#### H1-B Disclosure data (OFLC)

The H-1B program allows companies in the United States to temporarily employ foreign workers in specialty occupations. As part of the requirements of the program, companies must disclose information about the H-1B employees they sponsor, including details like the employee's job title, salary, work location, and more. This disclosure data provides valuable insights into how companies utilize the H-1B program.

"Disclosure data consists of selected information extracted from nonimmigrant and immigrant application tables within the Office of Foreign Labor Certification's case management systems. The data sets provide public access to the latest quarterly and annual data in easily accessible formats for the purpose of performing in-depth longitudinal research and analysis. Each data set is cumulative for the fiscal year, containing unique records identified by the applicable OFLC case number based on the most recent date a case determination decision was issued. Information that appears in these records is provided by employers and system-generated metadata, such as received dates and decision dates. Any typographical errors or other data anomalies (e.g., incomplete or blank data fields, etc.) may be due to internal data entry or other external customer errors in completing and submitting the applications for processing" [OFLC](https://www.dol.gov/agencies/eta/foreign-labor/performance). <br><br>


**H1B Data Preprocessing in Excel:** <br>
I conducted comprehensive data preprocessing on the H1B dataset obtained from the Office of Foreign Labor Certification (OFLC) in Excel to enhance its suitability for analysis in Python. The preprocessing involved several key steps to ensure data integrity and consistency.

* Column Cleaning:
Removed unnecessary columns to streamline the dataset.
* Column Renaming:
Renamed certain columns for consistency and improved readability.
* Handling Missing Data:
Cleaned/Dropped some missing or incomplete data.
* Subsampling:
    * Extracted a representative subset of 50,000 data points for each year.<br>
    * Subset spans from 2011 to 2022, optimizing dataset size for computational efficiency in python.
* The resulting dataset is available on my github repo and will be used for this analysis. <br><br>
* I recommend downloading the datasets and reading them locally, rather than reading directly from github.


**Data Dictionary:** <br>

**Field Name**          |**Description**                                                                                                                         
:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------
Submitted_Date          |Date and time the application was submitted                                                                                                                                                                                            
Employer_Name           |Employer's name                                                                                                                                                                                                             
Employer_City           |Employer's city                                                                                                                         
Employer_State          |Employer's state                                                                                                                                                       
Job_Title               |Job title                                                                                                                               
Decision_Date           |Date certified or denied                                                                                                                                                                                                               
Case_Status             |Approval status - certified or denied                                                                                                   
Wage_Rate               |Employer's proposed wage rate                                                                                                           
Wage_Unit_of_Pay        |Unit of pay for proposed wage rate - yearly, hourly etc.                                                                                                                                      
Full_Time_Position      |Y = Full time; N = Part time position                                                                                                   
Worksite_City           |Work city (location of the job opening)                                                                                                 
Worksite_State          |Work state (location of the job opening)                                                                                                
Prevailing_Wage         |Prevailing wage rate                                                                                                                                                                                       
                                        

#### Occupational and Wage Statistics data (BLS)

The Occupational Employment and Wage Statistics (OEWS) program at the Bureau of Labor Statistics produces employment and wage estimates for over 830 occupations. Data is collected from a semi-annual mail survey of non-farm establishments, providing key insights into the state of the labor market. The OEWS survey generates information on the number of workers in given occupations along with percentiles of their wage distributions. This allows for an understanding of employment levels and earning potentials across different jobs [BLS](https://www.bls.gov/oes/).

**Data Dictionary:** <br>

**Field**  |**Field Description**                                                                                                                                                                           
:----------|:-----------------------------------------------------------------------------------------------------------------------------------------                        
state      |The State name                                                                                                                                                                            
occ_title  |The Standard Occupational Classification title for the occupation                                                                                                                                          
tot_emp    |The estimated total employment rounded to the nearest 10 (excludes self-employed)                                                                                                                                                 
a_mean     |The mean annual wage                                                                                                                                                                                    
a_median   |The annual median wage (or the 50th percentile)                                                                     
