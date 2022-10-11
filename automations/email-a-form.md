---
title: Email a Form
permalink: /docs/automations/email-a-form
parent: Automations
nav_order: 1
redirect_from:
- /docs/updating-tasks-with-forms
---
Asking for information has gotten easier! You can email a request to anybody for information and their response will be
saved into your task. These forms can only be used to update a task once.

First let's create a form and include the fields that provide relevant contextual information and the information you
want. For example, below I have a form for customers to upload their receipts:

![](/assets/images/a097c18-upload-receipts-form.png)

Now that we have the form users will use, let's add it into our process. In the [Flow Builder]({% link
creating-workflows/accessing-the-flow-builder.md %}) select the action to add the Email a form step

![](/assets/images/fc22301-email-a-form-step.png)

In the modal fill out who should receive this email and if you want to provide them a message.

![](/assets/images/2a51315-email-a-form.png)

{: .info-title }
> Note
>
> Email a form step can also be used in automations!

Save your action with this new step and the next time this action is performed, a form will be sent to the user.
