---
title: "Definitions"
chapter: false
weight: 10
---

## Definitions

### Data Sources
A data source is any place an organization may store customer (or other) data that we want to reference to invoke routing decisions or provide powerful agent tooling.

We will divide this into 2 types, **Internal Data Sources** and **External Data Sources**.

### Internal Data Sources
As you may recall from the Data Action Construction Workshop, we utilized Genesys Cloud API's to reference queue data. From the Genesys Cloud perspective this will be considered an internal data source as we are not invoking data from external systems.

Genesys Cloud also has a 'data base' constructor, called **Data Tables**. For the purpose of this workshop, we will reference a data table to power most of the variables within our script.

### External Data Sources
Any system external to the Genesys Cloud environment that houses data we want to reference for routing and scripting is considered an external data source. Typical examples would be CRM's and data bases. Interacting with these systems typically requires custom data actions or integrations.

### Scripts
Scripts are what Genesys defines as agent displays. Using data from internal and external data sources, agents can be presented with powerful tooling such as customer record information, knowledge articles, the ability to execute data actions with button clicks, and many other functionalities that allow contact centers to create **meaningful interactions**.


