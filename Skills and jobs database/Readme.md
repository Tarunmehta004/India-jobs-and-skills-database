## About
This repository details out the process to scrape the PDF links of Qualification Files, specifying the tasks and duties for a job, from the NQR website. Further, it also contains the code files to extract these tasks and skills from the PDFs and perform preliminary cleaning on the text.

## Repository structure
This repo consists of the following major files:
1. `PDF_suffix_webscraped.txt`: Each qualification file is given a unique ID that can be combined with NQR's [base link](https://www.nqr.gov.in/qualifications/) to land on the corresponding jobs webpage. This text file contains a list of 2,227 unique ID, each corresponding to a single job. This list was extracted by scraping the necessary web elements from the NQR website.

1. `Scrape QF links 2Sept25.iPYNB`: This notebook builds a webdriver that visits each one of the jobs listed in Step-1 and scrapes all the relavant data related to its name, description, NQR code, and the PDF link. Results from this exercise are stored in `Active QF list with links 2Sept25.csv`.

1. `Download QFs 2Sept25.iPYNB`: This notebook cleans the `Active QF list with links 2Sept25.csv` file for invalid and inconsistent entries, reducing the number of jobs to 2080. Further, it visits each of the PDF link and downloads the associated QF to the local directory. The mapping between occupation name and final list of valid entries is stored in `Final qf list_cleaned.csv`. PDFs have not been uploaded to github to save memory.

1. `Extracting text from QFs 11Sept25.iPYNB`: This notebook reads each of the PDFs in `Final qf list_cleaned.csv` and uses regular expressions to extract data on performance criteria. Due to general difficulties in extraction of texts from PDFs, combined with non-standardised format of the QFs, reliable PCs could only be extracted for 1420 of the 2080 QFs. Results from the PC extraction are stored in `Unclean jobs and skills database 15Sept25.parquet`. 

1. `gemma_Skills cleaning 29Sept25.iPYNB`: Some of the skills extracted in the previous step were either incomplete or contained typographical errors. This notebook corrects for these issues by running each job through Google's Gemma 3 model (12 billion parameters). To respect API limits, each run was done in batches over multiple days and results stored in `llm_batches`.

1. `gemini_Residual skills cleaning 6Oct25.iPYNB`: Some of the jobs remained unprocessed by Gemma. I ran a second iteration for these jobs (~172) using Gemini Flash Lite. Results from this run were again stored in `llm_batches`.

1. `Batch compilation 6Oct25.iPYNB`: This notebook collates all batches and creates the final jobs database - `Cleaned Jobs and Skills database 6Oct25.parquet`. I recommend that you use this as the final file for all downstream tasks.

PS: Data files described above would only be made available after March 2026.