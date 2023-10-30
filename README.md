# Final-Project-Tableau

## Important Note for Tableau Public Users:
1. Please open "FAA_Public.twbx".  This is to be used with the subdirectory "FAA.twb Files" which contains the extracted/packaged data (.hyper file).  This file will enable Tableau Public users to see the Tableau workbook, sheets, dashboards, and story.
2. The file "FAA.twb" is the same content as above, but for users of the Tableau Desktop Professional verison of Tableau.

## Project/Goals
1. Derive insights from the cleaned dataset (available at: <a href="https://docs.google.com/spreadsheets/d/1V-tOmmtGtiY_3XMnYtVblDhlj_kzLBxa/edit?usp=sharing&ouid=108445376648788204707&rtpof=true&sd=true.">faa_data_subset.xlsx</a>) dervied from the FAA Wildlife Strike Database, which contains records of wildlife strikes reported by airlines, airports, pilots, and other sources.
2. Explore the dataset using Tableau visualizations and analytical tools like forecasting and clustering, to find interesting patterns, trends, outliers, or anything remarkable from the data.
3. Come up with different questions to answer using Tableau visualizations, dashboards and stories, which will be presented in a 5 minute presentation on Monday, October 30, 2023.

## Process
### Load dataset into Tableau and Data Exploration Using Visualizations
- Created a number of initial visualizations (these sheets are colored "mustard" in my Tableau workbook) to get a sense of the data, such as:
    - Location of reports (on US map), including sum of strike counts as size/bubbles
        - Added Running Total of of # Strikes over Years in a moving graphic on the map (each year is a Tableau "page"), and included in a Dashboard
    - Time (Hour of Day) from "Collision Date and Time" vs. "When: Time of day" field, to get a sense of whether I could create a Calculated Field to "fill in" incomplete When: Time of Day data (Result: there is no real pattern/rule for "Time of Day" reported when compared to Hour of Day that the collision actually occured, so no rule I can apply to reliably and consistently fill in missing data that wouldn't create bias - so I abandoned this plan).
    - Count of # Strikes by **each** Wildlife Species.
        - This led me to create an interactive visualization (horizontal bar chart) that looked at a number of selectable dimensions against "Top N" to quickly get a sense of the characteristics of the dataset and areas I wanted to hone in on for my deeper analysis.
        - The interactive horizontal bar chart was so good that I included it in one of my dashboards.
    - Explore number of strikes over time, exploring different time granularities with expansion of "Collision Date and Time" dimension.
        - Broke the above into different portions, settling on "Effect: Impact to flight" and "Effect: Indicated Damage" fields.
            - Looked at both a "total number" and a normalized (out of 100%) version of that visualization.
    - Count of Strikes and filtered/categorized by "Effect: Indicated damage" and "Effect: Impact to flight" across generic quarters, for each wildlife species.
        - This visualization was very busy and there was no easy way to simplify this visualization, so it functioned to help me explore the data but was not included in a dashboard.
    - Number of Strikes by "generalized Quarter", broken out by Species (color) to confirm the general pattern that Q3 has highest number of strikes over all years.
    - "Cost: Total $" and "Cost: Aircraft time out of service (hours)" plots against Wildlife Species.  This provided some interesting trends that I then decided to build interactivity into, simplify, and include in a dashboard.
    - Clustering:
        - In "Cost: Aircraft time out of service" vs. "Cost: Total $" scatterplot
        - When measuring only against a single dimension:
            - "# Strikes"
            - "Total $ Cost"
            - "Hours out of Service"
        - Decided to include all 3 of these in a dashboard for "backup slides of interest" section of my Tableau Story (won't be presented)
- Decided which visualizations should be tweaked and finalized for inclusion in a set of Dashboards (these sheets are colored "blue" in my Tableau workbook)
### Create Finalized Versions of Visualizations to Include in Dashboards
- Ended up creating 4 Dashboards with Visualizations
- Built a lot of interactivity into each visualization to provide maximum value in limited screen real-estate and with limited number of pages available for vieweing (4 sets of "slides" or "Story Points")
### Built a Dashboard Page with Salient Points/Text to Capture Significant Findings
- Built a single Dashboard or Story Point/"slide" that summarizes salient points that a reader who does not have access to the live presentation, can consider when interacting with the visualizations
- Each of these points are also significant findings that I saw through my visualizations/exploration and additional research.
### Build a singular Tableau Story with 5 Dashboards
- Each Dashboard functions as a singular Story Point, or "slide" in my "Tableau Story functioning like a Powerpoint Deck".
    - The first 4 Dashboards have Visualizations and interactivity and legends on each
    - The last (5th) Dashboard has words only:  6 boxes with salient points and findings, which should also inform the end-user's interaction with the interactive features on each Visualization.
        - This Story Point/"slide" is "wordy" and "busy", but was created to impart information and context to end-users who were not present at the presentation and only have access to the Tableau Story on Tableau Public Server.

## Results
- I chose **Option 2** and to work with the FAA Wildlife Strike cleaned data.
- See above under "Process" for a detailed description of all the Visualizations I created, which ones became part of my official Dashboards, and the rationale fo why.
- See the last "Story Point" or "Slide" in the Tableau Story to see all the salient points, trends, significant findings, and interesting patterns, I discovered.

#### Data Questions Posed:
The data questions I posed in developing my Dashboards were:
1. Which Animals (Species) cause the most number of strikes?
2. During which Phase of Flight do the most number of strikes occur?
3. What reported "Time of day" do the most number of strikes occur?
4. How are the "Amount of Damage" categories "distributed" in terms of where the most/least/mid Number of Strikes occur?
5. How are the Airports distributed in terms of Number of Strikes occuring or reported?
6. What States have the most Number of Strikes?
7. Where on the map of the US are the Stikes occuring / reported?  What are the relative sizes (numbers) of Strikes being reported in each location on the map?
8. What are the trends for Strike reporting over time?
    - What is the frequency of "Effect: Indicated Damage" and "Effect: Impact to flight" in each Quarter's reported Strikes?
    - How does the "Effect: Impact fo flight" differ when the crew determines there is damage vs. "No damage"?
    - How do the trends on the 2 points above change/look when "normalizing" the data so that the numbers of "Effect: Impact to flight" are counted as a proportion of the total number of strikes (i.e. out of 100%)?
9. During what time of year are the most number of Strikes occuring?
10. Which Wildlife Species comprise the reports of Number of Strikes in each portion of the year ("generalized Quarter")?
11. What are the Top N Wildlife Species causing the most damage in terms of "Cost: Total $ Cost" and "Cost: Aircraft time out of service (hours)"?
    - (Please note, a lot of fields were null for these 2 columns, so the conclusions drawn here may be inaccurate and/or there may be selection bias from the perspective of only larger $ Cost or Time out of service values are being reported)
12. What is the forecasted number of strikes per year for each of the Top 2 Wildlife Species causing the most monetary and "time out of service" impact?
13. What clusters emerge, if any, when looking at:
    - Number of Strikes
    - Total $ Cost of Damage
    - Hours aircraft out of service
14. Did the FAA implement new policy, procedures, or approach, or otherwise make strike reporting mandatory, to explain the increase in Number of Strikes starting around 2009 and increasing every year afterwards, or is there another phenomenon occuring which is causing a natural increase in Number of Strikes?
    - Stated another way:  There is an increase in Number of Strikes starting 2009 and continuing onward until 2015.  Is this due to reporting requirements or a natural phenomenon occuring with the wildlife?

## Challenges 
- As always, more time would allow more data gathering to fill in missing data (important missing data such as Total $ Cost and Aircraft hours out of service).
- For as much interactivity as I was able to build into my Visualizations and resulting Dashboards/Story, I was not able to figure out how to build in interactivity that would allow the end-user to collapse or expand the "Collision Date and Time" field (YEAR, QUARTER, MONTH) that is possible within the Sheet.
- I initially started with a different dataset (AirBnb) but found that dataset to be non-optimal in terms of its data quality, cleanliness and number of features, so moved onto using this FAA cleaned dataset after spending some hours working/doing EDA using visualizations with the AirBnb dataset.
    - This demonstrated the power of being able to do quick Visualizations as part of EDA!
- This FAA Wildlife Strikes dataset is a very feature-rich dataset, and there was simply not enough time to explore all the features and still get a reasonably-sized Tableau Story (to replace a "Powerpoint deck") that could be presented within a 5 minute time limit.
    - Even limiting my number of Dashboards and Visualizations, I am presenting only a fraction of what my Tableau Story includes, in order to stay within my 5 minute time limit.  I encourage interested readers to look at the last Story Point ("slide") on my Tableau Story to read about the interesting trends/patterns/salient points and ponderings I had while exploring this dataset, to be informed of how to interact with the Visualizations, and especially aspects that I did not speak to during my presentation.

## Future Goals
1. Perform statistical analyses to see if any findings of "increasing values" or "differences in values" were statistically significant
2. During my project, ironically when looking for a "bird strike" graphic for my Dashboards, I discovered a company called <a href="https://preciseflight.com/">Precise Flight</a> which makes Safety and Performance equipment for the Aviation Industry, including the <a href="https://preciseflight.com/pulselite-pulsing-aircraft-lights/">Pulselite Technology & System</a>, that reduces bird strikes.  It would be interesting to collect more data around number of bird strikes and impacts for planes that have deployed Pulselite Technology, to independently verify Precise Flight's reported "significant reduction in birds strikes" by airlines using the Pulselite system.
    - Credit to Precise Flight for the <a href="https://preciseflight.com/article/aviation-bird-strikes-solutions/#:~:text=%E2%80%9CSully%E2%80%9D%20tells%20the%20story%20of,%E2%80%9CMiracle%20on%20the%20Hudson%E2%80%9D.">bird strike image</a> on my Dashboards.
