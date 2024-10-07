# IPL Team Performance Analysis Project

## Overview
This project focuses on analyzing the performance of bowlers and overall team statistics in the Indian Premier League (IPL) from 2008 to 2020. By collecting data, cleaning it, and creating a Power BI dashboard, we aim to provide insights into various aspects of bowler performance, including wickets taken, runs conceded, and economy rate, as well as overall team performance metrics.

## Dataset
The data for this project was sourced from Kaggle. The dataset contains links to highlights of all IPL matches from 2008 to 2020. You can access the dataset [here](https://www.kaggle.com/datasets/narendrageek/can-generate-automatic-commentary-for-ipl-cricket?select=IPL_SCHEDULE_2008_2020.csv).

## Data Collection and Web Scraping
The data collection process involved the following steps:

1. **Data Cleaning:** Prior to web scraping, certain modifications were made to the URLs to ensure successful data extraction.
2. **Web Scraping:** We utilized Python's `requests` and `BeautifulSoup` libraries to scrape scorecard data from the URLs. The following Python code was used for this purpose:

   ```python
   import re
   import pandas as pd
   import openpyxl
   from openpyxl import load_workbook
   import requests
   from bs4 import BeautifulSoup

   # Load the dataset
   df = pd.read_csv(r'C:\Users\sahil\Desktop\IPL Project\Data\IPL_SCHEDULE_2008_2020.csv')

   # Initialize a list for failed URLs
   failed_urls = []

   # Loop through each URL in the DataFrame
   for url in df['URL']:
       # Fetch the data from the URL
       response = requests.get(url)
       soup = BeautifulSoup(response.content, 'html.parser')
       ...

3. **Error Handling:** Any URLs that failed to return data were logged in the `failed_urls` list. A total of **32 URLs** were unresponsive, which is minimal compared to the over **10,000 rows** of data successfully scraped.

## Data Storage
The scraped data is stored in an Excel file format (`.xlsx`) using the `openpyxl` library. This allows for easy access and manipulation of the data for further analysis and visualization.

## Data Analysis and Visualizations
The cleaned and scraped data was then loaded into Power BI, where various analyses and visualizations were created, including:

- **Bowler Profile:** Overview of individual bowler statistics such as wickets taken, runs conceded, and economy rate.
- **Discipline Analysis:** Stacked bar charts depicting the number of no balls (NB), wides (WD), and runs (R) conceded.
- **Wickets Distribution:** Pie charts showing the distribution of total wickets taken by each bowler.
- **Performance Over Time:** Line charts to track bowler economy rates and other metrics across matches.
- **Team Statistics:** Overall stats for teams, including total matches played, wins, losses, wickets taken, runs conceded, and extras given.

## Future Work
In future iterations of this project, I plan to develop match data highlights, providing additional insights into team and player performances.

## Dashboard Screenshots
![Dashboard Screenshot](https://github.com/Lord2709/PowerBI_Projects/blob/main/IPL%20Scorecard%20Dashboard/images/Dashboard%20ScreenShots/theme.png)
![Dashboard Screenshot](https://github.com/Lord2709/PowerBI_Projects/blob/main/IPL%20Scorecard%20Dashboard/images/Dashboard%20ScreenShots/home.png))
![Dashboard Screenshot](https://github.com/Lord2709/PowerBI_Projects/blob/main/IPL%20Scorecard%20Dashboard/images/Dashboard%20ScreenShots/drillthrough.png)
![Dashboard Screenshot](https://github.com/Lord2709/PowerBI_Projects/blob/main/IPL%20Scorecard%20Dashboard/images/Dashboard%20ScreenShots/bowlerprofile.png)

## Conclusion
This project serves as an extensive analysis of IPL bowlers and teams, contributing to a deeper understanding of performance metrics in cricket.

## Acknowledgements
Thank you to the creators of the dataset and any other resources used in this project.

## Contact Information
If you have any questions or feedback, feel free to contact me at [sahilchaudhari0927@gmail.com](mailto:sahilchaudhari0927@gmail.com).
