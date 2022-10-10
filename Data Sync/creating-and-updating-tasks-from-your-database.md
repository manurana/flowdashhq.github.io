---
title: "Creating and updating tasks from your database"
slug: "creating-and-updating-tasks-from-your-database"
hidden: false
createdAt: "2021-09-08T05:51:13.554Z"
updatedAt: "2021-12-16T01:41:31.135Z"
---
After [Connecting to a database](doc:connecting-to-a-database), you can setup Data Sync when creating a new workflow or via the Data tab.

Choose the database you've just connected and write your query that fetches records that should become a task. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/400c00c-database_setup.png",
        "database setup.png",
        1259,
        1042,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
Optionally add a variation of your fetch all records query to fetch a single record. We've supply the variable `{{id}}` to represent your primary key.
[block:callout]
{
  "type": "info",
  "title": "Query must return results",
  "body": "In order for us to analyze the results of your query, it must return at least one result."
}
[/block]

[block:api-header]
{
  "title": "Using a separate query for updates"
}
[/block]
If you want to use a different query to keep your tasks in Sync, select `Use a separate query for subsequent updates` and input your query. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1be9ed7-Separate_update_query.png",
        "Separate update query.png",
        670,
        437,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Mapping columns to fields"
}
[/block]
Press continue and we will now run your query. When it's completed you will have to confirm the columns to field mapping. You will have the choice of selecting an existing field or creating a new one.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9a303c-map-fields.png",
        "map-fields.png",
        1155,
        1422,
        "#fbfbfb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Sync Settings"
}
[/block]
Below you will have the option to configure how often the data sync will query your database.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e8241a-sync-settings.png",
        "sync-settings.png",
        385,
        152,
        "#f6f7f7"
      ],
      "border": true
    }
  ]
}
[/block]