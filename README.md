# What factors make a Kickstarter campaign successful?

This repository provides explanations of the data analysis process for the DataRes article "[INSERT YOUR TEAM'S ARTICLE TITLE HERE](INSERT URL)", published [INSERT DATE]. Please check out our article, which contains visualizations and insights about Kickstarter campagins.
Contributors: Raymond Bai, Samantha Chung, Emily Hou, Andy Shen, Amy Tang

# Data
The data used to develop our Medium article came from Kaggle: https://www.kaggle.com/kemical/kickstarter-projects?select=ks-projects-201801.csv
Give some background about the data here. When was the data set created? What year(s) was the data from the data set from? How many variables were in it?

There were 15 variables. 

The data set contained the following columns:
* `id` - Internal Kickstarter project ID
* `name` - Name of the project
* `category` - Category (specific)
* `main_category` - Category (main)
* `currency` - Currency of funds for project
* `deadline` - Deadline to fund goal amount
* `goal` - Goal amount to fund
* `launched` - Date project was launched
* `pledged` - Amount pledged in country's currency
* `state` - State of the project, includes "successful" , "failed" , "live" , "cancelled" , "undefined" , "suspended"
* `backers` - Number of people who contributed to the campaign
* `country` - Country project was launched in
* `usd.pledged` - Amount pledged in US dollars, conversion done by kickstarter
* `usd_pledged_real` - Amount pledged in US dollars, conversion done by Fixer.io API
* `usd_goal_real` - Goal amount in US dollars, conversion done by Fixer.io API


# Data Processing
In this section, focus on discussing the technical data cleaning/analysis that you did. How did you clean the data? Were there any columns with NAs or missing values and how did you treat them? What variables did your team omit, if any, and why? What variables did your team analyze in your article? What other issues with the data did your team encounter and how did you address it?

Time: To look at time elapsed, our team converted `deadline` and `launched` into date format, and subtracted to find time elapsed for each project. A subset of only successful projects was used (`state` = "successful"). We also analyzed the `goal` variable for successful projects, plotting goal over time elapsed to observe the distribution of time it takes to reach the successful state. 


# Analysis and Code
The analysis can be found at `[analysis/]`https://github.com/amytang-ml/blueteam/tree/main/analysis. 
Each member of our team contributed to developing visualizations for our article. Discuss the languages you used (R/Python) and what libraries you utilized for analysis and visualizations. Also talk about the types of research questions your team came up with and how you went about analyzing them.

We set out to answer questions about what makes a successful project:

# Time elapsed between launch date and date the goal was reached
What is the summary and distribution of time elapsed for all campaigns and successful campaigns? Is there a point where people should just give up on meeting their goal because it's been too long? How many days does it take for most projects to be completed? Median time elapsed of top categories? [Amy]

For successful campaigns, the 5 number summary is: 1 30 30 34 92
The minimum time elapsed is 1 day and the maximum is 92 days. 50% of the projects reached their goal funding 30-34 days after launching the project. The median time elapsed is 30 days. The mode time is also 30 days. The distribution of time elapsed for successful campaigns follows a roughly bell-shaped curve. The median elapsed time for the top main category, "Film & Video" , is 30 days. The median elapsed time for the top (more specific) category, "Product Design" , is 30 days.

# Categories 
Count (looking at the top three project categories, are projects in those categories more likely to succeed because of popularity or less likely because they are drowned out by others?) [Raymond]

# Funding goal
How big can projects get? How high is too high? Is there an ideal goal amount that has highest rates of success?) [Emily]

# Number of backers
For projects that succeed, look at number of backers [samantha]
For each project with successes, how many backers are there? Is it crowd funded, or is the success relied on one or two contributors?
Is there an “ideal” number of backers for the project to be successful?
Compare number of backers of successful campaigns to number of backers for all campaigns.

