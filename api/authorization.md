---
title: Authorization
permalink: /docs/api/authorization
nav_order: 0
parent: API Reference
---
To use any of the endpoints in the Flowdash API, you'll need to provide an API key in each request's Authorization
header.

You can create new keys and revoke existing keys from **Workspace Settings > API**

![](/assets/images/b346978-API_Keys.png)

To use a token, specify it in your Authorization header (don't forget the "Bearer"):

```
Authorization: Bearer YOUR_API_KEY
```
