*This repository is a mirror of the [component](http://component.io) module [segmentio/validator](http://github.com/segmentio/validator). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/segmentio-validator`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*

# validator

  Validate a value against a set of rules.

## Installation

    $ component install segmentio/validator
    $ npm install segmentio/validator

## Example

```js
var Validator = require('validator');

Validator()
  .rule(required, 'required')
  .rule(isEmail, 'email')
  .validate('test', function (err, valid, context) {
    valid; // false
    context; // "email"
  });
```

## API

### Validator(options)

  Create a new `Validator` with `options`:

    {
      optional: false  // whether return true on empty values
    }

### #rule(fn, [context])

  Add a new rule `fn` to the validator, with an optional `context`.

### #validate(value, callback)

  Validate the given `value`. If the validation fails, the `context` from the associated rule will be passed to the `callback`.

## Probes

  - `validator:<function-name>:start`
  - `validator:<function-name>:end`

## License

  MIT
