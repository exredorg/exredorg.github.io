---
title: Flow Editor
permalink: /guide/flows/editor
---

Flows define a network of processes (nodes) that exchange data across connections.

Nodes receive messages, act on them and send a new or updated message to other nodes that are connected to them.

The name of the currently selected flow and node is displayed in the navigation bar on top of the page.

![flow-editor](/assets/images/exred-flow-editor.png)

__Adding nodes__  
You can add nodes to the current flow by double clicking on one of the node prototypes in the node selector on the left. Click on the group names to expand the group

__Deleting nodes__  
Click on a node in the flow editor. This will select the node.  
Click on the Trash icon on the right side under the info and config tabs. This deletes the node. 
Deletion will fail if the node is connected to any other nodes. You need to delete the connections first.  

__Note:__ at this time there's no confirmation dialog and the deletion is immediate and permanent. 
{: .notice--warning}

__Connecting nodes__  
Start dragging from the dot on the side of the node and drop the connection arrow onto a dot on another node.

__Deleting connections__  
Hower over the circle in the middle of a connection. The circle should turn into a red X. Clicking on the X will remove the connection.  

__Note:__ just like with deleting nodes there's no confirmation dialog and the connection will be deleted immediately and premanently.
{: .notice--warning}
