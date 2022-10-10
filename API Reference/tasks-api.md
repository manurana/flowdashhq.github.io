---
title: "Tasks API"
slug: "tasks-api"
excerpt: "Read, create, or update tasks in a given workflow."
hidden: false
createdAt: "2021-06-21T23:13:57.487Z"
updatedAt: "2022-04-07T17:21:54.758Z"
---
[block:callout]
{
  "type": "info",
  "title": "A note on Unique IDs",
  "body": "Flowdash allows you to optionally designate one field in your workflow as a Unique ID. If a Unique ID field is defined, Flowdash will ensure that no two tasks are created with the same value for that field. In our example, we've designated Company ID as a unique ID."
}
[/block]
## GET List Tasks

To fetch existing tasks from a workflow, simply issue a GET request to the workflow's `tasks` endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks
```

As with all endpoints, make sure to include a valid workspace API key in the request's Authorization header. For more details on obtaining your API key, see the [Authorization](doc:authorization) section.

```
Authorization: Bearer YOUR_API_KEY
```

You can obtain the `workflow-id` from your workflow's URL:


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6546959-workflow-url.png",
        "workflow-url.png",
        1176,
        808,
        "#dee0e3"
      ]
    }
  ]
}
[/block]
A sample response might look like:

```json
[
    {
        "Stage": "In Progress",
        "Assigned To": null,
        "Task URL": "https://app.flowdash.com/workflows/2ylSaZ/tasks/ooCwnZ",
        "Company ID": "42",
        "Company Name": "Acme Corp",
        "Number of Employees": "10",
        "Contract Value": "10000.00",
        "Expected Close Date": "2020-01-31",
        "International?": false
    },
    {
        "Stage": "Not Started",
        "Assigned To": null,
        "Task URL": "https://app.flowdash.com/workflows/2ylSaZ/tasks/gqCQRO",
        "Company ID": "43",
        "Company Name": "XYZ Inc.",
        "Number of Employees": "300",
        "Contract Value": "500000.00",
        "Expected Close Date": "2020-03-31",
        "International?": true
    }
]
```

### Active Tasks

To fetch active tasks (tasks not in an end stage), use the following endpoint:
```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/active
```


### Filters

You can also filter tasks based on their stage, who they're assigned to, or any other field. For example, let's say we wanted to fetch all tasks that are unassigned and in the Not Started stage:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks?Assigned%20To=&Stage=Not%20Started
```

Following from our example above, this would return:

```json
[
    {
        "Stage": "Not Started",
        "Assigned To": null,
        "Task URL": "https://app.flowdash.com/workflows/2ylSaZ/tasks/ooCwnZ",
        "Company ID": "43",
        "Company Name": "XYZ Inc.",
        "Number of Employees": "300",
        "Contract Value": "500000.00",
        "Expected Close Date": "2020-03-31",
        "International?": true
    }
]
```

Similarly, we can fetch all tasks that are In Progress and have a Company ID of 42:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks?Stage=In%20Progress&Company%20ID=42
```

This would return:

```json
[
    {
        "Stage": "In Progress",
        "Assigned To": null,
        "Task URL": "https://app.flowdash.com/workflows/2ylSaZ/tasks/ooCwnZ",
        "Company ID": "42",
        "Company Name": "Acme Corp",
        "Number of Employees": "10",
        "Contract Value": "10000.00",
        "Expected Close Date": "2020-01-31",
        "International?": false
    }
]
```
[block:callout]
{
  "type": "info",
  "title": "Linked Tasks",
  "body": "Linked tasks are also included in the response. For more information, see [Working with Linked Tasks](https://docs.flowdash.com/docs/working-with-linked-tasks)."
}
[/block]
### Reading File Attachments

File fields are also returned via the API. For example, if we had a File Attachment field called "Documents" with two files attached, the API response would look something like:

```json
[
    {
        "Documents": [{
            "blobId": "abc123...",
            "contentType": "application/pdf",
            "filename": "resume.pdf"
        }, {
            "blobId": "def456...",
            "contentType": "image/jpeg",
            "filename": "photo.jpg"
        }],
        ...
    }
]
```

You can download the actual file contents with the [Files API](doc:files-api).

## GET Task by Unique ID

To fetch a task by unique ID, simply issue a GET request to the tasks endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/<unique-id>
```

A sample response might look like:

```json

{
    "Stage": "In Progress",
    "Assigned To": null,
    "Task URL": "https://app.flowdash.com/workflows/2ylSaZ/tasks/ooCwnZ",
    "Company ID": "42",
    "Company Name": "Acme Corp",
    "Number of Employees": "10",
    "Contract Value": "10000.00",
    "Expected Close Date": "2020-01-31",
    "International?": false
}
```

## POST / PUT Task
### Creating a new task

