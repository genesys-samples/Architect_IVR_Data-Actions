---
title: "Conclusion"
chapter: true
weight: 90
---

# Conclusion

Congrats! You've reached the end of today's workshop.
Please fill out today's feedback form via this [TODO](TODO)

{{% children showhidden="false" %}}


The very last step to testing our fancy new script is assigning a number to the flow that we just constructed.

The entire process may sound backwards, but we cant make pizza without an oven right?? And we can't build that oven without bricks... This process has us starting at the bricks.. Laying the foundation for the Oven that we'll build in part 2. 

Navigate to Admin > Call Routing, **Add Call Route**, select your flow within **Regular Routing** and define your called address under **Addresses** on the right, this will be and **DID** you own on the platform, or have built into your **DID Pool**

![image](/images/callrouting.PNG)

By calling the number you've assigned to this, you're calling the flow you just created with the **Data Table Lookup and Set Script**. If you assigned yourself as a member of the queue you should be able visually see the items we constructed.