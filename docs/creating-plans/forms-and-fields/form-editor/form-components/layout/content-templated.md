---
sidebar_position: 3
---

# Content Templating

Templating allows the Content component to display values from previous submissions in a manner similar to the Summary component, with the advantage of inserting values into HTML formatted text.

## Basic
Assuming that a user has submitted their telephone number in another form, e.g. form `onboardingPatient`, in the field `phoneNumber`, you can insert the phone number into the HTML content using the standard Healix Expression Grammar, wrapped inside the characters: `${<formula>}`.

E.g. 'Your phone number is ${lastVal("submission.onboardingPatient.phoneNumber")}.'

## Advanced
The Expression Grammar does not (currently) support Javascript string manipulation. In order to, taking our example use case, display only the last 4 digits of the phone number:
* In the submitting form `onboardingPatient` on the same page (if it's a wizard) as the `phoneNumber` field, add a Text Input component
* on the Display tab, enable "Hidden"
* on the API tab, set the key that you will use for retrieving the 4 digit number, e.g. `last4Digits`
* on the Data tab, in the "Calculated Value" box, enter the Javascript formula: `value = data.phoneNumber.substring(10, 15);`
* on the second form with the Content component, refer to the hidden field instead: `${lastVal("submission.onboardingPatient.last4Digits")}`

**NB** The formula you insert in the Content editor must be plain text. Copy and paste risks including formatting which will crash the server when invoked. If your content looks like this, it's definitely bad!
![screenshot_1428](https://github.com/user-attachments/assets/178e0160-0039-43f6-bd35-0d0e9fd3714d)
