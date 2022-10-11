---
title: Workspace API
permalink: /docs/api/workspace-api
nav_order: 12
parent: API Reference
---
## GET Workspace

To fetch workspace details for a given workspace API token, issue a GET request to the workspace endpoint:

```
https://app.flowdash.com/api/v1/workspace
```

For example,

```
curl https://app.flowdash.com/api/v1/workspace \
    --header 'Authorization: Bearer YOUR_API_TOKEN'
```

Example response
```json
{
   "id" : "123abc",
   "name" : "Acme Corp. Workspace"
}
```