1. Log into Flowdash and open the workflow you'd like to add tasks to.
2. Click the arrow next to the **New Task** button, then click the **Import from API** option in the dropdown.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a59674a-import-from-api.png",
        "import-from-api.png",
        1176,
        734,
        "#dddee1"
      ]
    }
  ]
}
[/block]
3. You'll be redirected to the workflow's API settings page, which includes an example cURL request for creating tasks. The example includes a sample payload that reflects your workflow's schema.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9a412c1-Sample_API_Payload.png",
        "Sample API Payload.png",
        2560,
        1018,
        "#e4e5e5"
      ]
    }
  ]
}
[/block]
In addition to the fields above you can also set the Stage and Assigned To. The Stage should be a string matching any of the stages defined on the workflow and Assigned To should be the email address of the user you'd like to assign the task to (or null if you'd like the task to be undefined). For example, if I'd like the mark the task as In Progress and assign it to user@example.com, I should include the following attributes in my request payload:

```json
{
    "Stage": "In Progress",
    "Assigned To": "user@example.com"
}
```

4. Adapt the example to your language and framework, change the sample data to real data, and you're ready to go! Here's an example for NodeJS using the Request library:

    ```javascript
    const request = require('request');
    const options = {
      'method': 'POST',
      'url': 'https://app.flowdash.com/api/v1/workflows/RmI4EA/tasks',
      'headers': {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer YOUR-API-KEY'
      },
      body: JSON.stringify({
        "Company ID":"42",
        "Company Name":"Acme Corp",
        "Number of Employees":10,
        "Contract Value":10000,
        "Expected Close Date":"2020-01-31",
        "International?":false,
        "Stage":"In Progress",
        "Assigned To":"user@example.com"
      })
    };
    request(options, function (error, response) { 
      if (error) throw new Error(error);
      console.log(response.body);
    });
    ```
### Response Codes and Body

A 2xx response indicates that the task was successfully created. The response body will include the task data submitted in the request payload, as well as the initial stage of the task. For the request submitted above, the response would be:

```json
{
    "Stage": "In Progress",
    "Assigned To": "user@example.com",
    "Task URL": "https://app.flowdash.com/workflows/2ylSaZ/tasks/ooCwnZ",
    "Company ID": "42",
    "Company Name": "Acme Corp",
    "Number of Employees": "10",
    "Contract Value": "10000",
    "International?": false,
    "Expected Close Date": "2020-01-31"
}
```

A 422 response indicates that invalid data was provided in the request body. The response body will indicate specifically which data was invalid (dates should be in YYYY-MM-DD format). For example, if we try to create a task with an invalid Expected Close Date, we would get a 422 response body with the following body:

```json
{
    "errors": {
        "Expected Close Date": [
            "is invalid"
        ]
    }
}
```

### Updating an existing task

If your workflow includes a Unique ID field, you can use the Flowdash API to update an existing task in addition to creating new tasks. Simply include the unique id field in your request body and Flowdash will update the existing task instead of creating a new one. If no existing task with the specified unique id is found, a new task will be created.

For example, if we'd like to update the Number of Employees in the example above from 10 to 20, we can issue a POST request to the same endpoint with the following request body:

```json
{
  "Company ID": "42",
  "Number of Employees": "20"
}
```

You can also update the built-in Stage and Assigned To fields:

```json
{
  "Company ID": "42",
  "Assigned To": "user@example.com",
  "Stage": "In Progress"
}
```

Similar to creating a task, a response code of 2xx indicates success and the response will include all fields of the given task. A 422 response indicates invalid data and the response body will provide more details about the specific error.
[block:callout]
{
  "type": "warning",
  "title": "POST vs. PUT",
  "body": "You can update existing tasks with either an HTTP POST or PUT, with one subtle difference.\n\nIn our tasks API, POST follows *upsert* semantics. That means that if a task with the specified unique id already exists, it will update that task. However, if the task does not exist, it will create a new one.\n\nOn the other hand, PUT follows *update* semantics. That means that, like POST, if a task with the specified unique id already exists, it will update that task. However, if the task does not exist, the request will fail and the API will return a 404."
}
[/block]
### Updating File Attachments

File attachments can be added and removed via the API. Let's say we had a "Documents" field with the following attachment:

```json
[
    {
        "Documents": [{
            "blobId": "abc123...",
            "contentType": "application/pdf",
            "filename": "resume.pdf"
        }],
        ...
    }
]
```

To remove a file attachment, omit it from the request payload:

```json
[
    {
        "Documents": [],
        ...
    }
]
```

To upload a new file, we can add an entry to the "Documents" field and encode the file data using Base64 or a remote downloadable url. For example:

#### Base64

```json
[
    {
        "Documents": [{
            "contentType": "text/plain",
            "filename": "hello.txt",
            "base64contents": "aGVsbG8sIHdvcmxkIQ==",
        }],
        ...
    }
]
```

#### Remote URL

(filename is optional)

```json
[
    {
        "Documents": [{
            "filename": "company-logo.png",
            "remoteUrl": "https://flowdash-assets.s3.us-west-1.amazonaws.com/logo/logo.png",
        }],
        ...
    }
]
```

## DELETE Task by Unique ID

If your workflow has a unique ID field, you can delete a task by unique ID by issuing a DELETE request to the tasks endpoint:

```
DELETE https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks/<unique-id>
```

If the delete is successful, the endpoint will return a `204` response code.
[block:callout]
{
  "type": "warning",
  "title": "Deleting tasks is permanent!",
  "body": "Be careful when programmatically deleting tasks. Deleting a task is permanent and cannot be undone."
}
[/block]