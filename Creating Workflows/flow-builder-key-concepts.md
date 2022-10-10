---
title: "Key concepts"
slug: "flow-builder-key-concepts"
hidden: false
createdAt: "2021-02-11T19:26:04.605Z"
updatedAt: "2021-12-17T04:32:35.576Z"
---
Once you've set up a **data model**, you'll want to think about the workflow itself. For each task, what is the specific process that your team should follow to complete that task? What are the major steps (or stages) of that process? What actions can users take at each step in the process? In Flowdash, these are all configured visually through the **Flow Builder**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72f9238-flow-builder-full.png",
        "flow-builder-full.png",
        2648,
        1320,
        "#fafafa"
      ]
    }
  ]
}
[/block]
# Stages

A workflow is made up of multiple **stages**. You can think of a task's stage as the high-level status of where the task is in your workflow. For example, if you're building a workflow to approve budget requests, your stages might be `Needs Review`, `Under Review`, `Approved`, or `Rejected`.

# Actions

At any given stage, users of your workflow can perform one or more **actions**. An action is a sequence of steps that should be executed on the user's behalf. In its simplest form, an action might simply update the task's stage (for example, an `Approve` action might update the stage from `Under Review` to `Approved`). In more advanced use cases, you can configure actions to do much more, such as sending a email or Slack message, or calling an API.