# JSONSchema Changelog

## Master

### Enhancements

- The failing required validation error message is now emitted for each
  individual required validation failure.

  The following JSON Schema would emit two validation failures, one for missing
  property name and the other for missing property price when when an empty
  object was validated.

  ```json
  {
    "required": ["name", "price"]
  }
  ```

### Bug Fixes

- The failing required validation error message incorrectly specified other
  found keys were missing under the case where another missing key validation
  failed.
  [#61](https://github.com/kylef/JSONSchema.swift/issues/61)

## 0.5.0

### Breaking Changes

- Support for Swift <= 4.2 was removed.
- `ValidationResult.Valid` was renamed to `ValidationResult.valid`.

### Enhancements

- Added support for JSON Schema Draft 6 and 7.
- Support for Swift 4 and 5.
- `uri` format is now validated.

### Bug Fixes

- Fixes cases where schemas containing an `enum` with a boolean or number may
  be incorrectly matched against values which are boolean or numbers.

  For example, `{ "enum": [1] }` incorrectly validated with values of `true`
  and vice-versa.

- Added support for referencing parts using escaped `~` and `/`.

## 0.3.0

### Enhancements

- Adds support for Swift 2.2.
- Adds support for Swift Package Manager.
