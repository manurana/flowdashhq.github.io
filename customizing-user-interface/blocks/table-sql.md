---
title: Table (SQL)
permalink: /docs/customizing-user-interface/blocks/table-sql
parent: Blocks
grand_parent: Customizing User Interface
nav_order: 0
---
After you have [connected to a database]({% link data-sync/connecting-to-a-database.md %}), you can use that connection
to display supplementary information inside workflows.

To use a database in your workflow, start with [Customizing the Layout of a Task]({% link
customizing-user-interface/customizing-layout.md %}). In Edit Layout, drag a Table Block from the left menu into to your
layout.

![](/assets/images/24077fa-block-table-sql.png)

Click on your newly created table block to focus the block. On the left menu, under Data, choose Database query from the
Type dropdown. Then you can choose the the database you created under Source.

![](/assets/images/2dc160e-block-edit-sql.png)

Click Edit SQL to open a modal that will allow you to type in your query.

## Filtering queries using task data

When writing your SQL queries, you can interpolate data from your task similar to [Action Steps]({% link
automations/action-steps.md %}). Start by typing `{{ "{{" }}` and that will reveal a dropdown with the available fields
to select from.

![](/assets/images/580f619-sql-queries.png)

If you need to write a query that includes wildcards, you can insert those within the curly brackets

![](/assets/images/a5e9e31-sql-wildcards.png)
