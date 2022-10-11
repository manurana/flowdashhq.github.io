---
title: Zapier
permalink: /docs/integrations/zapier
parent: Integrations
nav_order: 1
redirect_from:
   - /docs/connect-to-zapier
---
By connecting Flowdash and [Zapier](https://zapier.com/apps/flowdash/integrations), you can connect your workflows to
thousands of application you already use and love.

There are two primary ways of integrating Flowdash with Zapier:

1. Create or update tasks in Flowdash using Zapier
2. Trigger a Zap using a Flowdash action

## Creating tasks with the new Flowdash Zapier app

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/b4G684_zWws" title="YouTube video player"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen></iframe>

To create new tasks in Flowdash from Zapier, we'll set up a sample zap, where a new row in a Google Sheet is the trigger
to create a new task in a Flowdash workflow.

First, find the Flowdash app in
Zapier: [https://zapier.com/apps/flowdash/integration](https://zapier.com/apps/flowdash/integration).

For this example, we'll connect Flowdash + Google Sheets.

![](/assets/images/bf603f6-zapier-flowdash-gsheets.png)

Let's connect Google Sheets and select which sheet we want to listen for new rows on.

![](/assets/images/1cd33fd-zapier-flowdash-gsheet-trigger.png)

Now, let's connect to Flowdash. We'll just need an API key that has access to the workflow we care about.

![](/assets/images/daa7a92-zapier-auth.png)

To find your API Key, navigate to your workflow in Flowdash > Data > API, and copy the API key to paste in the Zapier
modal field for API Key.

![](/assets/images/02ba852-flowdash-ats-api-key.png)

Now, select your workflow you'd like to create new tasks in. For this, we'll use the "Applicant Tracker" workflow.

![](/assets/images/96d6077-zapier-select-ats.png)

Once you've chosen your workflow, we can now map values from our Google Sheet to our Applicant Tracker workflow.

![](/assets/images/600e35d-zapier-map-fields.png)

![](/assets/images/5f4d28c-zapier-turn-on.png)

That's it! Once you turn your zap on, new Google Sheet rows will trigger new task creation in Applicant Tracker :)

## Trigger a Zap from an Action

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/APxO4wTAi-4" title="YouTube video player"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen></iframe>

In order to trigger a Zap from Flowdash, we need to connect an Action from the Flow editor to a Zapier `Catch hook`.

1. In Flowdash, from the Flow Builder, add a `Zapier` step to on of our actions:

   ![](/assets/images/b830d5c-zapier-step.png)

2. A modal will open with further instructions:

   ![](/assets/images/29f9b6e-zapier-modal.png)

3. Per the modal's instructions, open Zapier and create a new Zap. Select **Webhooks by Zapier** as the trigger and **
   Catch Hook** as the trigger event.

   ![](/assets/images/fb07b3c-Screen_Shot_2021-02-10_at_3.19.45_PM.png)

4. Zapier will generate a unique Webhook URL that will look something
   like `https://hooks.zapier.com/hooks/catch/12345/abcdef/`. Copy-paste this URL into the modal from step 1.

   ![](/assets/images/f65d60a-zapier-webhooks-url.png)

5. You're ready to go!

   {: .info-title }
   > Testing the trigger
   >
   > To test the integration, you can click `Test Trigger` in Zapier then manually trigger the action in Flowdash using 
   > a test record. You'll notice that all of the task's fields get submitted to Zapier to use with other integrations.
