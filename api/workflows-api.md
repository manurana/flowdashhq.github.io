---
title: Workflows API
permalink: /docs/api/workflows-api
nav_order: 11
parent: API Reference
---
## GET List Workflows

To fetch workflows accessible to a given workspace API token, issue a GET request to the workflows endpoint:

```
https://app.flowdash.com/api/v1/workflows
```

For example,

```
curl https://app.flowdash.com/api/v1/workflows \
    --header 'Authorization: Bearer YOUR_API_TOKEN'
```

Example response
```json
[
   {
      "id" : "123abc",
      "name" : "Document Approval"
   },
   {
      "id" : "456def",
      "name" : "Bug Tracker"
   }
]
```
