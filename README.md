# NetApp Cloud Sync Monitor

Created by Philipp Fischer (Cloud Solutions Architect for Azure NetApp Files at NetApp)

This is a basic Azure Logic App to monitor NetApp Cloud Sync relationships and get notified via mail on either only on failures or on failures as well as successfull syncs.

## Introduction
This Cloud Sync monitor offers the following funcionality:
- 

#### The template deploys two components:
- The Azure Logic App containing the monitoring logic
- An Office / Microsoft 365 API connection, which is used to connect to your mail account to send the notification mails

## Prerequisites
### Cloud Central Refresh Token
The Azure Logic uses a refresh token provided through NetApp Cloud Central, which in turn is used to generate an access token for Accessing the API Services for Cloud Sync.
To generate a refresh token follow the below steps:

- Go to https://services.cloud.netapp.com/refresh-token, generate a refresh token and copy or save it somewhere. This will be needed during the Logic App Deployment
- This token can be reused multiple times when re-deploying the Logic App or also when creating multiple Logic App instances.
- If necessary you can also revoke the token and create a new one via the aforementioned link.

### Microsoft (Office) 365 Account
You will need an Office / Microsoft 365 Account that will be used to send the notification mails. Authentication to your account is securely handled with an Azure API connection to Office 365 that is created automatically during Logic App deployment. However, this is currently the only option to send notification mails.
If you don't have an Office 365 account, feel free to contact me and I can evaluate implementing other mail providers as well.


## Deployment & Configuration
### Deployment

All you need to do is clicking the Deploy to Azure button below, which then takes you right to the Azure Portal where you can specify the necessary parameters

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ffischerphilipp%2FCloudSyncMonitor%2Fmaster%2Ftemplate.json)

### Configuration
After launching the template you are presented with an Azure custom deployment screen that asks for some configuration details.

![Deployment Configuration](Screenshots/DeploymentParameters.png)



Hinweis auf: Wenn es aktuell keine Failed relationships gibt, dann zum Testen auf false stellen und anschließend ändern