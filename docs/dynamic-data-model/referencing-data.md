---
sidebar_position: 1
---

# Data References

To reference data, names for levels are separated by ``` . ``` are used when functions need coordinates for a data point.  For example: 

```
entity.category.field
```

## Entities
Entity is the highest level of categorization for data. Two entities currently exist

* **submission** - any form or rule derived data
* **carePlan** - hard coded care plan attributes (e.g. start date)

## Categories
Each Entity can optionally define a second level
In the case of *submission*, category is the form name

## Fields 

A field is defined by a name and type information

## Examples

For example, to get a field named "field1" from a form named "form1":

```
submission.form1.field1
```

Or to read the status of a plan:

```
carePlan.status
```

These data references are used by by *[Healix Expression Grammar](/docs/dynamic-data-model/healix-calculation-grammar)* discussed next.

