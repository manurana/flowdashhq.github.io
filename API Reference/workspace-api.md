---
title: "Workspace API"
slug: "workspace-api"
excerpt: "Read workspace details for the given workspace API token"
hidden: false
createdAt: "2021-11-28T16:42:56.015Z"
updatedAt: "2021-11-28T16:56:11.103Z"
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