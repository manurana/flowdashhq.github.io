---
title: "Block: Table (SQL)"
slug: "displaying-information-from-your-database"
hidden: false
createdAt: "2021-09-08T06:47:42.690Z"
updatedAt: "2022-01-22T00:10:34.215Z"
---
After you have [connected to a database](doc:connecting-to-a-database), you can use that connection to display supplementary information inside workflows.

To use a database in your workflow, start with [Customizing the Layout of a Task](doc:custom-layout). In Edit Layout, drag a Table Block from the left menu into to your layout.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/24077fa-block-table-sql.png",
        "block-table-sql.png",
        521,
        1520,
        "#f5f6f7"
      ]
    }
  ]
}
[/block]
Click on your newly created table block to focus the block. On the left menu, under Data, choose Database query from the Type dropdown. Then you can choose the the database you created under Source
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2dc160e-block-edit-sql.png",
        "block-edit-sql.png",
        592,
        1560,
        "#f1f3f8"
      ]
    }
  ]
}
[/block]
Click Edit SQL to open a modal that will allow you to type in your query.
[block:api-header]
{
  "title": "Filtering queries using task data"
}
[/block]
When writing your SQL queries, you can interpolate data from your task similar to [Action Steps](doc:action-steps). Start by typing `{{` and that will reveal a dropdown with the available fields to select from.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/580f619-sql-queries.png",
        "sql-queries.png",
        2672,
        1260,
        "#cbcccc"
      ]
    }
  ]
}
[/block]
If you need to write a query that includes wildcards, you can insert those within the curly brackets
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a5e9e31-sql-wildcards.png",
        "sql-wildcards.png",
        2660,
        1220,
        "#cdcecf"
      ]
    }
  ]
}
[/block]