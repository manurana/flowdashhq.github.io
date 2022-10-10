---
title: "Continuously sync data from your API"
slug: "continously-sync-data-from-your-api"
hidden: true
createdAt: "2021-05-06T01:51:21.263Z"
updatedAt: "2021-05-07T06:45:46.046Z"
---
Flowdash can be configured to continuously sync data from your API. We will poll your API every 5 minutes to ensure data within Flowdash is updated.

In your Workspace Settings, click on Field Sources and connect to an HTTP source
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc4a8e1-connect-to-http-source.png",
        "connect-to-http-source.png",
        984,
        549,
        "#eff0f0"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Response shape",
  "body": "We require your API to respond with an Array."
}
[/block]
To optimize these requests, a Field Source can be configured to pass query/body params for your API with information about which records and fields we need.  
[block:parameters]
{
  "data": {
    "h-0": "Variable",
    "h-1": "Description",
    "0-0": "workflowId",
    "0-1": "The id of the field's workflow",
    "1-0": "ids",
    "1-1": "Records we're trying to update",
    "2-0": "requestedFields",
    "2-1": "Attributes we need from your response",
    "3-0": "idFieldName",
    "3-1": "The field name where ids are derived from"
  },
  "cols": 2,
  "rows": 4
}
[/block]
For example, a GET request with ids `[1,2,3]` requesting for the `email` field will be sent as query params encoded 
[block:code]
{
  "codes": [
    {
      "code": "https://yoursite.com/api/users?ids=%5B%221%22%2C+%222%22%2C+%223%22%5D&fields=%5B%22email%22%5D",
      "language": "text",
      "name": "GET"
    }
  ]
}
[/block]
A post request with the same parameters will be sent as body params
[block:code]
{
  "codes": [
    {
      "code": "https://yoursite.com/api/users\n{\n  \"ids\": [\"1\", \"2\", \"3\"],\n  \"requestedFields\": [\"id\", \"email\"]\n}",
      "language": "text",
      "name": "POST"
    }
  ]
}
[/block]
After a Field Source has been created, now it's time to setup our fields. Start by [creating a field](doc:creating-fields) in your Workflow. Select *Load data from external source* and you'll be presented with new settings. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b500ab-new-options.png",
        "new-options.png",
        288,
        428,
        "#eeeee8"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "External Field types",
  "body": "Currently Fields with a data type of Text, Number, Date and Date & Time can be loaded from an external source."
}
[/block]
Select the field source that was created previously. This is the API Flowdash will call to populate this new Field. External field is the attribute you want to map to this new field.

Now we need to know how to map the tasks in Flowdash to the responses from the API. Select one of the fields to use as an identifier and type in the attribute that represents the same in the API response. 

For example, here we are adding an Email field and we want to make an API call to the Users API. In the response of the Users API, we want the value of email where the users_id (from the Task) matches the id attribute in the response.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dc65cc3-external-field.png",
        "external-field.png",
        305,
        480,
        "#eff6f2"
      ],
      "border": false
    }
  ]
}
[/block]
This is a response we would expect using this example:
[block:code]
{
  "codes": [
    {
      "code": "[\n  { \"id\": \"1\", email: \"richard@piedpiper.com\" },\n  { \"id\": \"2\", email: \"erlich@piedpiper.com\" },\n}",
      "language": "text",
      "name": "response"
    }
  ]
}
[/block]