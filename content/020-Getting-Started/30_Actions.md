---
title: "Actions"
chapter: false
weight: 30
---

## Built-in and Custom Actions

As mentioned, one of the most powerful tools in scripting is the ability to invoke APIs of internal or external platforms. These allow the ability get, update, create or delete resources from the agent perspective in a very transparent manner.

By navigating to the Play/Action icon on the upper right, we can see a list of all built in actions and have the ability to create custom actions.

The script editor has various built-in actions that can be mapped to different constructors, such as transfer, change page etc. For this workshop, we will be creating a custom action by selecting the "**+**" icon.

![image](/images/scriptactions.PNG)

We will name our action "Update Case", select **Add Step**, and select **Execute Data Action**, under Data Actions.

![image](/images/scriptactionstep1.PNG)

Search for your Genesys Cloud Data Action integration in the Category field, and select the Data Action you published earlier.

Within the input field we will type "**{{**", begin typing the matching variable names and click the variable to autocomplete -

![image](/images/scriptactionautocomplete.PNG)

Your Execute Data Action should look similar to this, with all additional fields above mapped -

![image](/images/scriptactionmap.PNG)

Select **Add Step**, and select **If/Else** to add another step to our action.

If/Else contructors allow us to compare data and execute different actions depending on the outcome. 

They are simply logical operators that allow us to say things like "**If** this equals this, **Then** do this, or **Else** do this.

We will set out **Left Hand Side** to your **successresponse** variable.

Our **Operator** will be **Equals**.

And our **Right Hand Side** will be set to "Updated Successfully"

What we've just constructed is the **If** portion of our If/else statement. At the top of the image below, the action constructor tells us what the logic we entered equates out to - 

![image](/images/scriptoutput.PNG)

> **If the output from our API equals "Case Updated Successfully" Then...**

For this workshop we will trigger an alert to the agent to the agent to let them know the case updated successfully, however you can trigger numerous additional **Then** steps, including another custom action.

With the If section finished, we will select **Add Step** directly beneath it and select **Scripter > Alert**, and enter in something like "Case Updated Successfully" (you could also put your API Output variable here) this will be our **Then** action. 

![image](/images/scriptactionif.PNG)

Expand the If/Else action by clicking the If box and add a step under **Else**. You will repeat the steps of adding a scripter alert but this time we will provide a value of "Failed to Update Case" (in a real world scenario, we would likely map the output response here).

**If** your action looks like the image below **Then** select Save, **Else**, make your action look like the image below (see what we did there?) -

![image](/images/scriptactioncomplete.PNG)

We're ready to map this action!

Select your input field and select your "Case Status" variable within the Value drop down. Within the Placeholder field, you can enter something like "Enter Case Status", this text will display to the agent on this field before they enter any text into it (you can see placeholder text by going into preview mode).

![image](/images/scriptinputfield.PNG)

Select your button, select No Action Selected under Click Action, and find your action within the custom drop down.

![image](/images/scriptbuttonaction.PNG)

We should now **Publish** our script by selecting **Script > Publish** in the top left corner.

We now have a fully functioning script! or at least we hope? Time to test...

