---
title: Actions API
permalink: /docs/api/actions-api
nav_order: 1
parent: API Reference
---
You can use the Actions API to fetch the currently available actions for a given task, execute one of those actions (an
action "execution"), and retrieve the status of that execution . Optionally, you may pass a user who is performing this
action -- if so, they will need appropriate permissions.

## GET List a Task's Available Actions

```
GET /api/v1/workflows/<workflow-id>/tasks/<unique-id>/actions
```

For example,

```bash
curl https://app.flowdash.com/api/v1/workflows/abc123/tasks/678/actions \
    --header 'Authorization: Bearer YOUR_API_KEY'
````

Example response

```json
[
  {
    "id": "edHR10",
    "name": "Approve"
  },
  {
    "id": "PvHaOO",
    "name": "Reject"
  }
]
```

## POST Create an Action Execution

```
POST /api/v1/workflows/<workflow-id>/executions
```

To execute a task's available action, issue a POST request to the executions resource, specifying the task's unique ID,
the ID of the action you wish to execute, and (optionally) the email of the user who is performing the action (*they
will need appropriate permissions*).

Action executions run **asynchronously**, so the response will include the execution ID and a status. If you would like
to track the status of the execution, you will need to poll (using the GET execution by ID endpoint) as the execution
runs.

{: .info-title }
> Note
> 
> **All action requirements are respected by this API**, as they are in the user interface, except for the user 
> confirmation requirement. For example, if a task has a "Name" required field, POSTing to this endpoint when the task 
> has a blank "Name" will return a 422 status code and an error message. See the example below.

For example,

```bash
curl -X POST https://app.flowdash.com/api/v1/workflows/abc123/executions \
    --header 'Authorization: Bearer YOUR_API_KEY' \
    --header 'Content-Type: application/json' \
    --data '{
          "task_id":"678",
          "action_id":"edHR10",
          "performed_by":"harry@hogwarts.edu",
    }'
```

Example response (2xx)

```json
{
  "id": "091has",
  "status": "Pending"
}
```

Example response when missing requirements (422)

```json
{
  "status": "Fail",
  "errors": [
    "Name is required",
    "Checklist must be completed",
    "Must be assigned",
    "Name must include honorable prefix" // custom condition requirement
  ]
}
```

## GET Action Execution Status

```
GET /api/v1/workflows/<workflow-id>/executions/<execution-id>
```

To retrieve the status of an executed action (typically when you are polling for status updates as the execution runs
asynchronously), use the execution ID returned by the POST request to create the execution.

Example request

```bash
curl https://app.flowdash.com/api/v1/workflows/abc123/executions/091has \
    --header 'Authorization: Bearer YOUR_API_KEY'
```

Example response

```json
{
  "id": "091has",
  "status": "Success"
}
```

Execution statuses: `"Pending", "Success", "Fail"`. When the status is "Fail", there will be an additional "errors" key
in the response body, specifying the error returned by the step that failed in the execution.

```json
{
  "id": "091has",
  "status": "Fail",
  "errors": [
    "foo is not a valid email"
  ]
}
```
