---
title: Data Syncs API
permalink: /docs/api/data-syncs-api
nav_order: 4
parent: API Reference
---
## POST Trigger a Data Sync

To trigger the data sync of a workflow, issue a POST request to the data syncs endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/data_syncs
```

With a valid workspace API key included in the Authorization header:

```
Authorization: Bearer YOUR_API_KEY
```
