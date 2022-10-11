---
title: Action Steps
permalink: /docs/automations/action-steps
parent: Automations
nav_order: 0
---
Actions can be configured to perform steps on your behalf such as assigning a task, sending an email, or calling an API.
To configure an action's steps, first, click the action you'd like to configure. The left sidebar will display the
action's properties such as its name and color, as well as which steps it should perform. To add a new step, you can
click the "New step" link in the left sidebar:

![](/assets/images/2e4a6e6-new-step.png)

## Step Types

Flowdash comes with several steps out of the box to help you orchestrate your team's processes. These steps include:

* **Move to stage** - move the task from one stage to another.
* **Assign to** - assign the task to a specific member of the team (helpful for handoffs, escalations, and manager
  approvals)
* **Update data** - update any of the task's fields with specific values.
* **Delete task** - delete this task
* **Schedule stage change** - Schedule a stage change in a certain amount of days. Useful for re-engagement reminders
* **Slack post** - send a formatted Slack message to a specified channel.
  See [Integrate Flowdash with Slack]({% link integrations/slack.md %})
* **Email notification** - send an email to any number of recipients where the subject line and body can include
  information from the current task.
* **Email a form** - Send an email with a form to allow users to update task data.
  See [Updating tasks with forms]({% link automations/email-a-form.md %})
* **API Call** - call an API and include the current task's data in the request payload. More details in
  our [API Reference for Actions]({% link api/actions.md %})
* **Zapier** - Send a Zapier zap, see [Integrate Flowdash with Zapier]({% link integrations/zapier.md %})
