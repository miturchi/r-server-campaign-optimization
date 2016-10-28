# Campaign Optimization - Predicting How and When to Contact Leads
<img src="Resources/Images/management.png" align="right">

## Implemented on SQL Server 2016 R Services

## Introduction

When a business launches a marketing campaign to interest customers in some new or existing product(s), they will typically use  a set of  business rules to select leads for their campaign.  Machine learning can be used to help increase the response rate from these leads.   This solution packet shows how to use a prediction model to increase the response rate to a campaign by recommending  **how to contact** (for example, e-mail, SMS, or cold call) as well as **when to contact** (day of week and time of day) each lead identified for use in a new campaign.

This template uses simulated data from the insurance industry to model the campaign response for an acquisition campaign. The model uses predictors like demographic details of the lead, historical campaign performance and product details. The model predicts the probability of a lead making a purchase from each channel, at various times of the day and days of the week, for every lead in the database. The final recommendation for targeting each user is decided based on the combination of **channel**, **day of week** and **time of day** with the highest probability of making a purchase. 

For customers who prefer an on-premise solution, the implementation with SQL Server R Services is a great option, which takes advantage of the power of SQL Server and the innnovation of the R language. 

We have modeled the steps in the template after a real-life data science process, where the data preparation, model training and evaluation can be done by a data scientist, from the convenience of their R IDE, and the deployment is done using SQL stored procedures with embedded R code. We also use PowerBI to visualize the deployed results. View the details and follow the solution from start to finish with [this typical workflow](Resources/Instructions/Typical_Workflow.md) involving multiple personas.

For convenience we also illustrate how all of these steps can be executed on a SQL Server client environment (such as SQL Server Management Studio), as well as from other applications. We provide a Windows PowerShell script that invokes the SQL scripts and demonstrate the end-to-end modeling process.

## For the Business Manager

A high level description of this solution is [described here](Resources/business-manager.md).

## For the Data Scientist 

This template showcases the use of Random Forest and Gradient Boosting to model for Campaign Responses. Data Scientists can follow the steps of data creation, model development, scoring and deployment.  The final deployed recommendations will then be visualized in PowerBI. [See more details and explanations of all the files involved in this solution.](Resources/data-scientist.md).

## Typical Workflow
[This guide](Resources/Instructions/Typical_Workflow.md) describes the roles of multiple personas involved in creating, deploying, and consuming this solution.

## Quick Start
If you’re just interested in creating this solution on your computer, use this fully automated solution that uploads the data to your SQL Server, preprocesses data, performs feature engineering, trains and scores the models by executing a PowerShell script. This is the fastest way to deploy the entire solution. See [PowerShell Instructions](Resources/Instructions/Powershell_Instructions.md) for this deployment.

##Template Contents 

[View the contents of this solution template](Resources/contents.md)


**NOTE:** Please don't use "Download ZIP" to get this repository, as it will change the line endings in the data files. Use "git clone" to get a local copy of this repository. 
 
This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.