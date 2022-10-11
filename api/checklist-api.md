---
title: Checklist API
permalink: /docs/api/checklist-api
nav_order: 2
parent: API Reference
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

|Field Name|Description|
|--- |--- |
|id|Unique identifier for the checklist item|
|title|The title for the checklist item|
|status|Can be one of "Blank", "Skipped", or "Completed"|
|editable|Whether the checklist item can be modified/deleted. Checklist items created from a checklist template cannot be deleted and will return false|
|Assigned To|The user's email that the checklist item is assigned to, or null if unassigned|
|Stage|The stage on which the checklist item will be shown|

{: .info-title }
> Filtering checklist items by stage
> 
> To only return checklist items for a given stage, you can include an optional **Stage** query parameter. For example:
> 
> GET /api/v1/workflows/\<workflow-id\>/tasks/\<unique-id\>/checklist_items?Stage=School%20Supplies

## GET Checklist Item

You can fetch an individual checklist item from the API by specifying its unique `id`:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/<unique_id>/checklist_items/<id>
```

## POST Create checklist item

To create a new checklist item, include the checklist item's title and the stage it should appear on as the body of a
POST request. All other fields are optional.

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

{: .warning-title }
> Some checklist items cannot be deleted
> 
> Checklist items added via the a checklist template cannot be deleted.
