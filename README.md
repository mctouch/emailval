# emailval
Custom validation
There are 2 ways to validate a field:

By checking the field value with callback function validate - use this when you want to simply check the validity on input (but note that it does not get triggered on form submit)
By setting the "valid" state directly - use this when you need to validate the entire form, so you keep the value in local state

Checking the field value with callback function "validate"
Option validate is a function that accepts the current field value and is called on every oninput. Return an object with attributes valid (Boolean) and error (message string):

m(TextField, {
  validate: value => {
    if (value !== value.toLowerCase()) {
      return {
        valid: false,
        error: "Only use lowercase characters."
      }
    }
  }
})