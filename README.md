# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this project is to compare different fundraising projects based on their launch dates and fundraising goals. Two data visualizations we can create to better understand this relationship is by creating a chart showing fundraising outcomes, whether the fundraiser was a success or failure, based on launch date, and another chart that compares outcomes based on the fundraising goal.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

To create my Outcomes Based on Launch Date chart, I started by adding a years function to my Kickstarter sheet.

=YEAR(cell)

This equation allowed me to determine the year that the campaign was created. My next step was to create a pivot table in the next sheet, that showed successful, failed, and canceled fundraisers by month. 

Parent CategorytheaterYears(All)Count of outcomesColumn LabelsRow LabelssuccessfulfailedcanceledGrand TotalJan5633796Feb71393113Mar5633392Apr71402113May111523166Jun100494153Jul87501138Aug72474123Sep5934497Oct6550115Nov5431388Dec3735375Grand Total839493371369


The pivot table was filtered to only display theater fundraisers. I then created a line chart using the data from the pivot table, which allowed me to see the relationship between the month of the year a campaign was launched and the outcome of the campaign.

### Analysis of Outcomes Based on Goals

For the chart inspecting the relationship between outcomes and goals, I started by adding the columns 

Goal
Number Successful
Number Failed
Number Canceled
Total Projects
Percentage Successful
Percentage Failed
Percentage Canceled

After adding these columns, I created dollar amount ranges for each of the goals. I then used the COUNTIFS function to populate the sheet with filter the Kickstarter by "Number Successful," "Number Failed," and "Number Canceled,Ó and filtered the sheet by monetary ranges and the subcategory plays. I had to nest COUNTIFS functions to filter for the various monetary ranges. For example, the equation for the number of successful campaigns that had a goal from $45000 to $49999 was:

=COUNTIFS(Kickstarter!$D:$D, ">=45000",Kickstarter!$F:$F, "successful", Kickstarter!$D:$D, "<=49999",Kickstarter!$R:$R, "plays")

This code instructs Excel to count the value of successful campaigns that had a value greater than or equal to $45,0000 and smaller than or equal to $49,999. Next, it instructed Excel to filter the sheet by the subcategory plays. 

Finally, I used the SUM function to calculate the total projects for each monetary range, and then divided the number successful, number failed, and number canceled by the total to find the percent successful, percent failed, and the percent canceled. I then used this information to create a line chart, comparing this information.

### Challenges and Difficulties Encountered

The only challenge I faced during this process was while using the COUNTIFS function, I did not realize that you had to filter the equation for plays and not just have the filter on in the Kickstarter sheet. I could not figure out why the number of canceled plays was not zero. I eventually realized that the filter on the sheet does not apply to the output of the COUNTIF function.


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

The first conclusion I can draw from the Theater Outcome by Launch Date chart is that most successful campaigns started out around May. Fewer successful campaigns launched every month later than May, and the number only picked up slightly around October then further decreased in September. From this, I can conclude that launching a fundraiser in May is ideal. A second conclusion I can make from this graph is that the number of campaigns that failed to meet their fundraising goals remained much more constant throughout the year than the number that succeeded. This means that broadly a smaller number of campaigns failed, and the month of the year that the campaign was launched did not cause a large variation in the number of campaigns that failed.

- What can you conclude about the Outcomes based on Goals?

From the outcomes based on goals chart, I can conclude that very small fundraising goals have a relatively high chance of meeting their goals, from less than $1000 to $1000- $4999. Beyond that, the chances of meeting fundraising goals decreased until it hits around $35,000. When the goal is over $44,999, the chance of meeting that goal decreases rapidly. 

- What are some limitations of this dataset?

One limitation of this data set is that it does not include a mean donation, just an average. This could impact the data available because fundraising techniques that are most effective might not be able to be properly inferred. There could be many situations where someone could be hosting a fundraiser and most people donate a relatively small amount, but one person donates most of the money. This might not be as useful as having information on a large number of smaller contributions, which could not be understood through an average of the donation amount. 

- What are some other possible tables and/or graphs that we could create?

Another graph you could create with this data set is a graph showing the number of backers over the duration of a fundraiser to see if there is any crucial time period that the fundraiser is gaining more momentum with a larger number of donors. 

