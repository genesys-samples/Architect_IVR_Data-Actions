---
title: "Variables and templates"
chapter: false
weight: 20
---

## Variables

Everything (almost) within a script **can** be a variable. Not everything needs to be, or should be a variable. To demonstrate this we will add a text box to our main vertical container, and paste in the text below. (based upon the example below, you can clearly just type something in here if you don't want to copy and paste)

```
Hi, thanks for calling our super cool company that does things! 
```
Our script is now displaying a static greeting that agents can read on every call. However, what if we want to have the agents say their name? or greet callers differently on a case by case basis. This is (at a very basic level) where variables absolutely shine (in a not incredibly glorious way)!

There are a few different types of variables which we will break down into two categories - 

**1. Scripter variables.**

**2. Custom variables.**

 #### Scripter Variables
These are built in variables that can be referenced without any additional configuration, such as the agent and queue name. A full list can be found by selecting the variable (or cube shaped icon in the upper right corner) and expanding the "Scripter" drop down.

![image](/images/scriptscriptervariables.PNG)

Some fields require selecting your variable in a dropdown, while in other fields you can reference/input a variable by typing 2 squiggly brackets (as they're known in the science community), or **{{** when interacting with an input field such as a text box.

By typing these within our text box, we are presented with a list of custom and scripter variables which can be input by selecting one. This list is also searchable by variable name, so it is best practice to use logical naming conventions.

In the example below, we will make a fully customized script by simply adding "My name is", and using the squiggly brackets for find "Scripter.Agent Name"

![image](/images/scriptagentvariable.PNG)

Below is an example where we've searched "Name" in the search field (searching becomes very useful as your scripts grow to tens or hundreds of custom variables).

![image](/images/scriptvariablesearch.PNG)

Non-input variables, along with many other components, can be tested by selecting preview script on the top right of the script interface.

![image](/images/scriptpreview.PNG)

Within the preview window, we can see our {{Scripter.Agent Name}} variable is now displaying the names on our account. The preview window is useful for testing components and displaying the script without all of the container formatting. It can be exited by selecting the preview script button again.

#### Custom Variables
These variables are created by you to customize your script, trigger visibility, data actions, script actions, etc.

By navigating back to the variable panel on the upper right corner, and selecting the **+** icon you can see a list of the different variable types. We will focus on **Basic String** types for this workshop. You can click [**Here**](https://help.mypurecloud.com/articles/dynamic-script-variables/) for information on dynamic variables.

The variable constructor allows you to define whether the values of the variable will be output from the script (to use in another source) or input to the script from another source (such as an architect flow). You can also define default values to display static information if no value is defined.

We will construct the following 6 string variables which map directly to the data table we constructed previously, these will all be set as **Input** with no default value - 
  * ANI 
  * CustomerName
  * Services
  * EmbeddedMap
  * KBURL
  * DataTableID

![image](/images/scriptcustomvariable.PNG)

We will add 1 more string variables with no direction set (leave outbound and inbound set to no) - 
  * CaseStatus

When you're done, you should have a list that looks like this - 

![image](/images/scriptvariablelist.PNG)

### Building our Script

With our 3 variables created, we will add the necessary components to map them to.

To start, we will delete the 2 buttons we've created (by selecting the button and clicking the trash can on the right side), making sure not to delete the containers themselves. Within the now empty containers, we will add web pages by selecting the **globe** icon while interacting with the container. The result should look like this - 

![image](/images/scriptwebpages.PNG)

> **You can select the webpage and navigate to layout to adjust the size**

We will now map our Embedded Map and KB URL variables to these by selecting a web page component and inputing the variable into the "Web Page Source" Field.

![image](/images/scriptwebpagesource.PNG)

With both of our web pages mapped, we will insert the customers name into our greeting text box. Your text box should look something like - 

```
Hi {{Customer Name}}, thanks for calling our super cool company that does things! My name is {{Scripter.Agent Name}}
```

If you ended up with your text box below the webpages, you can shift component by selecting the component and clicking the up or down arrow on the right hand side. 

![image](/images/scriptupdown.PNG)

We will Finish by adding an input field and a button beneath these web pages

![image](/images/scriptbuttoninput.PNG)

Your script design is now complete! It should look something like - 

![image](/images/scriptcomplete2.PNG)

Neat huh?! At this point, we like to consider this modern contemporary CX art.. We will now select **Script > Save, and Publish**.

The very last item in basic scripting is the ability to create component templates and script templates out of either containers, individual components, or entire scripts. 

You can create component template by selecting a container or component, and clicking the box icon next to the arrows and naming it - 

![image](/images/scriptcomponenttemplate.PNG)

These can be input into scripts using the same icon on the toolbar at the top and selecting the template by name.

Full script templates are created by selecting **Script > Create Template From Script**. They are selected upon creating a new script.