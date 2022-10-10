---
title: "Stages API"
slug: "stages-api"
excerpt: "Read stages for a given workflow"
hidden: false
createdAt: "2021-06-21T23:27:06.891Z"
updatedAt: "2021-09-16T23:45:39.124Z"
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