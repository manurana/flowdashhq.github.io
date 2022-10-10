---
title: "Analytics Export API"
slug: "analytics-export-api"
hidden: false
createdAt: "2022-04-21T17:57:33.966Z"
updatedAt: "2022-04-21T22:14:27.319Z"
---
This endpoint allows you to programmatically generate a CSV with the specified start and end dates and a URL to download the CSV. Please follow the [Authorization](doc:authorization) directions to include your Bearer token.

## POST Generate CSV
To start the CSV export, make a POST request to the following endpoint:
```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/analytics/exports
```
Your request must include a JSON body with the parameters `start_date` and `end_date` (inclusive).
```
{ 
  "start_date": "2022-01-01", 
  "end_date": "2022-03-01" 
}
```
### Sample Response
```
{
    "id": <export-id>
}
```

## GET Analytics CSV
After getting the id of the export from the POST endpoint, make a GET request to the following:
```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/analytics/exports/<export-id>
```

The CSV generation is asynchronous,  we will provide a status in the response that can be `Pending`, `Success` or `Fail`.

When it is a success, `file_url` will point you to the csv that was generated. 

### Sample Response
```
{
    "id": <export-id>,
    "status": "Success",
    "file_url": <file-url.csv>
}
```