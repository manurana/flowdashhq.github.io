---
title: "Slack"
slug: "connect-to-slack"
excerpt: "Integrate Flowdash with Slack for customized interactions and realtime updates"
hidden: false
createdAt: "2021-06-07T23:17:09.992Z"
updatedAt: "2022-01-21T19:06:41.797Z"
---
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FquIdzgBRfZY%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DquIdzgBRfZY&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FquIdzgBRfZY%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=quIdzgBRfZY",
  "title": "Slack Integration | Flowdash",
  "favicon": "https://www.youtube.com/s/desktop/7b8b5af6/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/quIdzgBRfZY/hqdefault.jpg"
}
[/block]
Connect Flowdash with your Slack workspace to receive messages in Slack via custom Triggers and/or Steps execute in Flowdash.

Connect to Slack either from the Workspace Integrations page, or when you're creating a new Step for an Action or Trigger.

Once connected, choose which channel you want to post the message to in Slack. Then, customize your message by interpolating values from task data. If you want to receive realtime updates for task data (Stage, Assigned To, and Updated At), check *Sync basic task details to Slack* in the Slack post modal.

## Connect from the Workspace Settings > Integrations page

1. Navigate to Workspace Settings > Integrations and click Slack.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bab2ee4-slack-integrations-page.png",
        "slack-integrations-page.png",
        3436,
        664,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
2. Click Connect to Slack and authorize Flowdash to post to the Slack workspace of your choosing.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b8aff4d-slack-integration-connect-popup.png",
        "slack-integration-connect-popup.png",
        2590,
        2454,
        "#f7f9f8"
      ]
    }
  ]
}
[/block]
3. Once connected, you'll see a "Connected to <your workspace>" notice. Now you can use this connection to post messages from Flowdash.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9575d5d-slack-integration-page-connected.png",
        "slack-integration-page-connected.png",
        2536,
        1104,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
## Create a new Slack post from a workflow Action

1. Select an Action from your workflow in the Workflow Builder UI and click Slack post
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/59bc4da-slack-workflow-step-option.png",
        "slack-workflow-step-option.png",
        794,
        1200,
        "#f7f7f7"
      ]
    }
  ]
}
[/block]
2. Select which Slack channel you'd like to post to and customize your message. The message body will not be updated after it posts to Slack. 

Optionally select *Sync basic task details to Slack* to receive task field changes in realtime. When any of the following change for a task in Flowdash that has a corresponding message in Slack, they will be updated on the Slack message as well (without changing the original message): Stage, Assigned To, Updated At.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47f1884-slack-workflow-modal.png",
        "slack-workflow-modal.png",
        2454,
        1884,
        "#aaadab"
      ]
    }
  ]
}
[/block]
3. Once the new Step is saved, you can perform the Action and see the message posted in Slack,
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/44a8551-slack-integration-message-in-slack.png",
        "slack-integration-message-in-slack.png",
        1134,
        382,
        "#f7f6f6"
      ]
    }
  ]
}
[/block]
4. When the Stage, Assigned To, or Updated At fields change in Flowdash, those changes will be reflected in Slack.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a88444c-slack-integration-updated-message-in-slack.png",
        "slack-integration-updated-message-in-slack.png",
        1134,
        388,
        "#f7f6f7"
      ]
    }
  ]
}
[/block]
See our [privacy policy](https://flowdash.com/privacy).