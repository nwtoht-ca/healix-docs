---
sidebar_position: 2
---

# Healix Expression Grammar

Healix includes a programming language like grammar for defining calculations.  

This is very similar in concept to formulas in Microsoft Excel or Google Sheets.  In these spreadsheets, data is pulled from a matrix, where A1 is the upper left cell of a sheet, and B1 is the cell to A1's right.  To add these to cells together you can enter ``` A1 + B1 ```.

In Healix, all the data is in forms or are attributes of a plan.  As discussed in [Data References](./referencing-data), in Healix you can use ```submission.form1.field1``` to reference a field called ```field1``` for a form called ```form1```.

However, a form can be submitted multiple times. So we need a way to identify which submission to use.  This is where functions come in. One of the most commonly used functions is ```lastVal```.  ```lastVal``` tells the expression interpreter that we want the "last value", or the one that was submitted most recently.  So

```
lastVal("submission.form1.field1")
```
returns the last value of field1 in form1 that was submitted.

## Calculation Contexts

When a calculation is executed it has access to certain data, depending on where it is run from.

For example, if a form submission is in context, the fields from the submitted form are in context and do not need to be qualified by the entity and form levels.   For example:

```
submissionVal("field1")
````
returns the value of "field1", but this only works in contexts where the system knows which form you are referencing.  For example, defining a [View](/creating-plans/presentation/views) for a submission.




