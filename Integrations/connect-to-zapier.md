---
title: "Zapier"
slug: "connect-to-zapier"
excerpt: "Integrate Flowdash with thousands of applications using Zapier"
hidden: false
createdAt: "2021-02-10T21:24:23.397Z"
updatedAt: "2022-01-21T19:06:27.929Z"
---
By connecting Flowdash and [Zapier](https://zapier.com/apps/flowdash/integrations), you can connect your workflows to thousands of application you already use and love. 

There are two primary ways of integrating Flowdash with Zapier:

1. Create or update tasks in Flowdash using Zapier
2. Trigger a Zap using a Flowdash action

# Creating tasks with the new Flowdash Zapier app
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2Fb4G684_zWws%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Db4G684_zWws&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2Fb4G684_zWws%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=b4G684_zWws",
  "title": "Create Tasks from Slack using Zapier | Flowdash",
  "favicon": "https://www.youtube.com/s/desktop/7b8b5af6/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/b4G684_zWws/hqdefault.jpg"
}
[/block]
To create new tasks in Flowdash from Zapier, we'll set up a sample zap, where a new row in a Google Sheet is the trigger to create a new task in a Flowdash workflow.

First, find the Flowdash app in Zapier: https://zapier.com/apps/flowdash/integration.

For this example, we'll connect Flowdash + Google Sheets. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bf603f6-zapier-flowdash-gsheets.png",
        "zapier-flowdash-gsheets.png",
        2472,
        1330,
        "#e9eef1"
      ]
    }
  ]
}
[/block]
Let's connect Google Sheets and select which sheet we want to listen for new rows on.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1cd33fd-zapier-flowdash-gsheet-trigger.png",
        "zapier-flowdash-gsheet-trigger.png",
        2236,
        1574,
        "#f8f9fa"
      ]
    }
  ]
}
[/block]
Now, let's connect to Flowdash. We'll just need an API key that has access to the workflow we care about. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/daa7a92-zapier-auth.png",
        "zapier-auth.png",
        2868,
        1678,
        "#edeeef"
      ]
    }
  ]
}
[/block]
To find your API Key, navigate to your workflow in Flowdash > Data > API, and copy the API key to paste in the Zapier modal field for API Key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/02ba852-flowdash-ats-api-key.png",
        "flowdash-ats-api-key.png",
        3570,
        1758,
        "#edeeef"
      ]
    }
  ]
}
[/block]
Now, select your workflow you'd like to create new tasks in. For this, we'll use the "Applicant Tracker" workflow.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/96d6077-zapier-select-ats.png",
        "zapier-select-ats.png",
        1624,
        650,
        "#f7f8f8"
      ]
    }
  ]
}
[/block]
Once you've chosen your workflow, we can now map values from our Google Sheet to our Applicant Tracker workflow.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/600e35d-zapier-map-fields.png",
        "zapier-map-fields.png",
        1450,
        1666,
        "#f3f3f4"
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
        "https://files.readme.io/5f4d28c-zapier-turn-on.png",
        "zapier-turn-on.png",
        1530,
        1084,
        "#f3f4f6"
      ]
    }
  ]
}
[/block]
That's it! Once you turn your zap on, new Google Sheet rows will trigger new task creation in Applicant Tracker :) 


# Trigger a Zap from an action
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FAPxO4wTAi-4%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DAPxO4wTAi-4&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FAPxO4wTAi-4%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=APxO4wTAi-4",
  "title": "Triggering Zaps from Actions & Automations | Flowdash",
  "favicon": "https://www.youtube.com/s/desktop/7b8b5af6/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/APxO4wTAi-4/hqdefault.jpg"
}
[/block]
In order to trigger a Zap from Flowdash, we need to connect an Action from the Flow editor to a Zapier `Catch hook`.

1. In Flowdash, from the Flow Builder, add a `Zapier` step to on of our actions:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b830d5c-zapier-step.png",
        "zapier-step.png",
        524,
        1198,
        "#f7f7f7"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
2. A modal will open with further instructions:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/29f9b6e-zapier-modal.png",
        "zapier-modal.png",
        1942,
        1520,
        "#f0f3f1"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
3. Per the modal's instructions, open Zapier and create a new Zap. Select **Webhooks by Zapier** as the trigger and **Catch Hook** as the trigger event. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fb07b3c-Screen_Shot_2021-02-10_at_3.19.45_PM.png",
        "Screen Shot 2021-02-10 at 3.19.45 PM.png",
        905,
        513,
        "#e6edf9"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
4. Zapier will generate a unique Webhook URL that will look something like `https://hooks.zapier.com/hooks/catch/12345/abcdef/`. Copy-paste this URL into the modal from step 1.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f65d60a-zapier-webhooks-url.png",
        "zapier-webhooks-url.png",
        835,
        153,
        "#f6f6f7"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
5. You're ready to go!
[block:callout]
{
  "type": "info",
  "title": "Testing the trigger",
  "body": "To test the integration, you can click `Test Trigger` in Zapier then manually trigger the action in Flowdash using a test record. You'll notice that all of the task's fields get submitted to Zapier to use with other integrations."
}
[/block]