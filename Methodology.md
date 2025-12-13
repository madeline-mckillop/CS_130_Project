# How I Identified the First 1-on-1 Contestants and Top-Four Outcomes

## Data Source(s)
- I downloaded the dataset from [https://github.com/fivethirtyeight/data/tree/master/bachelorette]. 
- The specific file I used is `bachelorette.csv`, which contains data and information about both Bachlorette and Bachelor contestants, including their participation in dates, rose ceremonies and their final outcomes in the show.


## Data Preparation/Cleaning
- One of the first things I did was import the CSV file into a pandas DataFrame for analysis.
- The second step involved filtering the dataset to include only contestants from "The Bachelorette" series. I did this by selecting rows where the "show" column contained "The Bachelorette".
- Another important step was to clean/delete multiple headers that were present in the dataset. I ensured that only one header row remained for accurate data referencing.
- I created new Boolean columns (first_1on1, top4, and made_top4) and initialized all values to False.
- I went on to loop through each season of "The Bachelorette" to identify who got the first 1-on-1 date for each season by scanning the DATES-* columns for the value "D1". If multiple contestants had a 1-on-1 date in the same week, I chose to keep all of the contestants who had a 1-on-1 date that week.
- I stored the results of the contestants who received the first one-on-one date of the season by updating the first_1on1 column.
- After that I calculated the total number of dates each contestant participated in using the DATES-* columns and stored this value in a new column called date_count.
- I then determined the Top 4 contestants in each season by sorting contestants in descending order based on date_count.
- Next I stored the results of the Top 4 contestants using the top4 column.
- Lastly, I Identified contestants who both received the first one-on-one date and finished in the Top 4, and recorded this outcome in the made_top4 column. 


## Assumptions
- I assumed that the dataset accurately reflects the events of each season of "The Bachelorette" without any missing or incorrect data entries.
- I have made an assumption that the first 1-on-1 date is a significant piece of a contestant's likelihood to reach the Top 4, which guided my analysis.
- I Assumed that contestants with the highest total number of dates accurately represent those who advanced furthest in the season. 
- Assumed that all DATES-* columns were comparable across seasons, even though the number of weeks varied.


## Limitations:
- I originally intended to identify the top 5 contestants, but due to the dataset structure and the way eliminations are recorded, I adjusted my analysis to focus on the Top 4 contestants instead.
- The dataset does not explicitly label eliminations, so advancing to the Top 4 was inferred from date frequency rather than official placement.
- Variations in season structure such as differing numbers of weeks or date opportunities may affect date counts.
- Some seasons included multiple contestants receiving a one-on-one date in the same week, which may reduce the clarity of “first” one-on-one.
- The analysis does not account for off-camera events or producer influence that could affect outcomes.