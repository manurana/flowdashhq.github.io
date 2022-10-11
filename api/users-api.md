---
title: Users API
permalink: /docs/api/users-api
nav_order: 10
parent: API Reference
---
## GET List Users

To fetch users in your workflow, issue a GET request the users endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/users
```

For example,

```
curl https://app.flowdash.com/api/v1/workflows/<workflow-id>/users \
    --header 'Authorization: Bearer YOUR_API_KEY'
```

Example response
```json
[
   {
      "saml_user_id" : null,
      "role_id" : "123abc",
      "first_name" : "Harry",
      "email" : "harry@hogwarts.com",
      "last_name" : "Potter",
      "id" : "456def"
   },
   {
      "saml_user_id" : null,
      "role_id" : "abc123",
      "first_name" : "Hermione",
      "email" : "hermione@hogwarts.com",
      "last_name" : "Granger",
      "id" : "def456"
   },   
]
```

## GET User by ID

To fetch a user in your workflow by ID, issue a GET request to the users endpoint, specifying the user ID.

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/users/<user_id>
```

For example,
```
curl https://app.flowdash.com/api/v1/workflows/<workflow-id>/users/456def \
    --header 'Authorization: Bearer YOUR_API_KEY'
```

Example response
```json
{
   "saml_user_id" : null,
   "role_id" : "123abc",
   "first_name" : "Harry",
   "email" : "harry@hogwarts.com",
   "last_name" : "Potter",
   "id" : "456def"
}
```

## DELETE User by ID

To delete a user in your workflow by ID, issue a DELETE request to the users endpoint, specifying the user ID.

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/users/<user_id>
```

For example,
```
curl -X "DELETE" https://app.flowdash.com/api/v1/workflows/<workflow-id>/users/456def \
    --header 'Authorization: Bearer YOUR_API_KEY'
```

The response code will be 204 on success.
