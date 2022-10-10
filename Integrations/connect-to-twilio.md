---
title: "Twilio"
slug: "connect-to-twilio"
excerpt: "Connect your communications hub to with Flowdash to view SMS messages"
hidden: false
createdAt: "2021-12-28T16:56:22.063Z"
updatedAt: "2022-01-21T19:06:53.383Z"
---
If you're using Twilio for customer engagement, this integration is for you. Bring in actionable context to your task details page with the Twilio SMS block. View all your conversations and task data in one place, and stop jumping between apps. 


## Setting up the integration
1. Navigate to `Workspace Settings` > `Integrations`
2. Choose Twilio and follow the instructions provided on the page. 
3. Once you've grabbed your Account SID and Auth Token, you're ready to start using Twilio across your workspace.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84ab2b7-Screen_Shot_2021-12-28_at_10.04.39_AM.png",
        "Screen Shot 2021-12-28 at 10.04.39 AM.png",
        2054,
        986,
        "#f0f6f1"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ced4057-Screen_Shot_2021-12-28_at_10.05.07_AM.png",
        "Screen Shot 2021-12-28 at 10.05.07 AM.png",
        2038,
        1048,
        "#fbfbfb"
      ],
      "caption": "Grab your Account SID and Auth Token to connect in Flowdash"
    }
  ]
}
[/block]
## Twilio SMS Task Block
1. After you've connected the integration, navigate to the Layout tab in the workflow you want to render Twilio SMS conversations in.
2. Grab the Twilio SMS block and drag it into the task layout.
3. In the righthand configuration panel, choose the phone number for which you'd like to view conversations. Commonly, users interpolate a phone field value (e.g., {{Phone}} in the example below).


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb55cfe-Screen_Shot_2021-12-28_at_10.08.07_AM.png",
        "Screen Shot 2021-12-28 at 10.08.07 AM.png",
        1816,
        342,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
That's it!
View all your conversations at a glance.