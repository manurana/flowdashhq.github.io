---
title: Slack
permalink: /docs/integrations/slack
parent: Integrations
nav_order: 0
redirect_from:
- /docs/connect-to-slack
---
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/quIdzgBRfZY" title="YouTube video player" 
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

Connect Flowdash with your Slack workspace to receive messages in Slack via custom Triggers and/or Steps execute in
Flowdash.

Connect to Slack either from the Workspace Integrations page, or when you're creating a new Step for an Action or
Trigger.

Once connected, choose which channel you want to post the message to in Slack. Then, customize your message by
interpolating values from task data. If you want to receive realtime updates for task data (Stage, Assigned To, and
Updated At), check *Sync basic task details to Slack* in the Slack post modal.

## Connect from the Workspace Settings > Integrations page

1. Navigate to Workspace Settings > Integrations and click Slack.

   ![](/assets/images/bab2ee4-slack-integrations-page.png)

2. Click Connect to Slack and authorize Flowdash to post to the Slack workspace of your choosing.
   
   ![](/assets/images/b8aff4d-slack-integration-connect-popup.png)

3. Once connected, you'll see a "Connected to <your workspace>" notice. Now you can use this connection to post messages
   from Flowdash.

   ![](/assets/images/9575d5d-slack-integration-page-connected.png)

## Create a new Slack post from a workflow Action

1. Select an Action from your workflow in the Workflow Builder UI and click Slack post

   ![](/assets/images/59bc4da-slack-workflow-step-option.png)

2. Select which Slack channel you'd like to post to and customize your message. The message body will not be updated
   after it posts to Slack.

   Optionally select *Sync basic task details to Slack* to receive task field changes in realtime. When any of the
   following change for a task in Flowdash that has a corresponding message in Slack, they will be updated on the Slack
   message as well (without changing the original message): Stage, Assigned To, Updated At.

   ![](/assets/images/47f1884-slack-workflow-modal.png)

3. Once the new Step is saved, you can perform the Action and see the message posted in Slack.
   
   ![](/assets/images/44a8551-slack-integration-message-in-slack.png)
   
4. When the Stage, Assigned To, or Updated At fields change in Flowdash, those changes will be reflected in Slack.

   ![](/assets/images/a88444c-slack-integration-updated-message-in-slack.png)
   
