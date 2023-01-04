---
sidebar_position: 3
---

# Phone Number

The phone number form component can be used to enter phone numbers in a form.

![Phone Number](img/phonenumber-component.png)

A textfield can be used for general text input that is shorter than a sentence. There are options to define input masks and validations so information can be molded into desired formats

![Phone Number](img/phonenumber-component-2.png)

## Label

The label for this field that will appear next to it.

## Placeholder

The placeholder text that will appear when this field is empty.

## Input Mask

An input mask helps the user with input by ensuring a predefined format. For a phone number field, the input mask defaults to (999) 999-9999.

- 9: numeric
- a: alphabetical
- \*: alphanumeric

Example telephone mask: (999) 999-9999

## Prefix

The text to show before a field. An example is ‘$’ for money

## Suffix

The text to show after a field. An example would be ‘lbs’ for weight.

## Custom CSS Class

A custom CSS class to add to this component. You may add multiple class names separated by a space.

## Tab Index

Sets the tabindex attribute of this component to override the tab order of the form. See the MDN documentation on tabindex for more information on how it works.

## Multiple Values

If checked, multiple values can be added in this field. The values will appear as an array in the API and an “Add Another” button will be visible on the field.

## Unique

If checked, this field will be enforced as unique for this form. Submissions will be checked to see if an existing value matches. This validation is currently server side only.

## Protected

If checked, this field is for input only. When being queried by the API it will not appear in the properties and also should not appear in exported data. You won’t be able to see the value on form.io, but it will be stored in database under the hood.

## Persistent

If checked, the field will be stored in the database. If you want a field to not save, uncheck this box. This is useful for fields like password validation that shouldn’t save.

## Table View

If checked, this value will show up in the table view of the submissions list.

![Phone Number](img/phonenumber-component-3.png)

## Required

If checked, the field will be required to have a value.
