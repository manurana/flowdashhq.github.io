---
title: "Data Syncs API"
slug: "data-syncs-api"
hidden: false
createdAt: "2021-06-25T20:32:09.570Z"
updatedAt: "2021-09-16T23:46:04.090Z"
---
[block:api-header]
{
  "title": "POST Trigger a Data Sync"
}
[/block]
To trigger the data sync of a workflow, issue a POST request to the data syncs endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/data_syncs
```

With a valid workspace API key included in the Authorization header:

```
Authorization: Bearer YOUR_API_KEY
```