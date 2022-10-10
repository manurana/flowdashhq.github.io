---
title: "Front"
slug: "connect-to-front"
excerpt: "Integrate Flowdash with Front to view conversations and messages in the task layout."
hidden: false
createdAt: "2021-06-11T16:23:42.667Z"
updatedAt: "2022-01-21T19:06:47.482Z"
---
Time to stop jumping between Flowdash and Front. Now you can view all your conversations _and_ task data in one place with the Front block. 

If you're using Front for team communications, render email conversations based on tags and other filters in your task view.


### How to set it up
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FrdW3oTnbiWY%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DrdW3oTnbiWY&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FrdW3oTnbiWY%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=rdW3oTnbiWY",
  "title": "Front Integration | Front",
  "favicon": "https://www.youtube.com/s/desktop/7b8b5af6/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/rdW3oTnbiWY/hqdefault.jpg"
}
[/block]
1. Navigate to the `Layout` tab in the workflow you want to render Front conversations in. 
2. Grab the Front block and drag it into the task layout.

3. Sign into Front and create a new API key https://app.frontapp.com/settings/tools/api. Call it `flowdash` and give it the proper scopes. Copy it to your clipboard for the next step.

4. Go to the right side panel and **paste your API key** + configure which conversations you'd like to render. 

Commonly, users interpolate an email field value for `Email` (`{{Contact Email}}` in the example below). You may also interpolate a list of conversation IDs from Front and/or specify Front tags.



That's it!
View all your conversations at a glance or click on one to dive deeper.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/16c5642-Screen_Shot_2021-12-15_at_5.54.20_PM.png",
        "Screen Shot 2021-12-15 at 5.54.20 PM.png",
        1794,
        786,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]