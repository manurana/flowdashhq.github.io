---
title: Creating an Action
permalink: /docs/creating-workflows/creating-an-action
parent: Creating Workflows
nav_order: 3
---
Actions can be created one of two ways.

## Connecting two stages
If your action is intended to transition a task from one stage to another, you can connect the two stages visually in the Flow Builder:
1. Click down on the connection icon from the stage you want to transition *from*.
2. Release your mouse cursor over the stage you want to transition *to*.

![](/assets/images/c68d232-connect-stages.gif)

## Creating an action manually
Alternatively, you can add a new action by clicking the "New Action" button at the top of the Flow Builder.

![](/assets/images/0f60a10-new-action.png)

When creating a new action you can specify
* a unique name for the action in your workflow.
* an optional color, which will be used as the button background color for your action.
* a series of [steps]({% link automations/action-steps.md %}) to perform when the action is taken.
* (optional) where to navigate after the action is performed.
