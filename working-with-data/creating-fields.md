---
title: Creating Fields
permalink: /docs/working-with-data/creating-fields
parent: Working with Data
nav_order: 1
---
When opening (or creating) a workflow, the first view you will see is a table view. The table view is composed of
multiple fields. Some of these fields are special and automatically created, while others are custom fields you can
create based on your use case.

## Special fields

By default, there are four special fields that are included in all workflows:

* **Assigned To** is used for task tracking purposes, to specify which collaborator is assigned to the task.

* **Stage** represents the current stage of any given task throughout the workflow.

* **Created on** is a non-editable field that represents when a task was created.

* **Updated On** is a non-editable field that represents the last time a task was updated.

At any given time, you can [show or hide these fields]({% link working-with-data/show-hide-and-order-fields.md %}) if
they are not relevant to your workflow.

## Creating new fields

![](/assets/images/8ed3a77-create-fields.gif)

You can create new fields from the table view by selecting the `+ New Field`  link placed after the last field in the
table (see screenshot above). Besides the field name and type, you can also specify whether a field is `Editable`
or `Required`.

When a field is editable, the value of the field can be edited after a task has been created.

When a field is required, a new task cannot be created unless a value is provided for this field.

## Updating existing fields

It is possible to edit a field's properties (e.g. name) after the fact. To do so, simply select the field from the table
and select `Edit field`.

![](/assets/images/ef3cc2e-edit-field.gif)

## Deleting fields

Similarly to editing a field, you can also delete a field by selecting the field from the table view.

![](/assets/images/d33fde8-delete-field.gif)

{: .danger-title }
> Data deletion
>
> When deleting a field, *all task data for this field will be lost*. This is not a reversible action.

## Advanced: Editing multiple fields at once

Sometimes, you may want to modify all your fields at once. In those cases, you can modify fields from within the
workflow settings page by navigating to `Settings`  (gear icon) and selecting the `Fields` tab.
