
# What factors make a Kickstarter campaign successful?

This repository provides explanations of the data analysis process for the DataRes article "What factors do successful Kickstarter campaigns tend to possess? (INSERT URL)", published [INSERT DATE]. Please check out our article, which contains visualizations and insights about Kickstarter campaigns.
Contributors: Raymond Bai, Samantha Chung, Emily Hou, Amy Tang

# Data
The original dataset contained 15 variables, with data from April 21, 2009 to January 2, 2018. The data was obtained from Kaggle, at https://www.kaggle.com/kemical/kickstarter-projects?select=ks-projects-201801.csv

The initial data set defined the status of the projects under six categories: canceled, failed, live, successful, suspended, and undefined, which we then condensed into three: “successful” (meeting the crowdfund goal within the time set by the creators), “failed” (failing to meet the goal by the deadline or irreversibly terminated by the creators), and “unknown” (either temporarily suspended, ongoing/live, or undefined at the time of data collection). Our analysis was performed across these three categories.

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
The dataset was relatively clean to begin with. When downloading the data from Kaggle, there were two CSV files; one labeled ‘2016’ and another labeled ‘2018’. We found that the dataset labeled ‘2018’ included all of the entries of the ‘2016’ dataset and more, so we simply just used the ‘2018’ dataset. There were NAs in the ‘usd.pledged’ column, but we did not use this column for our analysis, as there was another column with the amount pledged adjusted to USD that did not have any NAs. 

Our team converted `deadline` and `launched` into date format, and subtracted to find time elapsed for each project. A subset of only successful projects was used (`state` = "successful"). We also analyzed the `goal` variable for successful projects, plotting goal over time elapsed to observe the distribution of time it takes to reach the successful state. 
Other variables that our team analyzed included: comparisons of the time elapsed for successful projects, the main categories of the projects, number of backers, as well as the effects of a funding goal. All these were analyzed with respect to three categories: successful projects, cancelled + failed projects, and live + suspended + undefined projects.
Our team used R to clean data, perform analysis, and create visualizations. For exploratory data analysis (EDA), the package dplyr was used, and for visualizations, the package ggplot2 was used. 

# Analysis and Code
The analysis can be found at `[analysis/]`https://github.com/amytang-ml/blueteam/tree/main/analysis. 
Each member of our team contributed to developing visualizations for our article. 

