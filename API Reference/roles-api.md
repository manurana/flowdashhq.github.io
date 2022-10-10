---
title: "Roles API"
slug: "roles-api"
excerpt: "Read roles for a given workflow"
hidden: false
createdAt: "2021-06-21T23:26:57.684Z"
updatedAt: "2021-11-28T16:51:07.862Z"
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