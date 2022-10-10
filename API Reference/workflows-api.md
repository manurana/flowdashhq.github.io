---
title: "Workflows API"
slug: "workflows-api"
excerpt: "Read workflows accessible to a given workspace API token"
hidden: false
createdAt: "2021-11-28T16:42:31.949Z"
updatedAt: "2021-11-28T16:52:07.407Z"
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