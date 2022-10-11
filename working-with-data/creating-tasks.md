---
title: Creating Tasks
permalink: /docs/working-with-data/creating-tasks
parent: Working with Data
nav_order: 2
---
With a **data model** defined, you are able to add tasks to your workflow. There are a few different ways to do so,
depending on your use case.

![](/assets/images/4beb20d-add-new.png)

## Manually creating a task

To create a new task directly in Flowdash, simply click the `+ New Task` button in the workflow table page. You'll
notice a modal pop-up with all previously defined custom fields.

![](/assets/images/90184ee-add-new-user.png)

## Import from CSV

In cases where you want to migrate an existing data set to Flowdash, you can bulk import tasks using a CSV import.

## Import from Form

Sometimes, you want a public-facing form that anyone can use to submit data to Flowdash. In those cases, you can design
a web form within Flowdash that will automatically push responses to your workflow.

## Import from API

Another way to create tasks is programmatically through the API. This is useful when integrating with your core
application, or using [Zapier]({% link integrations/zapier.md %}) to integrate with another 3rd party software. Learn
more about [using the API to create tasks]({% link api/tasks-api/index.md %}).
