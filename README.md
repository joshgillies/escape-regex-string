# escape-regex-string
An extremely simple Node module to escape a string literal in preparation for passing to the RegExp constructor.

## Interface
#### escape-regex-string
```javascript
(require('escape-regex-string'))(patternString[, escapeCharsRegex])
```
* patternString String
* escapeCharsRegex Regexp
  * Defaults to value of member escape-regex-string.defaultEscapeCharsRegex (see below)

Returns the passed patternString with all RegExp tokens escaped.
#### escape-regex-string.defaultEscapeCharsRegex
```javascript
(require('escape-regex-string')).defaultEscapeCharsRegex
```
A read-only RegExp instance containing the default pattern used to escape passed strings. If a RegExp instance is manually passed into a function call to this module, the passed RegExp value will be used instead of this default value.

## Example Usage
```javascript
var escapeRegexString = require('escape-regex-string');
var regexString = '$&*()awsd';
var escapedRegexString = escapeRegexString(regexString); // '\\$&\\*\\(\\)awsd'
var regExpObject = new RegExp(escapedRegexString);
console.log(regExpObject); // /\$&\*\(\)awsd/
```

## Feedback
I wrote this miniature module to practice with a few of the tools, libraries, and workflows available to JS developers. I welcome constructive criticism and advice.
