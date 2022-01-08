# An Analysis of Kickstarter Campaigns
## Overview of Project
####  Louise wants to know how different campaigns fared in relation to their launch dates and their funding goals. Using the Kickstarter dataset provided, we will visualize campaign   outcomes based on their launch dates and their funding goals.
---
## **Analysis: Outcomes Based on Launch Date**
---
#### Analysis Overview:
---
#### Using the Kickstarter dataset provided, we will visualize Theater campaign outcomes based on their launch dates.
---
#### To start, we created the Years column in the Kickstarted sheet in order to extract the Year from the Date Created data. To do that we used the formula "=YEAR(S2)" where Column S stores Date Created data. 
---
#### We then created a pivot table in a new worksheet labeled "Theater Outcomes by Launch Date". The table rows were "Date Created" and Columns were "Outcomes". We also applied Parent Category and Years filters. We changed the Date Grouping to Months. 
---
#### Next we filtered by "Theatre" and charted the outcomes by month of year by inserting a line chart. Please see the outcome below:
---
![Theater Outcomes by Launch Date](/Resources/Theater_Outcomes_vs_Launch.png)

#### Challenges:
 
For this analysis one of the challenges was to filter by Month of Year rather than full Creation Date. To do that, in the pivot table, in the date row, we click on of the cells. Then we right click and select "Group" then select "Months" and click okay. Excel will then group these dates by Month of Year. 

## **Analysis: Outcomes Based on Goals**
---
#### Analysis Overview:
---
#### Using the Kickstarter dataset provided, we will visualize Theater campaign outcomes based on their Goals.
---
#### To start, we created a new sheet labeled "Outcomes based on Goals". We created a table with 12 Rows and 8 Columns. The Rows host 12Dollar Amount Goal ranges, starting from $1,000 to $50,0000 and above. In the columns we had the following headers: "Number Successful, Number Failed,	Number Canceled,	Total Projects,	Percentage Successful,	Percentage Failed,	Percentage Canceled)
---
To populate the values for each column, we filtered the data by 3 criteria:
1) Sub Category: "Plays"
2) Goal: According to the Goal groupings in our rows
3) Outcome: "Succesful" "Failed" or "Canceled"

To accomplish that we used the countifs function in Excel. For example, to count the number of **Succesful** projects that are **Plays** and have a goal under **$1,000** we used the following formula **"=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,"<1000")"**

---
Kickstarter!$F:$F is the column that hosts the outcome data
Kickstarter!$R:$R hosts the subcategory
Kickstarter!$D:$D hosts goal dollar amount

---

Following that, for each goal range, we found out the total number of projects by summing up all outcomes for each range. We used the following Excel formula: **"=SUM(B2:D2)"** 

---
We then calculated the percentages for each outcome category by dividing the number of projects in each category by the total. For succesful projects we used the following Excel formula: **"=B2/$E2"** and changed the cell number formatting to percentage.

---
#### Finally we created a line chart to visualize the relationship between the goal-amount ranges on the x-axis and the percentage of successful, failed, or canceled projects on the y-axis. Please see chart below:
---
![Theater Outcomes by Launch Date](/Resources/Outcomes_vs_Goals.png)
---
#### Challenges:
---
#### For this analysis one of the challenges was to ensure that while our filters categorized our data, we still managed to capture all of the projects. After populating all the values, we summed up all projects across outcomes and goal ranges. We compared that to the number of "Plays" in our Kickstarter sheet. We found that there is a discrepancy. After investigating it turns out that out dollar range filter were taking into account all projects with goals below $50,000 and those above $50,000. However our filters did not capture projects that have a funding goal of exactly $50,000. As a result we modified our final Goal category to "Greater than or Equal to 50000" instead of "Greater than 50000". We also had to use the following Excel formula: **"=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,">=50000")"** 
---
#### We highlight the use of ***">="*** operator instead of ***">"***
---
## **Results: Outcomes Based on Launch Date**
---
#### From looking at out line chart, we notice a significant increase in succesful projects in May, June, July and August. We can conclude that there is a higher chance for Play projects to succesfully fund their campaigns in those summer months. Another interesting observation is that the last three months of the year saw a downward tren in successful projects.
---
## **Results: Outcomes Based on Goals**
---
#### When looking at our Goal Based line chart we notice that projects with a funding goal below $5,000 had a high chance of success (~74%). More significantly however is that very few projects with funding goals over $45,000 were succesful (13%). 
---
## **Limitations**
---
#### Our data is limited to projects that are funded on kickstart only and does not included projects funded on other crowdfunding platforms. Further more we only have 3 years of data which does not give us a big enough sample set to concluded persistent patterns.

## **Recommendations**
#### It would be interesting to further understand the relationship between launch date and funding goal. One recommendation would be to further filter our Launch Date pivot table by funding goals. That way we can chart the monthly success/failure of projects based on their funding goals. We can understand if different funding goals have different favored months.
