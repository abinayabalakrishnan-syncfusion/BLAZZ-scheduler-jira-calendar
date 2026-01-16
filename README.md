# Blazor Scheduler with JIRA Calendar

This project contains that adding the JIRA calendar with Blazor Scheduler.

## Table of content
1. [Prerequisites](#prerequisites)
2. [How to run the project](#how-to-run-the-project)
3. [Add Credentials](#add-credentials)
4. [Add Rest API Url](#add-rest-api-url)
5. [Note on JIRA Credentials](#note-on-jira-credentials)
6. [Troubleshooting](#troubleshooting)



## Prerequisites

* Visual Studio 2022 or later 
* Visual Studio Code
* .NET SDK 8.0 or later

## How to run the project

* Clone the repository to your local machine.
* Open the solution file in Visual Studio 2022.
* Restore NuGet packages by rebuilding the solution.
* Run the application.

>✅Note: To run this application, we have to add JIRA credentials and Rest API url in OnInitializedAsync method in Index.razor file.

## Add Credentials

Refer [link](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)   to generate the token from your Atlassian account. 

Once token generated, specify your attlassian mail id and token in [Index page](https://github.com/SyncfusionExamples/blazor-scheduler-jira-calendar/blob/main/Pages/Index.razor#L81).

```
var byteArray = new UTF8Encoding().GetBytes("abc@xyz.com:qwertyuiop");
```
>✅ Tip:Replace the email ID and token values with your own Atlassian credentials.

## Add Rest API Url

Add your Rest API Url string in [http request](https://github.com/SyncfusionExamples/blazor-scheduler-jira-calendar/blob/main/Pages/Index.razor#L83).

```
new HttpRequestMessage(HttpMethod.Get, "https://api.atlassian.com/ex/jira/:cloudId:/rest/agile/1.0/sprint/20387/issue")
```
## Note on JIRA Credentials

JIRA credentials and the REST API URL are required to authenticate with the JIRA server and retrieve issue and sprint data. These details are configured in the OnInitializedAsync method of the Index.razor file, where the application makes REST API calls to JIRA during component initialization.Without valid credentials, the application will not be able to connect to JIRA or display calendar data in the Blazor Scheduler.

## Troubleshooting
- **No JIRA data displayed**: Verify JIRA email, API token, REST API URL, and cloudId in Index.razor
- **401 / 403 Unauthorized error**: Check that the API token is valid and the account has access to the JIRA project.
- **REST API call fails**: Ensure the REST API URL and sprint ID are correct and reachable.
- **Scheduler not rendering**: Confirm scheduler packages are restored and licensing (if required) is configured.
- **Runtime errors**: Clean and rebuild the solution and ensure .NET SDK 8.0+ is installed.


