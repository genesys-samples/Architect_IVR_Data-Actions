---
title: "Design"
chapter: false
weight: 10
---

## Scripter Design Elements

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
