---
sidebar_position: 3
---

# Dynamic Data Model

As forms and custom fields are added to a plan, a *Dynamic Data Model* is created based on the [form](/docs/creating-plans/forms-and-fields/form-editor) and field names.  A plan has a number of fixed fields and [Content Managers](/docs/using-healix/user-types#content-manager) can add new plan fields with [Custom Fields](/docs/creating-plans/forms-and-fields/custom-fields).

## Data Model Levels Components
### Entities
Entity is the highest level of categorization for data. Two entities currently exist

* **submission** - any form or rule derived data
* **carePlan** - hard coded care plan attributes (e.g. start date)

### Categories
Each Entity can optionally define a second level
In the case of *submission*, category is the form name

### Fields 

A field is defined by a name and type information
