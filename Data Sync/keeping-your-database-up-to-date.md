---
title: "Keeping your database up to date"
slug: "keeping-your-database-up-to-date"
hidden: false
createdAt: "2021-09-08T05:52:04.186Z"
updatedAt: "2021-12-16T01:49:18.331Z"
---
After setting up Data Sync, you can configure Flowdash to write Field changes to your database.

To enable updates, on the Sync Settings step, there is an Editable column for each field. Once you allow fields to be editable, we will ask for an update query.

This update query will be run when any of the editable fields are modified.

Please be careful to scope the update query by using the Unique ID column.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c96631-updates.png",
        "updates.png",
        1178,
        1323,
        "#fcfcfc"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Update requires the user in the data source to have write access to the table",
  "body": ""
}
[/block]

[block:api-header]
{
  "title": "Writing to a separate database"
}
[/block]
If you're using a read-only connection, you can add another data source with write credentials. We'll only use this connection to write updates. When any field is editable, select the database you want to write to. The default is the database that is being read.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ece95bb-updating_separate_database.png",
        "updating separate database.png",
        984,
        559,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Issuing updates to your database"
}
[/block]
After setting this up, keeping your database and Flowdash is all done behind the scenes. If you want to edit a field that is synced from your database, all you have to do is Edit and change the field on the Details Table.

We will always issue the update query and ensure the changes have been committed before showing the update within Flowdash.
[block:callout]
{
  "type": "danger",
  "title": "Do not sync columns that can be updated by database triggers",
  "body": "We utilize the single record query to verify the update query was successful. If you provide a column that is updated by database triggers like `updated_at`, that will cause your database and the Flowdash to drift and requires you to manually sync."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/439394c-editing-details-table.png",
        "editing-details-table.png",
        1255,
        425,
        "#fbfcfc"
      ],
      "border": true
    }
  ]
}
[/block]