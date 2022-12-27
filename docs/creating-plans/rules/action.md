---
sidebar_position: 4
---
# Action

The Action column defines what happens when the rule triggers.  When the action button is clicked, a dialog is displayed.

**Intervention Protocol** - When *Intervention Protocol* is selected, a Form Assignment that was configured to be assigned by a rule must be selected in the drop down.

![Action - Intervention Protocol](img/action-ip.png)

**Add Data Point** - When *Add Data Point* is selected, you must specify which field is to be changed and enter a [Healix Expression Grammar](/docs/dynamic-data-model/healix-calculation-grammar) to compute its value.

![Action - Add Data Point](img/action-data-point.png)

 * Set - You may select any field that at the plan level that you are allowed to compute or any [Custom Field](/docs/creating-plans/forms-and-fields/custom-fields) that you have defined.  You may set the following predefined fields
   * Status - This can only be set to OPEN or CLOSED
   * Risk Status
   * End Date
   * Start Date
 * Expression - Enter a [Healix Expression Grammar](/docs/dynamic-data-model/healix-calculation-grammar) for the computed value.  This can be as simple as a value.  Numbers and booleans do not need quotes.  Text strings do.




