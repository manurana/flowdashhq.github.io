---
title: Key Concepts
permalink: /docs/creating-workflows/key-concepts
parent: Creating Workflows
nav_order: 0
---

## Stages

A workflow is made up of multiple **stages**. You can think of a task's stage as the high-level status of where the task
is in your workflow. For example, if you're building a workflow to approve budget requests, your stages might
be `Needs Review`, `Under Review`, `Approved`, or `Rejected`.

## Actions

At any given stage, users of your workflow can perform one or more **actions**. An action is a sequence of steps that
should be executed on the user's behalf. In its simplest form, an action might simply update the task's stage (for
example, an `Approve` action might update the stage from `Under Review` to `Approved`). In more advanced use cases, you
can configure actions to do much more, such as sending a email or Slack message, or calling an API.
