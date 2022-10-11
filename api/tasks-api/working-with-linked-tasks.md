---
title: Working with Linked Tasks
permalink: /docs/api/tasks-api/working-with-linked-tasks
parent: Tasks API
grand_parent: API Reference
nav_order: 0
---
The Tasks API supports fetching linked tasks. You can also link/unlink existing tasks. Let's say we have two
workflows: `Houses` and `Wizards`. We've linked these workflows together such that a House has many Wizards.

## Fetching linked tasks

Linked tasks are returned via the `GET /tasks` endpoint, under a key matching the name of the relationship. For
one-to-many and many-to-many relationships, the response will be an array. One-to-one and many-to-one relationships will
return an object.

```
https://app.flowdash.com/api/v1/workflows/<workflow-id>/tasks
```

If we fetch the list of houses, the API will return an array of wizards since the relationship is defined as
one-to-many:
```json
[
  {
    "House ID": 1,
    "Name": "Gryffindor",
    "Wizards": [
      {
        "Wizard ID": 1,
        "First Name": "Harry",
        "Last Name": "Potter"
      }, {
        "Wizard ID": 2,
        "First Name": "Hermione",
        "Last Name": "Granger"
      }
    ]
  },
  // ...
]
```

If no wizards are linked, the `Wizards` key will return an empty array `[]`.

On the other hand, if we fetch the list of wizards, the API will return a single object representing the linked house
since the relationship is many-to-one:

```json
[
  {
    "Wizard ID": 1,
    "First Name": "Harry",
    "Last Name": "Potter",
    "House": {
      "House ID": 1,
      "Name": "Gryffindor"
    }
  }
]
```

If no house is linked, the `House` key will return `null`.

To fetch a single task, see the [Tasks API]({% link api/tasks-api/index.md %}#get-task-by-unique-id).

## Linking and unlinking tasks

Tasks can be linked and unlinked through the `POST /tasks` or `PUT /tasks` API.

### Linking tasks

Existing tasks can be linked through either side of the relationship. For example, say we have a new wizard, Ron
Weasley, that we'd like to create and add to Gryffindor. We do do this through `POST /tasks`:

```json
{
  "Wizard ID": 3,
  "First Name": "Ron",
  "Last Name": "Weasley",
  "House": {
    "House ID": 1
  }
}
```

Since the Gryffindor house already exists, we can simply reference it by ID. All properties other than unique ID
specified through the relationship are ignored. If we wanted to instead add Ron to a new house we'd have to (1) create
the house first, then (2) link Ron with that house.

We can also link the new wizard in the other direction, by posting to the Houses workflow:

```json
{
  "House ID": 1,
  "Name": "Gryffindor",
  "Wizards": [
    {
      "Wizard ID": 1
    },
    {
      "Wizard ID": 2
    },
    {
      "Wizard ID": 3
    }
  ]
}
```

This links the wizards with ids 1, 2, and 3 to Gryffindor house.

{: .danger-title }
> Include all ids when updating a one-to-many or many-to-many relationships
> 
> Any ids omitted in the request will be unlinked!

### Updating links

Existing links can be updated in a similar fashion. For example, if Ron were to switch house:

```json
{
  "Wizard ID": 3,
  "First Name": "Ron",
  "Last Name": "Weasley",
  "House": {
    "House ID": 1
  }
}
```

Or, we can also do this from the other direction:

```json
{
  "House ID": 2,
  "Name": "Hufflepuff",
  "Wizards": [
    // ...
    {
      "Wizard ID": 3
    }
  ]
}
```

### Unlinking tasks

Unlinking tasks is similar to linking tasks. If a wizard wants to leave a house, we can simply specify `null` in the
payload:

```json
{
  "Wizard ID": 666,
  "First Name": "Tom",
  "Last Name": "Riddle",
  "House": null
}
```

We can also unlink from the other direction. For example, to remove the wizard with ID=1 from Gryffindor house, we can
simply omit it from the Wizards array:

```json
 {
  "House ID": 1,
  "Name": "Gryffindor",
  "Wizards": [
    {
      "Wizard ID": 2
    },
    {
      "Wizard ID": 3
    }
  ]
}
```

To remove all wizards from a house, pass in an empty array `[]`.
