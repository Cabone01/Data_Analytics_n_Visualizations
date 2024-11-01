# Accenture Job Simulation
## Introduction
Social Buzz has scaled drastically faster than anticipated reaching over 500 million active users monthly. They have reached out to Accenture to help oversee their scaling process effectively. My team has been assigned a project with them to accomplish three tasks to show why Social Buzz should work with us.
- An audit of their big data practice
- Recommendations for successful IPO
- An analysis of their content categories that highlights the top 5 categories with the largest aggregate popularity.    
As the data analyst, two (imaginary) others and I are tasked with the last objective.
**Tools**
- Microsoft Excel
- Python
- Pandas
- Powerpoint
## Data Modeling
Outta 7 tables, I decided using Content, Reaction, and ReactionTypes would be best. These tables would allow us to find the top 5 categories with the largest popularity. To do that, these steps were taken.      
### Cleaning
From the Content table, we kept only the Content ID, Type, and Category. Content ID, the primary key, will be used to merge with the reaction table. Type tells us if the content was a gif, video, audio, or photo. The Category tells us what the content is like cooking, traveling, science, etc. Since we are looking for the best categories of content we would find that under the content table.     
From the Reaction Table, we kept only Content ID, Type, and Datetime. Content ID is the foreign key that would allow us to merge the table with Content. Type gives what type of reaction it was like if they loved it, detested it, enjoyed it, etc. DateTime gives when the reaction was made.     
From the ReactionTypes Table, everything was kept being Type, Sentiment, and Score. The Type is the same as before but is also what we need to merge this table with the Reaction. Sentiment tells us if the reaction is positive, negative, or neutral. The Score is related to the reaction type which goes from 0-100 on a scale of really hated to super loved. This will allow us to determine the popularity of a scale.    
Once these were all collected, the data was cleaned. First, the null rows were removed. This was then followed by string values being adjusted to match since both "science" and science showed up. Had to have both matches as the same value. The columns that were not kept were dropped. Finally, if any data types were different they were changed.
### Merge and Data Creation
This step was quick. Since the Content and ReactionTypes had no similar keys to merge, I used Reaction which connected to both to merge them. Content and Reaction merge with Content ID. Once they were merged, that table had Type which would merge with ReactionTypes' Type variable and merge them. Once they merged new columns were made. The DateTime was separated into Year, Month, Day, Hour, Minute, and Second to allow us to see more connections.
## Data Analysis
## Presentation
[Social Buzz Analysis.pptx](https://github.com/user-attachments/files/17595373/Social.Buzz.Analysis.pptx)     
[Social Buzz Analysis Presentation](https://drive.google.com/file/d/1vdI7_h1xYpCvwHF_Lnqq25jjmuzeTXPT/view?usp=sharing)
