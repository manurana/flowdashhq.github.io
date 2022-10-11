---
title: Key Concepts
permalink: /docs/working-with-data/key-concepts
parent: Working with Data
nav_order: 0
---

## Fields

**Fields** as similar to columns in a spreadsheet. For example, if we want to capture customer information, we could
create the following fields: `First Name`, `Last Name`, `Email`, `Company`, and `Website`.

When creating fields in Flowdash, along with a name you also need to specify a **data type**.

## Types

When working with data, it's very important to ensure your data remains clean to avoid downstream problems. For example,
capturing an invalid customer `Email` or having a typo when capturing a product `Launch Date` is a sure way to disrupt
business operations. That's where **data types** come in.

A type defines what kind of information should be stored within a field, and provides safeguards when performing data
editing. The following types are currently supported in Flowdash: `Text`, `Long Text`, `Number`, `Phone`, `Currency`
, `Date`, `Date & Time`, `Person`, `Single Select`, `Multiple Select`, `Checkbox`, `Unique ID`, `File Attachment`
, `Email`, `URL`
