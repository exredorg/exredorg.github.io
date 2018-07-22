---
title: Node Groups
permalink: /guide/nodes/groups
---

Node prototypes are grouped by their function. This grouping is purely cosmetic though. It is not used anywhere in the back-end. It only exists to help the user quickly find the node he/she is looking for.

There are some conventions though.

Nodes in the Input group receive or get data from outside resources. As such they don't have input ports and other nodes in the flow can't send messages to them. They act as input for the flow and send messages to other nodes in the flow.  
An example is the **GPIO In** node that receives data from a GPIO pin.

Output nodes are the opposite. They send messages to or write to outside resources (eg. to a database).

There's one special node type that does not process any messages in the flow. These are the Daemon nodes. They are similar to a daemon process in Unix. They are long running background processes that provide services for other nodes.  
For example the **Redis Daemon** node provides a connection pool to a Redis database. The **Redis In** and **Redis Out** nodes use this connection pool to communicate with Redis.

Daemon nodes can be dropped anywhere in the flow. They don't have to be connected to any other nodes (in fact they can't be since they don't have input/output ports) but they have to be present if other nodes in the flow need to use their services.

