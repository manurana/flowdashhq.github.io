---
title: Front
permalink: /docs/integrations/front
parent: Integrations
nav_order: 2
redirect_from:
- /docs/connect-to-front
---
Time to stop jumping between Flowdash and Front. Now you can view all your conversations _and_ task data in one place
with the Front block.

If you're using Front for team communications, render email conversations based on tags and other filters in your task
view.

## How to set it up

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/rdW3oTnbiWY" title="YouTube video player"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen></iframe>

1. Navigate to the `Layout` tab in the workflow you want to render Front conversations in.
2. Grab the Front block and drag it into the task layout.

3. Sign into Front and create a new API
   key [https://app.frontapp.com/settings/tools/api](https://app.frontapp.com/settings/tools/api). Call it `flowdash`
   and give it the proper scopes. Copy it to your clipboard for the next step.

4. Go to the right side panel and **paste your API key** + configure which conversations you'd like to render.

Commonly, users interpolate an email field value for `Email` (`{{ "{{Contact Email"}}}}` in the example below). You may
also interpolate a list of conversation IDs from Front and/or specify Front tags.

That's it!
View all your conversations at a glance or click on one to dive deeper.

![](/assets/images/16c5642-Screen_Shot_2021-12-15_at_5.54.20_PM.png)
