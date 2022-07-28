---
title: "Script Configuration"
chapter: false
weight: 30
---

## Data Table Construction

To begin we will navigate to Admin > Scripts and create a new script. After providing a name you will be presented a list of default script options, for this workshop we will use a **Blank Script**.

Welcome to the blank canvas! While we encourage all forms of artistic design, for this portion of the workshop we will build a script that, while not the most beautiful, demonstrates the simplicity of providing powerful information to the agents.

To begin, it is important to understand the concepts of script construction. 

Scripts can be very simple with static components, meaning we can display the same script to a set of agents (or all agents) on every call. Even a static script can provide incredibly beneficial information, or even embedded tools to an agent.

Scripts can also grow to become more advanced with external data actions and fully dynamic variables. Using custom script actions you can allow agents to trigger API calls to internal or external systems with a click of a button, such as updating a customer record in an external CRM.

The basic building blocks of scripts are **Horizontal Containers** and **Vertical Containers**. Simply put, do you want your components to align left to right? or top down?

In the image below, you can see the 2 container types of horizontal and vertical at the top tool bar. 

![image](/images/scriptcontainers.PNG)

Containers are capable of being nested, meaning you can have containers within containers. At the bottom of the screen you can see what container you're currently interacting with and easily navigate between these containers by clicking on lower or higher level containers.

![image](/images/scriptnesting.PNG)

In the image below, we have a horizontal container with 2 nested horizontal containers stacked side by side. 

![image](/images/scripthorizontalstack.PNG)

This allows us to split a single horizontal container into 2 separate containers, and input components such as buttons into separate portions of the screen. Below we can see a button in both of the horizontal containers, creating a visual separation of these components.

![image](/images/scriptbuttons.PNG)

There are numerous visual editors we can add to these containers, such as background color or borders (both of which can be found by selecting the container and selecting appearance on the right hand side).

![image](/images/scriptcontainerappearance.PNG)

Within layout, we can define visualizations such as **Child Arrangement** (do I want my buttons centered, at the start or at the end of a container?) and **Visibility** (do I only want to show this component based upon other parameters?)

Below we can see both buttons being centered within their containers with a child arrangement of center.

![image](/images/scriptcentered.PNG)