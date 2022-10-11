---
title: Fields API
permalink: /docs/api/fields-api
nav_order: 5
parent: API Reference
---
## GET List Fields

To fetch fields for a given workflow, issue a GET request to the fields endpoint:

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/fields
```

For example,

```
curl https://app.flowdash.com/api/v1/workflows/<workflow-id>/fields \
    --header 'Authorization: Bearer YOUR_API_TOKEN'
```

Example response
```json
[
   {
      "editable" : true,
      "id" : "oRtbjQ",
      "name" : "Name",
      "required" : false,
      "type" : "text"
   },
   {
      "editable" : true,
      "id" : "W6tOxT",
      "name" : "description",
      "required" : false,
      "type" : "longText"
   },
   {
      "editable" : true,
      "id" : "ajtXY9",
      "name" : "count",
      "required" : false,
      "type" : "number"
   },
   {
      "editable" : true,
      "id" : "Mop39Y",
      "name" : "phone",
      "required" : false,
      "type" : "phone"
   },
   {
      "editable" : true,
      "id" : "Nitj9k",
      "name" : "salary",
      "required" : false,
      "type" : "currency"
   },
   {
      "editable" : true,
      "id" : "XptOZd",
      "name" : "day",
      "required" : false,
      "type" : "date"
   },
   {
      "editable" : true,
      "id" : "J2tp8P",
      "name" : "appointment time",
      "required" : false,
      "type" : "datetime"
   },
   {
      "editable" : true,
      "id" : "Nbrq9p",
      "name" : "manager",
      "required" : false,
      "type" : "person"
   },
   {
      "editable" : true,
      "id" : "gOtlab",
      "name" : "type",
      "options" : [
         "hybrid",
         "remote",
         "office"
      ],
      "required" : false,
      "type" : "singleSelect"
   },
   {
      "editable" : true,
      "id" : "ER0j09k",
      "name" : "tags",
      "options" : [
         "cheap",
         "cool"
      ],
      "required" : false,
      "type" : "multipleSelect"
   },
   {
      "editable" : true,
      "id" : "aptd0a",
      "name" : "is cool?",
      "required" : false,
      "type" : "checkbox"
   },
   {
      "autoincrement" : true,
      "editable" : false,
      "id" : "ertLKX",
      "name" : "ID",
      "required" : false,
      "type" : "uniqueId"
   },
   {
      "editable" : true,
      "id" : "RxapP2",
      "limit" : 2,
      "name" : "attachments",
      "required" : false,
      "type" : "file"
   },
   {
      "editable" : true,
      "id" : "v8thd8",
      "name" : "email",
      "required" : false,
      "type" : "email"
   },
   {
      "editable" : true,
      "id" : "BEt015",
      "name" : "website",
      "required" : false,
      "type" : "url"
   }
]
```

Available types
* text
* longText
* number
* phone
* currency
* date
* datetime
* person
* singleSelect
* multipleSelect
* checkbox
* uniqueId
* file
* email
* url
