# NetApp Cloud Sync Monitor

Created by Philipp Fischer (Cloud Solutions Architect for Azure NetApp Files at NetApp)

This is a basic Azure Logic App to monitor NetApp Cloud Sync relationships and get notified via mail on either only on failures or on failures as well as successfull syncs.

## Introduction

## Prerequisites and Deployment
### Prerequisites

#### Cloud Central Refresh Token
The Azure Logic uses a refresh token provided through NetApp Cloud Central, which in turn is used to generate an access token for Accessing the API Services for Cloud Sync.
To generate a refresh token follow the below steps:

- Go to [https://services.cloud.netapp.com/refresh-token], generate a refresh token and copy or save it somewhere. This will be needed during the Logic App Deployment

#### Microsoft (Office) 365 Account
You will need an Office / Microsoft 365 Account that will be used to send the notification mails. Authentication to your account is securely handled with an Azure API connection to Office 365 that is created automatically during the Logic App deployment. However, this is currently the only option to send notification mails.
If you don't have a Office 365 account, feel free to contact me and I can evaluate implementing other mail providers as well.

### Deployment


[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ffischerphilipp%2FCloudSyncMonitor%2Fmaster%2Ftemplate.json)
