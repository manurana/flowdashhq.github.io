---
title: "Creating Fields"
slug: "creating-fields"
hidden: false
createdAt: "2021-02-11T19:17:34.383Z"
updatedAt: "2021-12-17T04:30:56.749Z"
---
When opening (or creating) a workflow, the first view you will see is a table view. The table view is composed of multiple fields. Some of these fields are special and automatically created, while others are custom fields you can create based on your use case.

# Special fields

By default, there are four special fields that are included in all workflows:

* **Assigned To** is used for task tracking purposes, to specify which collaborator is assigned to the task.
 
* **Stage** represents the current stage of any given task throughout the workflow.

* **Created on** is a non-editable field that represents when a task was created.
  
* **Updated On** is a non-editable field that represents the last time a task was updated.  

At any given time, you can [show or hide these fields](doc:show-hide-and-order-fields) if they are not relevant to your workflow.

# Creating new fields
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ed3a77-create-fields.gif",
        "create-fields.gif",
        600,
        291,
        "#f6f7f8"
      ],
      "border": true
    }
  ]
}
[/block]
You can create new fields from the table view by selecting the `+ New Field`  link placed after the last field in the table (see screenshot above). Besides the field name and type, you can also specify whether a field is `Editable` or `Required`.

When a field is editable, the value of the field can be edited after a task has been created.

When a field is required, a new task cannot be created unless a value is provided for this field.    

# Updating existing fields

It is possible to edit a field's properties (e.g. name) after the fact. To do so, simply select the field from the table and select `Edit field`.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ef3cc2e-edit-field.gif",
        "edit-field.gif",
        600,
        263,
        "#f4f5f7"
      ],
      "border": true
    }
  ]
}
[/block]
# Deleting fields

Similarly to editing a field, you can also delete a field by selecting the field from the table view. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d33fde8-delete-field.gif",
        "delete-field.gif",
        600,
        263,
        "#f4f5f7"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Data deletion",
  "body": "When deleting a field, *all task data for this field will be lost*. This is not a reversible action."
}
[/block]
# Advanced: Editing multiple fields at once

Sometimes, you may want to modify all your fields at once. In those cases, you can modify fields from within the workflow settings page by navigating to `Settings`  (gear icon) and selecting the `Fields` tab.