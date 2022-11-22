---
title: "Data Sources"
chapter: false
weight: 30
---

## Referencing a Data Source

Scripts can be used to provide powerful tooling, such as embedding tools, providing knowledge suggestions and customer information. One of the most powerful functions scripts offer is the ability to tie API calls to the buttons and fields agents are interacting with inside of the agent script interface. This allows agents to update external or internal case records, process payments, schedule appointments etc. in a transparent and simplified manner without ever navigating away from Genesys Cloud.

For this workshop, we will be using the internal data table we just created as a mock external data source. We will import a data action that updates the **CaseStatus** field for a row within our data table. While this is an internal data action, the methodology can be used for external actions.

While still within the data table we constructed, we will copy the data table GUID and store this for later reference. This can be found within the address bar as seen below - 

![image](/images/DTguid.PNG)

With our data table GUID saved, we will download and import an already constructed data action.

If you do not have an Oauth Client with **Data Table Write** permissions, or do not have a **Genesys Cloud Data Actions** integration installed, please reference the following page from the [Data Action Workshop](https://workshop.genesys.com/workshops/DataActionsWorkshop/020-configuration/30_third.html), note this does not specify a specific Oauth role but demonstrates how to construct the client and allocate permissions.

To import the data action, navigate to - https://github.com/GSC-Shared-Resources/ArchitectWorkshopContent, select the green **Code** button, and download zip.

![image](/images/githubdl.PNG)

After extracting this folder on your local machine, navigate to Genesys Cloud > Admin > Actions, select "Import" and navigate to the .json file you just extracted. Select your integration name and provide the data action a name.

![image](/images/daconstruct.PNG)

To validate that the data action works properly, within the data action we just imported, we will navigate to Setup > Test, enter in fake information for every field **except ANI** where we will enter in the ANI we provided (1234) for our blank row entry and select **Run Action**. If the action returns green/successful, we can navigate back to our data table and see these updates to that row, however at this point we should be able to **Save & Publish** our data action.

![image](/images/DAtest.PNG)

We've now created a data action to update our mock CRM/DB that can be used within the agent script to allow agents to make updates to 'external' platforms without having to leave their single pane of glass.