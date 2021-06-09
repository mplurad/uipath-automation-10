# uipath-automation-10

## Project Description

Send outlook calendar invites to P2 and P3 presentations based on user input emails. Emails are obtained either through MS Office 365 or defaults to whatever data is already in the queue (e.g. Emails.csv file is manually uploaded through UiPath Cloud into queue).

## Technolgies Used
* UiPath Studio
* Uipath Orchestrator
* MS Office 365
* Azure Portal
* Microsoft Graph API

## Features
* Ability to send emails by going into Office 365 and finding Emails.xlsx file
* Ability to default to sending emails based on whatever is already in the queue

## Getting Started
To get this automation running on your machine, you will need to setup UiPath Orchestrator with the following assets
* GoogleCredential
* ZohoCredential
* EmailWorkbookPath
* GSuiteOAuthCredential

###### Email Workbook Path

* After downloading this automation, Create a xlsx file called 'AssociateEmails.xlsx' and add all the new batch associates email addresses to it under the first column which needs to be named 'Email'.
* The sheet name should just be 'Sheet1' 
* Add 'AssociateEmails.xlsx' to the Input subfolder in the Data folder of the project to configure the workbook path.

###### GsuiteOAuthCredential Setup

* Navigate to Console.Cloud.Google.com
* Click the dropdown box at the top of the webpage marked 'Select a project' and then click the 'Create a new project' button in the top right of the newly opened window.
* Name the project something relevant like UiPath Gsuite, but the name isnt really important.
* Navigate to the APIs & Services Dashboard by clicking on the sidebar option on the left and click the '+ Enable APIs and Services' button at the top of the page. Then search for and enable any APIs you would want your bot to use. In this case, all you will need to enable is the Gmail API.
* Now click on the APIs & Services sidebar button but navigate to the 'Credentials page instead. From here click the '+ Create Credentials' dropdown at the top of the page, select 'OAuth client ID and then click the 'Configure Consent Screen' button.
* Select the 'External' radio button and hit create. Then enter a name to the application being used. You can again just put Uipath Gsuite, then hit save to configure your consent screen. (You may be asked for a contact email too)
* Once again navigate to the APIs & Services Credentials page, click the '+ Create Credentials' dropdown and select 'OAuth client ID.
* Select 'Desktop app' for the application type and give it a name like before and click create.
* Your 'GSuiteOAuthCredentials' will now be displayed on the screen.

###### Uipath extension for Edge

* Make sure you have the UiPath web automation extension enabled on your Microsoft Edge browser. 
* To do this, go to https://docs.uipath.com/studio/v2019-fastTrack/docs/installing-the-edge-extension for a step-by-step guide. (You will need to have studio installed already)
* This will allow the automation to interact with the Edge browser

# First Time Run Notes

###### Consent Screen For Gmail

* The consent screen that was configured in the previous steps will allow you to send emails with Gmail. 
* But the first time you try to do this, you will encounter that consent screen and will need to manually give the bot consent to send emails. 
* You will probably also have to get past the 'This app isn't verified' screen. Just click the Advanced button and then click 'Go to <App name>(unsafe)'. (This is your own application so there is actually no safety concern)
* You wont have to worry about any of this if you are only using Zoho to send the emails.

## Usage

Once You have installed everything, have credentials & workbook path setup and dealt with the consent screen for the first time, you should be able to run the introductory email automation.
