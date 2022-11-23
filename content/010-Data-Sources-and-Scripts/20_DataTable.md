---
title: "Data Table Configuration"
chapter: false
weight: 20
---

## Data Table Construction
![image](/images/DTlimits.PNG)

For this portion of the workshop we will construct an internal data source, or **Data Table**. This data table will serve as the repository containing customer information that we will present to our agents. 

Keeping in mind the base idea of **"Creating more meaningful interactions"**,
the best practice when constructing a data table is asking the question -  **"What information can I provide to my agent to make this a catered experience for the customer"**. Regardless of whether you're interacting with an external CRM or an internal data table, **more is more**. This means, store, import or pull as much information for a customer as possible, even if you wont use it now, you may use it later. If I knew the customers favorite sports team, I could use that to create a more meaningful interaction! 

To begin we will navigate to Admin > Data Tables and select the **+** icon on the top right corner to construct a new table.

Data Tables have 2 primary components that we will need to define prior to populating our data table -

  * **Reference Key Label** - This is the 'key', or the piece of data that will be used to reference a specific row in the data table. In the example below we are using ANI, or the callers phone number, to look up the specific row of data.
  > **During construction, ANI is simply the name we are giving this column, or key. You can enter any value into this field, but this is the field we will use to find our customer.**

  * **Custom Fields** - These fields are ultimately the data we are trying to gather by looking up the customers ANI. This could be simple items such as their name and address or more advanced items such as KB articles that will help an agent troubleshoot their account, or items such as external account numbers for use in future data actions. 
> **In the image below you can see the 4 variable types for these fields. Upon selecting a variable type you will need to name the field, and if desired provide a default value (this is useful if many rows will house the same data for the agent script or routing).**

![image](/images/datatableconstruction.PNG)

For our use case we will construct a data table with the following **string** type fields (with the key of ANI) -
  * CustomerName
  * CaseStatus
  * Services
  * EmbeddedMap
  * KBURL

We will begin by populating a single row into this data table. 

For ANI, we will enter in the number we will be calling from (we will not use .e164 or dashes as it will simplify ANI parsing later on). 

For **CustomerName** you can enter any name you would like.

For **CaseStatus** we will just provide a fake case status

For **Services** we will define 2 services by a pipe, such as "Insurance|Childcare".

For **EmbeddedMap** we will enter the following URL -
```
https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4328.119139375052!2d-105.04811270372998!3d39.90911499772483!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x876b8bb21a22f617%3A0xa3877b5da434ea5f!2sOrchard%20Park!5e0!3m2!1sen!2sus!4v1659042755728!5m2!1sen!2sus
```
For KB URL you can enter a URL to any page you would like.
> **Note: Not every web page is configured to be i-frameable, so it is important to test and ensure these pages display correctly at the script configuration.**

With our first row completed, we will add 1 more row with a different ANI that you can remember (such as 1234) and blank fields for the rest of the columns. 

Once you have completed your 2 row entries, your rows and columns should look something like this -

![image](/images/DTrowcomplete.PNG)

While it may seem basic, we've layed the basic building blocks to provide our agents interactive maps based upon the customers location, knowledgebase suggestions based upon indicators from the customers account, and base level account information that customers hate having to offer to both the IVR and the agent.

If a customer calls in and matches this record, you can **WOW** them with what you know about their account, and this is a very rudimentary and difficult way of pulling a customers information because we're building it locally.

 In this case, this information is relatively static, but by interfacing with external platforms this information can be pulled and used on the fly!

We've now completed our internal data source! You can continue to add additional fields to this data table as needed (to the constraints of the limits above).