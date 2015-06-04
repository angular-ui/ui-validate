# AngularUI ui-validate

General-purpose validator for ngModel.
angular.js comes with several built-in validation mechanism for input fields (ngRequired, ngPattern etc.) but using
an arbitrary validation function requires creation of a custom formatters and / or parsers.
The ui-validate directive makes it easy to use any function(s) defined in scope as a validator function(s).
A validator function will trigger validation on both model and input changes.

 @example `<input ui-validate=" 'myValidatorFunction($value)' ">`
 @example `<input ui-validate="{ foo : '$value > anotherModel', bar : 'validateFoo($value)' }">`
 @example `<input ui-validate="{ foo : '$value > anotherModel' }" ui-validate-watch=" 'anotherModel' ">`
 @example `<input ui-validate="{ foo : '$value > anotherModel', bar : 'validateFoo($value)' }" ui-validate-watch=" { foo : 'anotherModel' } ">`

@param ui-validate {string|object literal} If strings is passed it should be a scope's function to be used as a validator.
If an object literal is passed a key denotes a validation error key while a value should be a validator function.
In both cases validator function should take a value to validate as its argument and should return true/false indicating a validation result.
