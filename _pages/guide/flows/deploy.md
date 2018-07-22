---
title: Deploying Flows
permalink: /guide/flows/deploy
---

You can deploy flows with the Deploy button in the top-right corner.

This will set up the supervison tree and create the nodes needed to run the flow. Once deployment is done the flow is live and ready to start processing messages.

![flow-deploy](/assets/images/exred-flow-deploy.png)

Messages can come from input nodes like the GPIO In node that can receive messages from a Raspberry Pi's GPIO pins.  

You can also interact with some nodes through the editor UI. These nodes have a fire button on the left side that when pressed fires an action defined by the node.  
For example the Trigger node will send a message when its fire button is pressed in the UI.
 
Running nodes can broadcast different types of events. One of these is the notification event that gets streamed to the UI when you open the debug tab. Events are internally represented as maps and displayed as JSON objects in the UI.  
You can hover over an event in the Debug tab and the corresponding node that produced the event will turn yellow in the UI.

