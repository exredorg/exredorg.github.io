---
title: Demo Flow
layout: single
permalink: /guide/nerves/demo/
---

The Exred Nerves release image comes with a database populated with a demo setup:

![demo](/assets/images/exred-nerves-demo-1.png)

To try it out do this:

1. Click on the deploy button in the top-right corner

    A notofication should show up that says 'Requesting Deploy' and a couple seconds later another one saying 'Deployed Flows'.  
    At this point processes were created on the back-end for each of the nodes in the flow and they were configured according to their settings in the 'Config' tab.

2. Switch to the Debug tab on the far right side
3. Click on the Play button in the Trigger node that's in the top left of the flow editor area.  
    You should see a debug message showing up in the Debug window with a "Hello World" payload.

    This is what happened in the background:
    - Trigger node in the UI received the click
    - a message was sent to the corresponding Trigger process that runs on the back-end
    - 'Trigger' process sent a message to the 'Hello Fun' process
    - 'Hello Fun' prepended "Hello" to the message and sent it to the 'Debug' process
    - 'Debug' process sent the message back to the UI
    - UI displayed the message in the Debug tab

4. Click on the Trigger node, switch to the 'Config' tab and change its configuration (change the payload or change the interval to 2000)
5. Save the new config and deploy the flow again
6. Switch back to the Debug tab and see what happens when you click on Trigger again


The rest of the nodes are examples of reading from/writting to a GPIO pin and reading a value from Redis.

If you switch to the Info tab and click on a node you'll find documentation on how to use that node type.

For more information read the rest of the User Guide under the Flows and Nodes sections.

