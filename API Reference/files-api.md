---
title: "Files API"
slug: "files-api"
excerpt: "Read a file by its blob ID"
hidden: false
createdAt: "2021-06-21T23:26:50.708Z"
updatedAt: "2021-09-16T23:44:14.382Z"
---
## GET File by ID

To fetch a file in your workflow, issue a GET request to the files endpoint, specifying the blob ID:

```
https://app.flowdash.com/api/v1/files/<blob_id>
```

For example, consider we fetched a task object with the following shape

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
    "International?": false,
    "Receipt": [{
        "blobId": "123abc",
        "filename": "company_outing_receipt.png",
        "contentType": "image/png"
    }],   
}
```

Let's download that file locally with the following command
```
curl https://app.flowdash.com/api/v1/files/123abc \
    --header 'Authorization: Bearer YOUR_API_KEY' \
    --output local_receipt_copy.png
```

The contents of the file should be saved in `local_receipt_copy.png`