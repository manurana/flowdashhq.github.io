---
title: Comments API
permalink: /docs/api/comments-api
nav_order: 3
parent: API Reference
---
## GET List Comments

To fetch comments for a task in your workflow, issue a GET request to the comments endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/<unique_id>/comments
```

For example,

```
curl https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/123/comments \
    --header 'Authorization: Bearer YOUR_API_KEY'
```

Example response
```json
[
   {
      "author" : "harry@hogwarts.com",
      "body" : "comment number one!",
      "timestamp" : "2021-06-22T22:39:48Z"
   },
   {
      "author" : "harry@hogwarts.com",
      "body" : "Tagging you for visibility @Ron Weasley",
      "timestamp" : "2021-06-22T22:39:52Z"
   }
]
```

## POST Create Comment

To create a comment, issue a POST request to the comments endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/<unique_id>/comments
```

All comments created via the API will have the author set to "API". You can also mention users by including the `@`
symbol and the user's full name:

Example payload
```json
{
  "body": "@Ron Weasley This is an automated comment posted via API."
}
```
