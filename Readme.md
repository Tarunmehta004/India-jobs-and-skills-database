# Steps taken
1. Download QF excel list from NQR website.
2. NQR website doesn't have QF links. Scrape it manually through Selenium.
3. Although the number of QFs in step 1 and 2 match, there are NQR code inconsistencies in about 132 of them. I remove these occupations from the final analysis.
4. Some QF links are invalid. These are also removed.
5. Extract NCO codes using regex
6. Extract PC tasks using regex. For ~660/2080 jobs PC tasks could not be extracted.