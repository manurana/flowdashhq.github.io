---
title: "Authorization"
slug: "authorization"
hidden: false
metadata: 
  title: "Authorization | API Reference"
createdAt: "2021-06-21T22:40:57.841Z"
updatedAt: "2021-09-16T18:23:13.801Z"
---
To use any of the endpoints in the Flowdash API, you'll need to provide an API key in each request's Authorization header.

You can create new keys and revoke existing keys from **Workspace Settings > API** 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b346978-API_Keys.png",
        "API Keys.png",
        2292,
        786,
        "#e6e6e6"
      ]
    }
  ]
}
[/block]
To use a token, specify it in your Authorization header (don't forget the "Bearer"):

```
Authorization: Bearer YOUR_API_KEY
```