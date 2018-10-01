# What is Civic Graph?
Civic Graph shows who’s who and what’s what in the growing field of civic technology. It is an open source, crowd-sourced knowledge base and data visualization project. It aims to map the civic tech community players and connections -- their types, locations and levels of influence in an interactive, intuitive, and modern way.

## Technical Breakdown

Civic Graph is built in three parts:

1. [Civic-Graph-UI: Angular.js (v1) and D3.js](#civic-graph-ui) - <https://github.com/MicrosoftTCE/civic-graph-UI>

2. [Civic-Graph-API: Python (v3)](#civic-graph-api) - <https://github.com/MicrosoftTCE/civic-graph-API>

3. [Azure hosting](#azure-hosting)

### Civic Graph UI

The **UI** front-end is built with Angular.js (v1) and D3.js for the network graph visualization. [Civic Graph](http://civicgraph.io/) graph nodes represent entities, which could consist of people or organizations involved in the field of civic technology. The links among the entities represent the types of relationships or connections these entities share.

Filtering options provide a unique method for visualizing certain aspects of the civic technology space.

|Type of Entities | Color Representation
|----------------|-----------------
|`For-Profit`|`Green`
|`Non-Profit`|`Blue`
|`Government`|`Red`
|`Individuals`|`Orange`

|Type of Connections | Color Representation
|----------------|-----------------
|`Funding`|`Red`
|`Data`|`Blue`
|`Employment`|`Purple`
|`Collaboration`|`Orange`

### Civic Graph API

The **API** back-end is built with Python and serves information from a SQL database. 

API links:
- <http://api.civicgraph.io/api/entities>
- <http://api.civicgraph.io/api/connections>
- <http://api.civicgraph.io/api/categories>

### Azure Hosting

The fullstack application is hosted on **Azure cloud**. Our services are listed under the Civic-Graph resources froup.

## Local Environment Setup

### _UI setup_

*Most updated instructions can be found on the Civic Graph UI Github repo: <https://github.com/MicrosoftTCE/civic-graph-UI>*

All changes made to setup instructions should be made in the Github repo.

### _API setup_

*Most updated instructions can be found on the Civic Graph API Github repo: <https://github.com/MicrosoftTCE/civic-graph-API>*

All changes made to setup instructions should be made in the Github repo.


## Troubleshooting

What happens when something breaks in Civic Graph? The following are best practices and suggested steps as per previous experience.

Our services are hosted in the "South Central US" datacenters. This is automatically assigned and as far as we know, based on answers from Azure technical support, there is no way to change this.

Very rarely does Azure go down but checking the Azure status page is a simple first step to take in case there is an issue with Azure. Link: [https://azure.microsoft.com/en-us/status/](https://azure.microsoft.com/en-us/status/)

#### Diagnose:

If Azure status is all good, begin diagnosis. Is this a UI issue or an API issue?

UI issues include position of elements being off, text displayed incorrectly, etc.

API issues include data on graph not appearing or graph not appearing at all.

UI issues can be tied into API issues. For example, if the graph keeps loading and does not display any content, this is an API issue with failure to render on the UI.

#### UI issue

If the issue is with the UI:

1. Checkout master branch for the UI repo and create a new git branch with the name of the issue
2. Serve the app locally and try to replicate the UI problem on your local environment
3. Test any proposed changes to fix the problem locally
4. Once you're satisfied with the changes, commit and push them to your new branch
5. Create a Pull Request to merge into Master and have it reviewed to merge into az-prod branch

#### API issue

To check for an API issue, inspect the page using Google Chrome Developer Tools. If there are any red warnings, click on them to review.

Usually, API issues are related to the API code breaking, database not updating, or a break in the link to the API. Check the API links above to see if any return an error. 

To diagnose an API issue further, you want to go to Azure portal and check the logs as follows:

1. Go to **Resources** > **Civic-Graph** or [Link](https://portal.azure.com/#@civicmachineoutlook.onmicrosoft.com/resource/subscriptions/d6b238db-2ea5-4c4b-8a39-401d161baddf/resourceGroups/Civic-Graph/overview)
2. Click into the **Civic-Graph-API** Web service
3. On the left sidebar, select **Diagnose and solve problems**
4. Search for "failed request tracing logs"
5. Select the most recent log with a failed status code of _400_ or _500_

Read through the trace log and see if there is a line that the API is failing at. You will need to go through the API source code and find that line to start applying a fix.

## Further Technical Support

If you still need help diagnosing a problem and you have searched through all available (online) resources, you can open a support ticket via Azure for Azure technical support to assist. Your mileage may vary with how far someone will go to help you and you can always submit more than one ticket if you don't feel the issue has been resolved. Make sure to note everything you have tried so far.

## SQL Database

The database for Civic Graph API is hosted on ClearDB. It would be best to host under Azure DB instead but this has sufficed for now.

Credentials for the database via ClearDB can be accessed via LastPass.

## Registrar

This project is registered under Namecheap. Credentials to access Namecheap are available via LastPass.

## SSL Certificate

An SSL certificate is available via Azure portal for this web app.

