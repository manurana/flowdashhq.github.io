---
title: "Checklist API"
slug: "checklist-api"
hidden: false
createdAt: "2022-02-25T22:15:57.539Z"
updatedAt: "2022-02-26T01:04:49.578Z"
---
You can use the checklist API to read, create, update, or delete a task's checklist items.

## GET List Checklist Items

To fetch checklist items for a task in your workflow, issue a GET request to the `checklist_items` endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/<unique_id>/checklist_items
```

For example,

```
curl https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/123/checklist_items \
    --header 'Authorization: Bearer YOUR_API_KEY'
```

Example response
```json
[
    {
        "id": "N7gIDN",
        "title": "Cloak",
        "status": "Completed",
        "editable": false,
        "Assigned To": "harry@hogwarts.com",
        "Stage": "School Supplies"
    },
    {
        "id": "xqkIg6",
        "title": "Nimbus 2000 broomstick",
        "status": "Skipped",
        "editable": false,
        "Assigned To": "harry@hogwarts.com",
        "Stage": "School Supplies"
    },
    {
        "id": "6JZId6",
        "title": "Bertie Botts every flavor beans",
        "status": "Blank",
        "editable": true,
        "Assigned To": null,
        "Stage": "School Supplies"
    }
]
```

[block:parameters]
{
  "data": {
    "h-0": "Field Name",
    "h-1": "Description",
    "0-0": "**id**",
    "1-0": "**title** ",
    "2-0": "**status** ",
    "3-0": "**editable** ",
    "4-0": "**Assigned To** ",
    "5-0": "**Stage** ",
    "0-1": "Unique identifier for the checklist item",
    "1-1": "The title for the checklist item",
    "2-1": "Can be one of \"Blank\", \"Skipped\", or \"Completed\"",
    "3-1": "Whether the checklist item can be modified/deleted. Checklist items created from a checklist template cannot be deleted and will return `false`",
    "4-1": "The user's email that the checklist item is assigned to, or `null` if unassigned",
    "5-1": "The stage on which the checklist item will be shown"
  },
  "cols": 2,
  "rows": 6
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Filtering checklist items by stage",
  "body": "To only return checklist items for a given stage, you can include an optional **Stage** query parameter. For example:\n\nGET /api/v1/workflows/<workflow-id>/tasks/<unique_id>/checklist_items?Stage=School%20Supplies"
}
[/block]
## GET Checklist Item

You can fetch an individual checklist item from the API by specifying its unique `id`:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/<unique_id>/checklist_items/<id>
```

## POST Create checklist item

To create a new checklist item, include the checklist item's title and the stage it should appear on as the body of a POST request. All other fields are optional.

```
POST /api/v1/workflows/<workflow-id>/tasks/<unique_id>/checklist_items
```

For example, you can POST the following body to add an item to the School Supplies stage:

```json
{
    "Stage": "School Supplies",
    "title": "Wand (Phoenix Tail Core)"
}
```

## PUT Update a checklist item

To update a checklist item, issue a PUT request and include your updates in the request body:
```
PUT /api/v1/workflows/<workflow-id>/tasks/<unique_id>/checklist_items/<id>
```

For example, to set the status to "Completed":
```json
{
  "status": "Completed"
}
```

## DELETE Delete a checklist item

You can delete a checklist item by issuing a DELETE request:
```
DELETE /api/v1/workflows/<workflow-id>/tasks/<unique_id>/checklist_items/<id>
```
[block:callout]
{
  "type": "warning",
  "title": "Some checklist items cannot be deleted",
  "body": "Checklist items added via the a checklist template cannot be deleted."
}
[/block]