---
title: Keeping your database up to date
permalink: /docs/data-sync/keeping-your-database-up-to-date
parent: Data Sync
nav_order: 2
---
After setting up Data Sync, you can configure Flowdash to write Field changes to your database.

To enable updates, on the Sync Settings step, there is an Editable column for each field. Once you allow fields to be
editable, we will ask for an update query.

This update query will be run when any of the editable fields are modified.

Please be careful to scope the update query by using the Unique ID column.

![](/assets/images/1c96631-updates.png)

{: .info-title }
> Note
> 
> Update requires the user in the data source to have write access to the table

## Writing to a separate database

If you're using a read-only connection, you can add another data source with write credentials. We'll only use this
connection to write updates. When any field is editable, select the database you want to write to. The default is the
database that is being read.

![](/assets/images/ece95bb-updating_separate_database.png)

## Issuing updates to your database

After setting this up, keeping your database and Flowdash is all done behind the scenes. If you want to edit a field
that is synced from your database, all you have to do is Edit and change the field on the Details Table.

We will always issue the update query and ensure the changes have been committed before showing the update within
Flowdash.

{: .danger-title }
> Do not sync columns that can be updated by database triggers
> 
> We utilize the single record query to verify the update query was successful. If you provide a column that is
updated by database triggers like `updated_at`, that will cause your database and the Flowdash to drift and requires you
to manually sync.

![](/assets/images/439394c-editing-details-table.png)
