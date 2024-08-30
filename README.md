# RETRIEVING-JIRA-PROJECTS-AND-THEIR-ASSIGNED-OWNERS
ASSIGNMENT- RETRIEVING JIRA PROJECTS AND THEIR ASSIGNED OWNERS 
 
Table of Contents
Introduction	2
1.1 Problem Statement	2
1.2 Solution Explanation	2
1.2.1 Solution Files	2
1.2.2 Solution Components	2
1.2.3 Solution Generalization	2
1.2.4 Solution Assumptions	2
1.2.5 Solution Limitation	3
Solution Guide	4
2.1	Jira Account	4
2.1.1	Generate an API Token (if you don’t already have one):	4
2.2	Postman configurations and running script	7
Solution Delivery	11
3.1	Google Drive	11
3.2	Solution Files	11

 


 
Introduction
1.1 Problem Statement
Scalable Capital is using a Jira Cloud instance, accessed at the url https://scalablegermany.atlassian.net. You are the Jira admin in Scalable Capital, and you have been asked to produce a csv file with 2 columns: all Jira project names listed in the first column, and a list of each project’s owner in the second column. You know that the Jira Cloud installation contains 120 projects. You can already open each project one at a time and view the project details (including project name and project owner) so you know the information is available. But even after searching for some time and asking Jira support, it turns out there is no report in the Jira Cloud user interface that can give you the combined information of Project+Owner for all 120 projects together. How else can you extract this information and generate the needed csv output file?
1.2 Solution Explanation
Solution is provided in java script which can be run using Postman tool. The script is fetching all projects in Jira account using Jira API calls. All projects can be fetched by a direct request in Postman and response will include project name. A subsequent request can be sent for each project to get lead of each project using Scripts tab in Postman to process the response. In the end all Project+Owner information is printed in console as comma separate which can be copied and saved in a CSV file.
1.2.1 Solution Files
Following files are part of solution:
1.	Solution.js (JavaScript file)
2.	Output.csv (Output file)
1.2.2 Solution Components
Following files are solution components:
1.	Jira Account at https://www.atlassian.com/ 
This will be used to create projects as input to fetch details of project later using script in Postman.
It will be used to create API token as well which will be used for authentication while calling Rest API from Jira.
2.	Postman
Postman tool is used to call Rest API from Jira to fetch all projects from Jira Account. URL of Jira Account and API Token are used in Postman for Rest API call.
1.2.3 Solution Generalization
This solution can be used to fetch project details for any Jira account however API Token of that account will be required for authentication in Postman. Script is using MyURL and MyToken variable for usage for any other Jira account to achieve generalization.
1.2.4 Solution Assumptions
This solution is based on assumptions that user has already created Jira Account and projects in that account.
1.2.5 Solution Limitation
This solution requires copying output from Postman console to save in file manually as Postman has limitation to enable and run Node.js required for writing output to a file in its free version. Running script in Postman will provide output to console same as opening a text file and it can be used by copy/paste to any other file.

 
Solution Guide
Following are steps to execute script to get all projects from Jira accounts with respective owners.
2.1	Jira Account
Create Jira account by login to https://www.atlassian.com/ This solution assumes that user has already created a Jira account and some projects in that account. However following steps are required to create an API Token used in solution from that account.
2.1.1	Generate an API Token (if you don’t already have one): 
1.	Log in to your Jira account.
2.	Go to your account settings 
 
 
3.	Go to Security tab and click on Create and manage API tokens
 
 
4.	Click on Create API token
 
5.	Provide a Label e.g. Assignment and click on Create
 
6.	Copy token to save it in a file as you will not be able to view it later. Click on Close to close it.
 

2.2	Postman configurations and running script
1.	Download Postman and run it. Postman v11.10.1 was used for developing and testing solution.js script which is the latest version [29 August 2024].
2.	Click on New
 
3.	Select HTTP
 
 

4.	Select GET from drop-down option
 
5.	Provide Rest API endpoint as follows:
https://<your-jira-account>.atlassian.net/rest/api/3/project/
For example: https://aasrz.atlassian.net/rest/api/3/project/ 
 

6.	Go to Authorization tab and select Basic Auth from drop-down menu
 
7.	Provide Username and API token in Password
 
 

8.	Go to Headers tab and add Key=Content-Type and Value=application/json
 

9.	Click on Send button and verify that you are getting HTTP 200 OK status code and response below
 
10.	Go to Scripts tab and copy contents of Solution.js in this window and click on Send button
 
 

11.	Click on Console button on bottom left of window to view output of script
 

12.	Copy results of all processed projects from console window
 
13.	Paste the results into the text file and save it as csv file.
 
Solution Delivery
3.1	Google Drive
This solution is shared on Google Drive folder as below:
https://drive.google.com/drive/folders/1fVj_6GCwqVSbt75dGDgt6sxkxW27XOgm?usp=sharing

Google drive folder is shared with cloud-application-administrator@scalable.capital 
 

3.2	Solution Files
Following are files in Google Drive folder:
1	ReadMe.pdf
2	Solution.js
3	Output.csv
