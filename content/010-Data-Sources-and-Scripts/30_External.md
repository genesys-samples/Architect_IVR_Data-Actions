---
title: "External Data Sources"
chapter: false
weight: 30
---

## Referencing an External Data Source

For our external data source, we will create a mock API Endpoint [**Here**](https://beeceptor.com/)

If you have a preferred API mocking tool, feel free to use that.

If you have an external data source, such as a CRM, or any place that you can easily POST an update to, feel free to use that, though we will not assist in troubleshooting issues relating to these.

Within Beeceptor, provide your endpoint a unique name and select "Create Endpoint".

![image](/images/beeceptorname.PNG)

Select "Mocking Rules" on the upper right and select "Create New Rule".

![image](/images/beeceptormockingrules.PNG)

![image](/images/beeceptornewrule.PNG)

Change the Method to "POST" and modify the response body to -

```
{"Case":"Updated Successfully"}
```

![image](/images/beeceptorrule3.PNG)

After saving, copy your endpoint address. We now have a mock API to POST to!

![image](/images/beeceptorurl.PNG)

Within Genesys Cloud, Navigate to Admin > Actions and create a new Web Services Data Action.

![image](/images/Newaction.PNG)

Under the Input contract add a string named "CaseStatus", under Output Contract create a string named "Case"

![image](/images/actioncontract.PNG)

Within the Configuration tab, set the request type to "POST" and paste your beeceptor endpoint URL into the "Request URL Template".

![image](/images/actionconfiguration.PNG)

Navigate to the Test tab, enter in a fake case status into the input field, and run action. You will see an output of "Updated Successfully".

![image](/images/actiontest2.PNG)

You can now save and publish this data action.

By navigating back to beeceptor, you should see the POST request you just executed using the test, by expanding it you can see the case status you entered and the response that was returned.

![image](/images/beeceptorlog.PNG)
