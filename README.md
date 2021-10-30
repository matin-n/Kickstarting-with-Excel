# Kickstarting with Excel

## Overview of Project

### Purpose
This project's purpose is to analyze different Kickstarter campaigns and how they performed in relation to their launch dates and funding goals.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

I created a pivot table based on the `Parent Category` and `Years` columns.  Within the pivot table, I filtered the `Parent Category` by `Theater` to analyze the theater category. From the pivot table, I created a dotted line chart to visualize the relationship between outcomes and launch month.

To create the `Years` column, I used the `YEAR()` function to extract the year from the `Date Created Conversion` column and placed the data in a new column `Years`. Then, within the pivot table, I filtered the `Parent Category` by `Theater`  to analyze the theater category.

The line chart shows the number of successful, failed, or canceled projects by month. With the line chart visualization, we can see how each month impacted the fundraising campaign outcome:

![Analysis of Outcomes Based on Launch Date](https://raw.githubusercontent.com/matin-n/kickstarter-analysis/main/resources/Theater_Outcomes_vs_Launch.png)

We can deduce that the month of May is the month with the most successful Kickstarter campaign. However, May, June, July, August, and October all had roughly the same number of failed campaigns launched.

### Analysis of Outcomes Based on Goals

I created another line chart to visualize the percentage of successful, failed, and canceled plays based on the funding goal amounts.

First, I created a sheet labeled "Outcomes Based on Goals" with the following columns:

* Goal
* Number Successful
* Number Failed
* Total Projects
* Percentage Successful
* Percentage Failed
* Percentage Cancelled

Then, I grouped the projects by the following dollar-amount ranges within the "Goals" column:

* Less Than 1,000
* 1,000 to 4,999
* 5,000 to 9,999
* 10,000 to 14,999
* 15,000 to 19,999
* 20,000 to 24,999
* 30,000 to 34,999
* 35,000 to 39,999
* 40,000 to 44,999
* 45,000 to 49,999
* Greater than 50,000

I then populated the number of successful, failed, and canceled projects by utilizing the `COUNTIFS()` function to collect the outcome and goal data of the "plays" subcategory. For example, I used the following function to collect the number of successful plays that had a goal of less than 1000: `=COUNTIFS(Kickstarter!D:D, "<1000", Kickstarter!F:F, "=successful", Kickstarter!R:R, "=plays")`

Next, I calculated the Total Projects by using the `SUM()` function on the range of successful, failed, and canceled projects of each row. I was then able to utilize the sum of projects to determine the percentage of successful, failed, and canceled projects.

Finally, I created a line chart to visualize the relationship between the goal-amount ranges on the x-axis and the percentage of successful, failed, and canceled projects on the y-axis.

![Analysis of Outcomes Based on Goals](https://raw.githubusercontent.com/matin-n/kickstarter-analysis/main/resources/Outcomes_vs_Goals.png)

We can conclude that there is a relationship between the goal amount and the campaign's success or failure rate. We can deduce that the rate of projects being successful will decrease as the funding goal amount increases. However, there were a few that we were able to successfully launch with a higher budget in the range of $35,000 to $34,999 and $40,0000 to $44,999. The reasoning for this discrepancy is unclear as we are limited by the dataset. We could speculate that the projects with the higher goals could have had a higher demand and a better marketing campaign to gather more interest, but we cannot see this with our current dataset.

### Challenges and Difficulties Encountered
It has difficult to find a reason why the budget range of $35,000 to $45,999 had an increase in successful projects. The data is limited by the number of projects, and we can only speculate with outside factors that are not included in the dataset on why this range had an increase of successful campaigns.



## Results

- We can deduce that the month of May is the month with the most successful Kickstarter campaign. However, May, June, July, August, and October all had roughly the same number of failed campaigns launched.

- We can conclude that there is a relationship between the goal amount and the campaign's success or failure rate. We can deduce that the rate of projects being successful will decrease as the funding goal amount increases. However, there were a few that we were able to successfully launch with a higher budget in the range of $35,000 to $34,999 and $40,0000 to $44,999. The reasoning for this discrepancy is unclear as we are limited by the dataset. We could speculate that the projects with the higher goals could have had a higher demand and a better marketing campaign to gather more interest, but we cannot see this with our current dataset.

- A limitation of this dataset is that we do not have marketing metrics. Therefore, a project may have had a larger marketing budget to increase the amount of sign-up backers for the Kickstarter. Another limitation is that the data does not include detailed information on the donation statistics. We only have access to the average donation. We do not have access to the data of the individual person that donated. It would be interesting to conduct on factors such as how much each person contributed, gender, or age.

- A possible graph that we could create could be a line chart on the outcome of the project based on average donation.
