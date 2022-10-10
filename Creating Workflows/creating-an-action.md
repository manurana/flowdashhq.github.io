---
title: "Creating an Action"
slug: "creating-an-action"
hidden: false
createdAt: "2021-02-11T19:33:57.610Z"
updatedAt: "2021-12-17T04:34:20.786Z"
---
Actions can be created one of two ways.

# Connecting two stages
If your action is intended to transition a task from one stage to another, you can connect the two stages visually in the Flow Builder:
1. Click down on the connection icon from the stage you want to transition *from*.
2. Release your mouse cursor over the stage you want to transition *to*.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c68d232-connect-stages.gif",
        "connect-stages.gif",
        297,
        246,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
# Creating an action manually
Alternatively, you can add a new action by clicking the "New Action" button at the top of the Flow Builder.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f60a10-new-action.png",
        "new-action.png",
        2648,
        1320,
        "#f9fafa"
      ]
    }
  ]
}
[/block]
When creating a new action you can specify
* a unique name for the action in your workflow.
* an optional color, which will be used as the button background color for your action.
* a series of [steps](doc:action-steps) to perform when the action is taken.
* (optional) where to [navigate](doc:action-navigation) after the action is performed.