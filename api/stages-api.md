---
title: Stages API
permalink: /docs/api/stages-api
nav_order: 8
parent: API Reference
---
## GET List Stages

To fetch the stages for a given workflow, issue a GET request to the stages endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/stages
```

For example,

```
curl https://app.flowdash.com/api/v1/workflows/<workflow-id>/stages \
    --header 'Authorization: Bearer YOUR_API_KEY'
```

Example response
```json
[
   {
      "name" : "Not Started"
   },
   {
      "name" : "In Progress"
   },
   {
      "name" : "Done"
   }
]
```
