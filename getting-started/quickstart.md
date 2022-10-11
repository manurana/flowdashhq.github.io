---
title: "Quickstart"
permalink: /quickstart
excerpt: "Flowdash overview in 5 minutes"
hidden: false
metadata: 
  description: "Get up and running in Flowdash in just 5 minutes."
createdAt: "2021-01-21T22:44:52.539Z"
updatedAt: "2021-12-17T04:23:05.171Z"
nav_order: 1
---
Flowdash was designed to make it fast and easy to build task management software tailored to your unique business needs. The goal of this tutorial is to give you a quick overview of how Flowdash works. In this example, imagine we're a company launching a new product soon and have multiple users who requested early access. We'll create a simple workflow for manually reviewing those users, and automatically send an email to those who are approved.

# Getting started

1. Begin by creating an account at [flowdash.com](https://flowdash.com)

2. Once logged in, let's create a new workflow from scratch. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/20079d1-create-new-workflow.png",
        "create-new-workflow.png",
        1388,
        488,
        "#d8e2f1"
      ],
      "caption": ""
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/24db414-workflow-record-type.png",
        "workflow-record-type.png",
        2776,
        1448,
        "#fafbfb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Because this workflow will be tracking a *list of users* requesting early access, we'll make the record type *user*."
}
[/block]
# Design your data model

If you've used a spreadsheet before, this part will feel familiar. You'll notice that by default, we have a table with few special columns such as `Assigned to` and  `Stage`. More on that later.

For now, as we're tracking a list of users, we'll start by creating additional fields (e.g. columns) to capture the user's company and email address.

1. Create a text field named `Company`
2. Create an email field named `Email`
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb69512-create-new-field.png",
        "create-new-field.png",
        2650,
        1289,
        "#f8f9f9"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Fields & Data types",
  "body": "Unlike spreadsheets, when creating fields in Flowdash you have to specify a *data type*. Data types define the type of information that will be saved in the future. Flowdash supports multiple data types such as Text, Email, Date, File attachment, and more.\n\nBy defining a type, you're ensuring your data always remains clean and consistent. In order words, no data-entry mistakes down the line."
}
[/block]
# Build your workflow

Time to hop to the Flow Builder to create a process for reviewing users who requested early access. 

1. Navigate to the Flow editor by clicking on the diagram icon in the top left shortcut menu. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/238bf72-flow-builder-button.png",
        "flow-builder-button.png",
        1090,
        630,
        "#f3f3f6"
      ],
      "caption": "Navigate to the Flow Builder",
      "sizing": "80",
      "border": true
    }
  ]
}
[/block]
The Flow Builder is a visual editor where you can manage **stages** and **actions**. By default, a new workflow contains 3 stages (`Not Started`, `In Progress`, and `Finish`) and 2 actions (`Start`, and `Finish`).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb58315-Screen_Shot_2021-02-05_at_10.20.04_PM.png",
        "Screen Shot 2021-02-05 at 10.20.04 PM.png",
        466,
        380,
        "#f6f8f7"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "What's a stage?",
  "body": "*Stages* indicate the progress of a task throughout the workflow. At any given time, a task will always be within one of the defined stages. You can add as many stages as necessary to map out the various steps of your process."
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "What's an action?",
  "body": "*Actions* are manual decisions that users can take for any given stage. Those actions can transition from one stage to another. In the example above, when a task is `In Progress`, we can trigger the `Finish` action which will set the stage to `Done`."
}
[/block]
2. Let's start by removing the default stages and actions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d026876-remove-stages.gif",
        "remove-stages.gif",
        613,
        408,
        "#f7f8f6"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
3. Create two new stages: `Approved` and `Rejected`
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0b4524e-new-stages.gif",
        "new-stages.gif",
        644,
        407,
        "#f6f8f7"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
4. Create two actions that can be taken from the `Not Started` stage.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bcd8185-new-actions.gif",
        "new-actions.gif",
        431,
        335,
        "#f6f6f6"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can automatically create an *transition action* by connecting two stages in the editor. Keep in mind that the order in which you connect the stages matters!"
}
[/block]
5. Setup the `Move to Approved` action to send an email to the user.

Beyond stage transitions, actions can also implement business logic through a set of steps. For example, an action can send an email, trigger a slack alert, or automate actions in a 3rd party software.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/636edbe-email-step.gif",
        "email-step.gif",
        895,
        485,
        "#f8f7f7"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Customize your email with user data",
  "body": "When creating your email template, you can use user data as variables that will automatically get replaced when triggering the action. To do so, simply use the double bracket notation (e.g. `{{Email}}`)"
}
[/block]
6. Setup the `Move to Rejected` action to send a rejection email. Nothing too harsh, plz :) 

7. Let's return to the dashboard view by clicking on the back arrow in the top left of the editor.

# Add data to your workflow 

1. Now that the workflow is ready to use, let's create a user to review by clicking the `+ New User` button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c69a8f-add-new-user.png",
        "add-new-user.png",
        2650,
        1388,
        "#868a8f"
      ],
      "sizing": "80",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Please use your real email when creating users",
  "body": "Remember, we've setup our actions to send emails. As a result, please use your real email address to ensure the emails get delivered, and to avoid spamming a random person."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c0e7178-import.png",
        "import.png",
        1094,
        644,
        "#f2f2f5"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Importing data to Flowdash",
  "body": "In this example, we manually create a new user. However, in practice this isn't the way people would request early access. That's why Flowdash supports importing data using a CSV, a fully customizable Web Form, or using an API."
}
[/block]
# Triggering an action

Great, now that you've added a record, we can open up the details page and take an action.

1. Open the new user's details page by clicking on the latest record in the table view.

2. Take a moment to familiarize yourself with the details page. In particular, notice the user's current stage (top left) and available actions for that stage (top right). These are the actions we've created in the Flow editor!
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/78c0235-a384b72-Screen_Shot_2021-02-10_at_1.09.59_PM.png",
        "a384b72-Screen_Shot_2021-02-10_at_1.09.59_PM.png",
        1224,
        243,
        "#f8f3f1"
      ]
    }
  ]
}
[/block]
3. Decision time: Let's decide to `Move to approved` this user. 

You'll notice that the current stage for this user has changed to "Approved". Also, assuming you entered your personal email, you should have gotten an email notification.

4. Return to the list view (top left).

# Wrapping up

Congratulations, you've successfully created and used your very first workflow! To summarize, we have:

* Define a data model to capture user information
* Created a workflow for either approving or rejecting a user
* Added automation for automatically sending an email
* Added a new user to our workflow
* Approved a user, which triggered an email being sent. 

In doing so, you've touched on many on the core ideas behind Flowdash and ready to build and collaborate on more complicated workflows.
