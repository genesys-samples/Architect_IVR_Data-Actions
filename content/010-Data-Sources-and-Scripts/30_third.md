---
title: "Script Configuration"
chapter: false
weight: 30
---

## Building Your Script

To begin we will navigate to Admin > Scripts and create a new script. After providing a name you will be presented with a list of default script options, for this workshop we will use a **Blank Script**.


Welcome to the blank canvas! 

![image](/images/scriptcanvas.PNG)

While we encourage all forms of artistic design, for this portion of the workshop we will build a script that, while not the most beautiful, demonstrates the simplicity of providing powerful information to the agents.

Before we begin, it is important to understand the concepts and fundamentals of script construction. 

By Selecting "Script" (top left corner of your blank script) > Script Properties we can see script features. Scripts can be turned on for different media types, enabled to access data actions and UUI data, or loaded with Outbound campaign contact lists. For this workshop, we will enable Inbound and Data Actions.

![image](/images/scriptproperties.PNG)

In the same "Script" button, you will also see a "Save" button. It is recommended to save frequently to avoid losing your work!

Scripts can be very simple with static components, meaning we can display the same script to a set of agents (or all agents) on every call. Even a static script can provide incredibly beneficial information, or even embedded tools to an agent.

Scripts can also grow to become more advanced with external data actions and fully dynamic variables. Using custom script actions you can allow agents to trigger API calls to internal or external systems with a click of a button, such as updating a customer record in an external CRM.

### Containers and Arrangement

The basic building blocks of scripts are **Horizontal Containers** and **Vertical Containers**. Simply put, do you want your components to align left to right? or top down? The script starts out as root vertical container

In the image below, you can see the 2 container types of horizontal and vertical at the top tool bar. 

![image](/images/scriptcontainers.PNG)

Containers are capable of being nested, meaning you can have containers within containers. At the bottom of the screen you can see what container you're currently interacting with and easily navigate between these containers by clicking on lower or higher level containers.

![image](/images/scriptnesting.PNG)

In the image below, we have a horizontal container (depicted as the dotted box on the outside) with 2 nested horizontal containers stacked side by side. We can see we're currently interacting with one of these nested horizontal containers as it appears bolded. 

![image](/images/scripthorizontalstack.PNG)

This allows us to split a single horizontal container into 2 separate containers, and input components such as buttons into separate portions of the screen. Below we can see a button in both of the horizontal containers, creating a visual separation of these components.

![image](/images/scriptbuttons.PNG)

There are numerous visual editors we can add to these containers, such as background color or borders (both of which can be found by selecting the container and selecting appearance on the right hand side).

![image](/images/scriptcontainerappearance.PNG)

Within layout, we can define visualizations such as width and height, as well as **Child Arrangement** (do I want my buttons centered, at the start or at the end of a container?) and **Visibility** (do I only want to show this component based upon other parameters?)

Width and height all you to define the size of a component. For some components such as containers, leaving them to stretch or auto-size will allow them to fill up the space they need. Components such as images may need to be manually sized.

By selecting each of our button containers and setting child arrangement to **center** we can see the buttons shift to the center of the container.

![image](/images/scriptcentered.PNG)

By Selecting a button (or even the container itself) we can find background color, or text color where applicable, within both the common and appearance toolboxes. Colors can be defined at a hex level for granular color schemes.

![image](/images/scriptcolorhex.PNG)

They can also be defined as a variable, allowing for different color schemes to be input dynamically.

![image](/images/scriptcolorvariable.PNG)

Within the layout section of a component we can configure visibility. Visibility allows us to define a boolean variable to determine whether or not a component displays.

Below we've assigned a boolean variable named "Existing Customer?", which would allow us to hide script components (such as account fields) if the customer is not an existing customer.

![image](/images/scriptvisibility.PNG)

### Variables

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

We will construct the following 3 variables which map directly to the data table we constructed previously, these will all be set as **Input** with no default value - 
  * Customer Name
  * Embedded Map
  * KB URL

![image](/images/scriptcustomvariable.PNG)

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

Your script is now complete! It should look something like - 

![image](/images/scriptcomplete.PNG)

Neat huh?! We will now select **Script > Save, and Publish**.

The very last item in basic scripting is the ability to create component templates and script templates out of either containers, individual components, or entire scripts. 

You can create component template by selecting a container or component, and clicking the box icon next to the arrows and naming it - 

![image](/images/scriptcomponenttemplate.PNG)

These can be input into scripts using the same icon on the toolbar at the top and selecting the template by name.

Full script templates are created by selecting **Script > Create Template From Script**. They are selected upon creating a new script.
