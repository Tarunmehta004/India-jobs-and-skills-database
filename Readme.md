## About
This repository aims to collate, organise and analyse data on skills in India's labour market.

Unlike the United States or the European Union, India does not have a standardised skills database. Rather, we have National Occupation Standards (NOSes) that specify the standards of performance an individual must achieve when carrying out a function in a workplace. Each job is a combination of two or more NOSes, which themselves consist of multiple tasks and duties (called performance criteria (PC)). While the PCs provide very detailed insights into a job, and can be used as proxies for the skills required to perform well in a job, they are written in a non-standardised manner. This makes any ready-made analysis of skill requirements across jobs and sectors almost impossible.

Through this repository, I mainly aim to make the India's skills databse (based on approximately 1400 jobs )accessible to researchers. I will also complement this data with some meta analysis to demonstrate the use case for such a database.    

## Repo structure
This repo consists of the following major folders:
1. `Skills and jobs database`: This folder contains codes and databse of all jobs with valid Qualification Files at the [National Qualification Register][https://www.nqr.gov.in/]. It is only for the jobs in the NQR, with valid and clean documentation, that skills extraction is possible. 

<!-- # Steps taken
1. Download QF excel list from NQR website.
2. NQR website doesn't have QF links. Scrape it manually through Selenium.
3. Although the number of QFs in step 1 and 2 match, there are NQR code inconsistencies in about 132 of them. I remove these occupations from the final analysis.
4. Some QF links are invalid. These are also removed.
5. Extract NCO codes using regex
6. Extract PC tasks using regex. For ~660/2080 jobs PC tasks could not be extracted. -->
