---
title: Creating and updating tasks from your database
permalink: /docs/data-sync/creating-and-updating-tasks-from-your-database
parent: Data Sync
nav_order: 1
---
After [Connecting to a database]({% link data-sync/connecting-to-a-database.md %}), you can setup Data Sync when
creating a new workflow or via the Data tab.

Choose the database you've just connected and write your query that fetches records that should become a task.

![](/assets/images/400c00c-database_setup.png)

Optionally add a variation of your fetch all records query to fetch a single record. We've supply the
variable `{{ "{{id" }}}}` to represent your primary key.

{: .info-title }
> Query must return results
> 
> In order for us to analyze the results of your query, it must return at least one result.


## Using a separate query for updates

If you want to use a different query to keep your tasks in Sync, select `Use a separate query for subsequent updates`
and input your query.

![](/assets/images/1be9ed7-Separate_update_query.png)

## Mapping columns to fields

Press continue and we will now run your query. When it's completed you will have to confirm the columns to field
mapping. You will have the choice of selecting an existing field or creating a new one.

![](/assets/images/d9a303c-map-fields.png)

## Sync Settings

Below you will have the option to configure how often the data sync will query your database.

![](/assets/images/6e8241a-sync-settings.png)
