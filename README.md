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
Once the data was sorted and tables were created, I created several visuals to see the results of the work.      

### Categories  
![image](https://github.com/user-attachments/assets/89ff0cb0-428f-4b05-b95a-377876b0d083)    
The above bar graph shows the Aggregate Popularity of each Category. From this, we can easily deduce that travel, science, healthy eating, animals, and cooking are the top five popular categories being nearly or exceeding 50,000 scores. We can also see that the drops in the following categories are not drastic. They progressively go down.      

![image](https://github.com/user-attachments/assets/d675a71c-0cb8-4ab3-b3a6-1f935ae88255)    
With the top categories known, a pie chart was made to see the percentage of popularity they hold amongst themselves. Besides cooking at 18.9%, they all are rather similar in percentage showing how close they are together.    

![image](https://github.com/user-attachments/assets/f669fe56-f0a0-4145-8b0b-8128a735a800)    
From the top five categories, we can see the users' sentiments toward each. Positive reactions are rather similar with only healthy eating at 57.7% being ahead by about 0.7%. Regardless all categories hold above a 55% positivity to them. Then science at 29.5% and healthy eating at 29.8% are much lower in the percentage of negative reactions. This is nearly 3% lower than the other categories.    

### Content Type
![image](https://github.com/user-attachments/assets/f926d8ae-84d9-4fde-a356-38e47c540194)
![image](https://github.com/user-attachments/assets/8109b982-cb78-4a09-a2ce-8ec9b1e6c783)    
So here I wanted to go above two different graphs at the same time. So first we can see that photo is the most popular content type followed by video, gif, and audio. The same then can be said in the following graph in the amount of posts made by the content type. This directly shows a positive correlation between the number of posts and popularity score since they follow a similar pattern in both graphs.    

![image](https://github.com/user-attachments/assets/3ac0435f-ee9c-4343-8a04-6f6dc960c019)    
Despite photos being uncontested in popularity, it does not hold the highest positive reactions by users at 56.4%. It is second to audio which has 57.4% positive reactions. The content type with both the lowest amount of posts and popularity has done slightly better gaining positive reactions. Negative reactions between the 4 are quite similar with the difference at most being 0.4% with photos at 30.8% and gifs at 31.2%.

### Popular Category and Content-Type
![image](https://github.com/user-attachments/assets/49298532-d9d9-4b03-8e87-4f23d3a2c13c)    
There is a lot to gather from this bar graph which is separated by content type and categories. Despite the travel category being the top, it does not hold the highest position in any of the content types. It barely loses 1st in both video and gifs while being abysmally low in audio. The popularity of travel audio is barely 1/3 in comparison to every other content type. It would also appear that both science and healthy eating stay within a constant range with either not having 1 content type performing horribly.     

### Dates
![image](https://github.com/user-attachments/assets/9ca9f5cf-4721-4c9c-bb70-350a314f51fb) 
![image](https://github.com/user-attachments/assets/9110b64a-656f-4eb2-9c65-e15dfa5502cb)       
Once again I will go over two graphs at the same time. In the first graph, we can see that the month with the most popularity was May at 64,545. However, the same can not be said with the second line graph. In that, the months of August, October, and January tied with the highest amount of posts at 622 with May not being even 3rd at 607. Looking back at the first line graph over shows that the months with the highest posts also placed 2nd-4th in popularity. The line graphs may not follow quite the same trend but popularity and posts appear to be slightly positively correlated between each other based on the month. 

## Final Analysis Presentation
[Social Buzz Analysis.pptx](https://github.com/user-attachments/files/17595373/Social.Buzz.Analysis.pptx)     
[Social Buzz Analysis Presentation](https://drive.google.com/file/d/1vdI7_h1xYpCvwHF_Lnqq25jjmuzeTXPT/view?usp=sharing)
