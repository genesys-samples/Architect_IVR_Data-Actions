---
title: "Architect"
chapter: false
weight: 40
---

## Testing Our Script

To close out part 1 of this workshop, we will create a simple architect flow that calls our data table, sets the returns as useable variables, and maps them to an agent script. We will be going over all architect portions in **Much** greater detail in part 2. For this portion, we are simply creating a basic flow to test our script and ensure it functions.

To start we will construct a queue:

If you didnt attend the prerequisite workshops - 
1. Navigate to Admin > Queues, **Create Queue**.
![image](/images/queuecreate.PNG)

Assign yourself as a member 

![image](/images/queueaddmembers.PNG)

Now we will create a new architect flow by navigating to **Admin > Architect**, within **Inbound Call** we will select **+Add** and provide a meaningful name, description and select **Create New**.

![image](/images/architectnewflow.PNG)

With our new flow constructed, the first thing we will do is add a new reusable task. On the left panel select **Add reusable task here**, hover over **Toolbox** and select **Task**.

![image](/images/architectnewtask.PNG)

We will then set this as our starting task, as further defined in part 2, this will be the entry point to our flow.

![image](/images/architectsetstart.PNG)

With our new blank canvas, we're going to add a couple items, the first being a data table lookup, within the toolbox navigate to **Data > Data Table Lookup** and set this as our starting point by dragging this onto our canvas.

By selecting this block, we can **choose the data table we constructed previously**, setting our input - **what are we using to find an entry in this data table?**. in this case we will statically assign our **Key/ANI** in the input field. As well as our outputs, or **what are we returning from this data table?**.

Our input/output mapping should look as follows - 

![image](/images/architectdt.PNG)

Within the found path of our data table we will drag a **Set Screen Pop** operator, which can be found in the toolbox under **Flow**.

![image](/images/architectsetscreen.PNG)

On the right hand side we will select our script, and begin mapping the **Outputs** from our **Data Table** to the **Input Variables** that we constructed in our script. Simply put, we have data being output from our data table, that we need to input into our script for agents to see.

 We will map the variables we retrieved from our data table lookup to the requested inputs for our script with a few exceptions, your screen pop fields should look like the diagram below, again,**this will be clarified and declared in part 2**. For now we're just testing our script to ensure it works.


![image](/images/architectscriptmap.PNG)

In the ending path we will add a **Transfer to ACD** by navigating within the toolbox to **Transfer > Transfer to ACD** and dragging this beneath our **Set Screen Pop**. Select the queue we constructed previously and in the failure path of the **Transfer to ACD** we will add a **Disconnect** Block which can be found in the base layer of the toolbox.

In the end, our flow should look like the image below.

![image](/images/architectflowend.PNG)

If your flow looks like the image above, select **Publish** on the toolbar to make your changes live.

![image](/images/architectpublish.PNG)

The very last step to testing our fancy new script is assigning a number to the flow that we just constructed.

The entire process may sound backwards, but we cant make pizza without an oven right?? And we can't build that oven without bricks... This process has us starting at the bricks.. Laying the foundation for the Oven that we'll build in part 2. 

Navigate to Admin > Call Routing, **Add Call Route** and 





