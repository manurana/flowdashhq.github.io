---
title: "Creating a new action"
slug: "creating-a-new-action"
hidden: false
createdAt: "2021-06-21T22:27:27.292Z"
updatedAt: "2021-06-21T22:27:42.751Z"
---
1. First, open the Flow Builder:

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5e9dab09-92ed-4f53-8c03-a1c065673b8a/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5e9dab09-92ed-4f53-8c03-a1c065673b8a/Untitled.png)

2. Next, create a new action, or select an existing action from the canvas. In the screenshot below, **Start** and **Finish** are existing actions:

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/47969225-fff5-4752-9840-0d707be1def8/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/47969225-fff5-4752-9840-0d707be1def8/Untitled.png)

3. In the left sidebar, click the **+ New Step** button and select **API Call** from the dropdown:

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/89196c4f-9fc2-457a-abf3-afb77e0ec883/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/89196c4f-9fc2-457a-abf3-afb77e0ec883/Untitled.png)

4. In the modal that opens, you can specify the URL of your API endpoint as well as any additional headers (for example, authorization headers):

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6116a5a7-b174-46e1-b277-f58a5d21e8a3/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6116a5a7-b174-46e1-b277-f58a5d21e8a3/Untitled.png)

5. Once you're done, click **Apply**, then click **Save** in the left sidebar to commit your changes.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/42a71ee5-a381-4d78-a0f4-4cc2081c5691/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/42a71ee5-a381-4d78-a0f4-4cc2081c5691/Untitled.png)

### Request Payload

When the specified action is performed, Flowdash will call your application at the URL provided and the request body will include the name of the action as well as a JSON representation of the task. Following the example from above, the request body would look like:

```json
{
  "action": "Finish"
  "task": {
    "Stage": "Completed",
    "Assigned To": "user@example.com",
    "Company ID": "42",
    "Company Name": "Acme Corp",
    "Number of Employees": "20",
    "Contract Value": "10000",
    "International?": false,
    "Expected Close Date": "2020-01-31"
  }
}
```

### Response Format

If your application responds with a 2xx code, Flowdash will interpret the API call as successful and move on to the next step in the action. If your application responds with a non-2xx code, Flowdash will abort the action on the current step and alert the user that an error has occurred.

In addition to being able to indicate success/failure, you can also modify the task in your response in the success case. For example, if we wanted to update the Expected Close Date, you could include the following in the response payload.

```json
{
  "task": {
    "Expected Close Date": "2020-02-01"
  }
}
```