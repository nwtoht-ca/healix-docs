# Optional Inputs
By "Optional" is meant that the user is required to fill his choice of one of two input fields. (for the custom "Verify phone/email" component, see [this article](../advanced/verify).)

For this to work, validation must be done in the "Custom Validation" field of the component, _not_ using any of the other validation options.  
Typical code is as follows:
`````
var otherKey = 'phone'
var otherInput = data[otherKey];
var otherOk = otherInput.length > 0;
var thisOk = input.length >= 5 && input.length <= 50;
valid = otherOk ? true : thisOk ? true :'(error message here)'
`````
The “gotcha” is that the code in each component must validate _both_ components. In this example, `otherOk` checks the _other_
component for any value, while `thisOk` checks the current component for a value between 5 and 50 characters in length.  
Lines of code that the CM must adjust are:
* `var otherKey = 'phone'` set 'phone' to the API key of the other component
* `var otherOk = otherInput`… is to be completed with the Javascript expression to validate the other component.
* Likewise, `var thisOk = input`… is to be completed with the Javascript expression to validate this component.
* In the final line, replace `(error message here)` (inside the quote characters!) with the error message to be displayed if this component is invalid. 

In the other component, be sure to swap the validation expressions between `var otherOk` and `var thisOk` (unless of course you are applying the same validations).

#### Types of Validation Expressions:
##### Required
Instead of selecting “Required” use `.length > 0`.
##### Min/Max Length (Text Field)
Instead of selecting “Min/Max Length” use `.length >= 5 && .length <= 50`.
##### Min/Max Value (Number)
To validate a Number component is similar to Text, but dropping `.length`, e.g. `otherOk = otherInput >= 5 && otherInput <= 50;`.
##### Regex (advanced!)
Writing regular expressions can be daunting; there are online tools for writing and testing regular expressions,
and google searches can usually find a regex for most common uses.

For example, to valid an email address with regex, replace the `thisOk` line in the email input component with:
`````
var reg = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
var thisOk =  reg.test(input);
`````
And likewise, in the other component, replace the `otherOk` line.

However, for the most common expected use case - email or phone number - use the custom  [Verify phone/email component](../advanced/verify) instead.
