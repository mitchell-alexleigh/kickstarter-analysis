# Analysis of Kickstarter Play Campaigns
## Overview

The purpose of this project is to analyze data on previous Kickstarter campaigns in order to provide recommendation for a future campaign. The analysis focuses on the outcome of campaigns for plays. Included are reports on outcome and its relationship to launch date and outcome and its relationship to the fundraising goals. Also included is the full dataset. 

Below I describe my process and provide my findings. 

## Analysis and Challenges

### Analysis 

To analyze the outcome data and its relationship to the launch date I created the following pivot table in the Theater Outcomes by Launch Date.

![Pivot_Table](/Resourses/Pivot_Table.png)

The table is filtered by the Parent Category “theater.” Because the focus of this project was plays, a subcategory of theater, the filter was a applied to show the data relevant to the clients request. The data in this pivot table is visualized in the Theater Outcome Based on Launch Date graph included in the Results potion of this document. 

To analyze the outcome data and its relationship to fundraising goal I created the following table in the Outcome Based on Goals sheet. 

![goal_outcome_data](/Resourses/goal_outcome_data.png)

To create the “Number Success”, “Number Failed”, “Number Canceled” columns I used a variation of the following formula. 

![countifs_formula](/Resourses/countifs_formula.png)

The COUNTIF()  function counts all data that meets the following criteria 
*>= the lowest goal amount of the given range in the goal column 
*<= the highest goal amount of the given range in the goal column
*has the subcategory column of “plays” from the Kickstarter Data dataset
*has the appropriate value of “Successful”, “Failed”, or “Canceled” from the Outcomes column of the Kickstarter dataset

Additionally, I utilized absolute cell references so that the formula could easily be applied to other cells with minimal adjustments. 

To create the Total projects column, I used the following formula.

![sum_formula](/Resourses/sum_formula.png)

To create the percentage columns, I used the following formula

![percentage_formula](/Resourses/percentage_formula.png)

Because the formula includes division, I wrapped the formula in the IFERROR function. If the denominator were ever 0, a “0%” would display in the cell instead of a error message. 

The data in this table is visualized in Outcome based on Goals graph included in the Results potion of this document.

### Challenges

When populating the Outcome Based on Goals sheet, I found the process of entering formulas into the “Number Success”, “Number Failed”, “Number Canceled” cells very time consuming. To combat this, I utilized absolute cell references so that the formal could be easy copied down rows and across columns. 

Because the formula used for the “Number Success”, “Number Failed”, “Number Canceled” cells is has several permeates, I did receive errors. Resolving this error requires attention to detail to ensure each comma, apostrophe, and quotation mark was appropriately placed. 
 
## Results

### Theater Outcomes Based on Launch Dates
![Theater_outcomes_vs_Launch](/Resourses/Theater_outcomes_vs_Launch.png)

### Theater Outcomes Based on Launch Dates: Conclusion 1
#### Theater Kickstarter Campaigns launched in May, June, and July are the most successful
The graph shows these months have higher success rates than other months. The Failed rate increase slightly for these months indicating that there are more campaigned launched these months. However, the increase in success is disproportionally higher. 

### Theater Outcomes Based on Launch Dates: Conclusion 2
#### The worst month to launch a Theater Kickstarter Campaigns is December
The shows December having the least amount of successful Theater Campaign launches. Additionally, the number of failed campaigns is very close the number of successful ones.  

### Theater Outcomes Based on Launch Dates
![outcome_vs_goals](/Resourses/Outcome_vs_Goals.png)

### Outcome Based Goals: Conclusion 
#### Theater Kickstarter Campaigns with a fundraising goal between $5,000 and $9,999 are the most successful. 
According to the Outcome Based on Goals graph, campaigns with goals between $5,000 and $9,999 have the highest success rate at 100% successful. 

### Summary of Limitations and Recommendations 

#### limitations
One limitation of that data is that there is no recent data. That most recent data point comes from 2017. 

##### Recomendatiosn 
In addition to the graphs included in this report, I recommend creating a table to analyze the relationship between pledges received and number of backers. 

I would also recommend creating a table to analyze the relationship between the number of backers and success rate.  


