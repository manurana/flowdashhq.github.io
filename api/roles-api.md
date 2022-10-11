---
title: Roles API
permalink: /docs/api/roles-api
nav_order: 7
parent: API Reference
---
## GET List Roles

To fetch roles for a given workflow, issue a GET request to the roles endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/roles
```

For example,

```
curl https://app.flowdash.com/api/v1/workflows/<workflow-id>/roles \
    --header 'Authorization: Bearer YOUR_API_TOKEN'
```

Example response
```json
[
   {
      "id" : "123abc",
      "name" : "Administrator",
      "admin" : true
   },
   {
      "id" : "456def",
      "name" : "Collaborator",
      "admin" : false
   }
]
```
