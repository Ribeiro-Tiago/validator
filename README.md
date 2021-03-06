# Current avaiable functions
  - [isEmpty](#isempty)
  - [isPositive](#ispositive)
  - [isEven](#iseven)
  - [isArray](#isarray)
  - [isObject](#isobject)
  - [isDOM](#isdom)
  - [isString](#isstring)
  - [isFunction](#isfunction)
  - [isNumber](#isnumber)
  - [isBoolean](#isboolean)
  - [escapeString](#escapestring)
  - [Array.pushUnique](#pushunique)
  - [Array.removeIfExists](#removeifexists)
  - [Date.formatDate](#formatdate)

# Instalation
You can either download (dist/index.js) and include the script to your HTML: ``<script src="path/to/script"></script>`` or ``npm install --save utilities-js``

# Usage
Depending on your development environment and how you import it, you may need to call `` util. `` or use the functions directly. For instance if you're on browser you need to do `` util.isEmpty(value) `` but on react native and node you can import each function seperately:  `` import { isEmpty } from "utilities-js"; `` and then `` isEmpty(value) ``, or import them all, using `` const util = require("utilities-js") `` or `` import * as util from "utilities-js"`` .

Note: As I'm still testing this out on TypeScript, if you're using on TS you need to specify the type on your ``tsconfig.json`` file: 
```json
    "typeRoots": ["./node_modules"],
    "types": ["utilities-js"],
```

## Examples
Note: All of these examples assume that either the script is included on HTML or imported using `` const util = require("utilities-js") `` or `` import * as util from "utilities-js" ``.

### isEmpty
Pretty self explanatory, checks if the value is empty. <br/>
Returns true if it is and false otherwise.
```javascript
util.isEmpty(value) 
```

### isPositive
Checks if the value is numeric and positive. <br/>
Throws an Error if the value isn't a number. <br/>
Returns true if it is and false otherwise.
```javascript
util.isPositive(value) 
```

### isEven
Checks if the value is numeric and even. <br/>
Throws an Error if the value isn't a number <br/>
Returns true if it is and false otherwise.
```javascript
util.isEven(value) 
```

### isArray
Checks if the value is an array. <br/>
Throws Error if value is empty <br/>
Returns true if it is and false otherwise.
```javascript
util.isArray(value) 
```

### isDOM
Checks if the value is a HTML DOM object. <br/>
Throws Error if value is empty <br/>
Returns true if it is and false otherwise.
```javascript
util.isDOM(value)
```

### isString
Checks whether or not the received value is a string. <br/>
Throws Error if value is empty <br/>
Returns true if it is and false otherwise.
```javascript
util.isString(value)
```

### isObject
Checks if the value is an object. <br/>
Throws an Error if the value is empty. <br/>
Returns true if it is and false otherwise.
```javascript
util.isObject(value) 
```

### isFunction
Checks if the value is a function. <br/>
Throws an Error if the value is empty. <br/>
Returns true if it is and false otherwise.
```javascript
util.isFunction(value) 
```

### isNumber
Checks if the value is a number. <br/>
Throws Error if value is empty <br/>
Returns true if it is and false otherwise.
```javascript
util.isNumber(value) 
```

### isBoolean
Checks if the value is boolean. <br/>
Throws Error if value is empty <br/>
Returns true if it is and false otherwise.
```javascript
util.isBoolean(value) 
```

### escapeString
Sanitizes a string, escaping special characters, double and single quotation marks and removing white spaces at the start and end of the string. <br/>
Throws an Error if the value is not a string. <br/>
Returns escaped string.
```javascript
util.isObject(value) 
```

### pushUnique
This is a Array.prototype function meaning it's only accessable through a instantiated array.  <br/>
This function checks if the value exists on the array and if it doesn't it'll push it in. <br/>
Returns false if the value is in the array and true otherwise.
```javascript
var arr = [1, 2, 3];
arr.pushUnique(2); // does nothing
arr.pushUnique(4); // adds 4 to the array
```

### removeIfExists
Also a prototype function. This one checks if an element exists in the array and if so, removes it. <br/>
Returns nothing.
```javascript
var arr = [1, 2, 3];
arr.removeIfExists(2); // removes 2
arr.removeIfExists(4); // does nothing
```

### formatDate 
Can be used either on an instantiated object or not. <br/>
Formats a date to either EU, US or MySQL-ready. Can return date and time or date only. The seperator can be specified to either "/" or "-" <br/>
Returns the formated date <br/>
Throws an Error if the date is empty or if the date was invalid and couldn't create a date instance with the received date.
```javascript
Date.formatDate(new Date(), type, withTime, seperator); 
```
or 
```javascript
var d = new Date();
d.formatDate(type, withTime, seperator); 
```
Where: <br/>
type = ``1 (EU format)``, ``2 (US format)`` or ``3 (database format)`` <br/>
withTime = ``true`` or ``false``, defaulting to ``true`` <br/>
seperator = ``/`` or ``-``, defaulting to ``/`` <br/>

# ChangeLog

### Version 1.1.4
- Added testing 
- Minor bugfixes to some functions

### Version 1.1.3 
- Fixed bug with DateFormat
- Migrated to TypeScript
- updated readme

### Version 1.1.2
- minor bugfixes

### Version 1.1.1
- improvements to isDOM
- added isBoolean function
- added better error messages for each function
- fixed issues formatDate had
- added param validation to formatDate
- added more customizability to formatDate

### Version 1.1.0
- removed input validation to it's own library as it no longer made sense here (https://github.com/Ribeiro-Tiago/input-validator)

### Version 1.0.9
- optmized isFunction
- optmized compatibility with nodejs
- added escapeString function

### Version 1.0.8
- added isString
- added isFunction
- added support for react native (not tested on reactjs but should work)

<br/><br/>

#### footnote
Currently when using webpack (with ts-loader) to compile and minify makes the functions aren't exported as they should. 
As a workaround for now, I'm manually transpiling using tsc and minifying the file, until I've more time to figure our what's the problem


# License
[MIT](https://couto.mit-license.org/)