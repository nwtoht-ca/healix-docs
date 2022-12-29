---
sidebar_position: 10
---

# Healix Roadmap

## Creating Templates
### Roles Improvements
#### Role visibility
* The current role visibility impacts all users.  We intend to allow a content manager to define how any given role can view another. (E.g. a Patient Supporter's contact details may be visible to Providers by hidden to patients, opposed to hidden to all)
### Forms Improvements
#### Template Scoped Forms
* Currently forms exist in a global space, meaning any plan template can reference an individual form.  We are changing this so that a form's scope is limited to the current template.  This means that you edit the forms within the template editor and editing a form cannot inadvertently break other templates.
### Rules Improvements

#### More than one Action

Currently a row on the decision table leads to only one action.  This causes unnecessary duplication when a content manager wants to create many actions based on the same criteria.  We will add the ability to create multiple actions.

#### Decision Tree Editor

The current decision table offers the maximum flexibility to express any arbitrary set of conditions and will remain a key component to definition rules. However, understanding, visualizing and maintaining rules with multiple conditions becomes unwieldy.  To address this we will add a decision tree editor which will present a tree like decision structure.

#### Calculated Columns

In order to expand the flexibility of the rules editor, we plan to allow [Healix Expression Grammar](/docs/dynamic-data-model/healix-calculation-grammar) calculated columns to be added as column types.

#### Rules Action Audit and Debugger

Each event and corresponding action that the rules engine executes is stored.  We will expose this to administrators and content managers for additional transparency and debugging capability.

### Units of Measure

We plan to expand the concept of Unit of Measure used for charts.  This will allow the same Unit of Measure to be referenced by many form fields.  As well, we plan to leverage Units of Measure to provide charts and dashboards that aggregate multiple plans.

### Test Automation Improvements

* Complete additional test types (expressions, external notifications)
* Improve documentation generation.  Each test case can generate a document describing the pathway case including screenshots.  This is useful for documenting the plan
* Known-to-be-correct Screenshots can be compared to the plan being tested.  When a difference is spotted, users running the test can accept the new version or flag it is as a test failure

