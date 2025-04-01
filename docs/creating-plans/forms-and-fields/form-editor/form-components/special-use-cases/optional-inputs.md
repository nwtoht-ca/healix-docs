# Optional Inputs
By "Optional" is meant that the user is required to fill one of two input fields. (for the custom "Verify phone/email" component, see [this article](../advanced/verify).)

For this to work, validation must be done in the "Custom Validation" field of the component _not_ using any of the other validation options. The basic code is as follows:
`````
var otherKey = 'phone'
var otherData = data[otherKey];
var otherOk = data[otherKey].length > 0;
var thisOk = input.length > 5 && input.length < 50;
valid = otherOk ? true : thisOk ? true :'please enter a valid email address'
`````
This handles only the simplest validation — “Required”. As long as the user enters anything at all in the other field _or_ text 
between 5 and 50 characters in the current field, the validation passes. If neither is true, the error message is displayed.
