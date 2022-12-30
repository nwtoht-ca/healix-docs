---
sidebar_position: 1
---

# Form Editor

Creating forms is done at the top level.  Note that soon creating forms will be integrated into the Plan Template editor.

**[form.io](https://form.io)** Editing and Displaying forms is done by using  source components [formio.js](https://github.com/formio/formio.js).  Healix wraps the core form feature and customizes it by adding new components and features.

After you create or edit a form the Form Editor is displayed.

![Form Editor](img/form-editor.png)

**Form Name** - The Form Name is the identifier of the form and should not contain spaces or special characters.

**Type** - Types help categorize the form for easy searching.  Choose from *Form*, *Education* or *Tracker*.

**Display Name** - The text that is displayed on default [Task Cards](/docs/glossary#task-card) and when the form appears on lists

**Display** - Choose *Form* for a standard form or *Wizard* for a form that is broken into pages

**Referenced Forms** - Select forms that will be referenced.

**Status** - IN_REVIEW status forms will only be used in the [Simulator](/docs/creating-plans/simulator/).  ACTIVE status will be used by real users.  As well as changing the status here, the status is also changed when a template that references the form is published (i.e. changing a templates status to ACTIVE also changes any referenced forms to ACTIVE)

**Auto Save** - If this is set to true, then each time the user leaves a field, the field is saved on the server.  This allows them to finish the form at a later time.

**Form.io Editor** - the remaining contents is the core form editor from form.io. See [Core Form Editor](form-io-editor) for details.




