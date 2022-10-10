---
title: "Linking multiple workflows"
slug: "linking-multiple-workflows"
hidden: false
createdAt: "2021-02-11T19:43:39.349Z"
updatedAt: "2021-12-16T01:52:43.205Z"
---
You can link multiple workflows together to better organize your data. Linked workflows allow you to:
* Define relationships between tables. For example, tying multiple Contacts to a single Account.
* Link disjoint processes across different teams without requiring access to both workflows.
* Automatically create tasks in a workflow in response to events in another workflow.
[block:api-header]
{
  "title": "Linking one workflow to another"
}
[/block]
Let's say we have two workflows, Accounts and Contacts, and we'd like to define a relationship between these workflows such that every account can be tied to multiple contacts. To start, we'll open the Accounts workflow, but this can also be initiated from the Contacts workflow.

Workflow links can be created be found under the **Settings** tab under the **Linked Workflow** section. Click the "New linked workflow" button to get started:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3b9efa5-create-a-new-linked-workflow.png",
        "create-a-new-linked-workflow.png",
        2088,
        966,
        "#e9e8e9"
      ],
      "sizing": "80"
    }
  ]
}
[/block]
This will open the following modal to configure the relationship:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb6a181-new-workflow-link-modal.png",
        "new-workflow-link-modal.png",
        1244,
        1298,
        "#e2eae6"
      ],
      "sizing": "80"
    }
  ]
}
[/block]

The first dropdown allows you to select which workflow to link. In our case, we've selected the **Contacts** workflow. 

**Relationships** - Flowdash supports one-to-one, one-to-many, and many-to-many style relationships. For our example, we've selected a one-to-many relationship since an Account has many Contacts. Note that if we had started from the Contacts.

**Link Name** - This is the name that will appear in the Accounts table, each Account detail page, and the API representing the relationship to the Contacts table. Since it will appear alongside other fields, this name cannot collide with any of your field names.

**Inverse Link Name** - This is similar to Link Name, but on the inverse direction. This name refers to the Account from the Contacts table, so it cannot collide with any of the field names on Contacts.
[block:api-header]
{
  "title": "Linking records"
}
[/block]
Now that the relationship has been defined, let's trying connecting an account to a contact. First, we'll open the details page for an account. The page will now include a new block to display the account's linked contacts:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/367d145-linked-tasks-table.png",
        "linked-tasks-table.png",
        1538,
        952,
        "#fbf8f8"
      ],
      "sizing": "80"
    }
  ]
}
[/block]
If you don't like the default placement of the block or would like to configure how it is displayed, you can [customize the layout](doc:custom-layout). From this block you can:
* Create a new contact linked to this account
* Link existing contacts to this account
* Unlink the contact from this account
* Click the row to navigate to the details page of the contact
* Edit any of the contact's fields
[block:callout]
{
  "type": "info",
  "title": "Linked workflows and permissions",
  "body": "The linked tasks block will not be visible if the current user does not have read access to the linked workflow. This can be helpful to separate visibility across different teams while preserving the relationship."
}
[/block]
If we click one of the rows in the contacts table it will open the details page for that contact. This page will also include a new block to represent the linked account. Since the contacts-to-accounts relationship is many-to-one, it displays as a details block instead of a table:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/23e07bf-linked-task-block.png",
        "linked-task-block.png",
        1524,
        1084,
        "#fbf8f8"
      ],
      "sizing": "80"
    }
  ]
}
[/block]
From here, you can:
* Open the details page of the linked account
* Edit any of the fields of the account
* Unlink the account
[block:api-header]
{
  "title": "Using linked tasks in actions and automations"
}
[/block]
Linked tasks can also be used in [Actions](doc:actions) and Automations. Namely, you can:
* Create a new linked task, and
* Update existing linked tasks
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e1fc825-linked-task-steps.png",
        "linked-task-steps.png",
        584,
        864,
        "#f8f6f7"
      ],
      "sizing": "original"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "\"I'm not seeing the Create a linked task and Update linked tasks steps\"",
  "body": "These steps will only appear after you've set up a linked workflow."
}
[/block]

[block:api-header]
{
  "title": "API"
}
[/block]
You can also read linked tasks, link existing tasks, or unlink tasks programmatically via our [API](doc:working-with-linked-tasks).