# Cookies module

Provides a utility for getting or setting the value of cookies.  Also contains additional methods for getting and setting parameters of certain FT cookies (which use a variety of different syntaxes)

## API

* `get(name)` - retrieves the value of cookie `name`
* `set(name, value, options)` - sets the value of cookie `name` to `value`. The options object, if specified, can have any of the following properties
	* `expires`: Lifetime of the cookie. Value can be a number of days from time of creation or a Date object. *default: 730 days*
	* `path`: The path where the cookie is valid *default: '/'*
	* `domain`: The domain where the cookie is valid *default: '.ft.com'*
	* `secure`: If `true` the cookie will only be sent over https *default: false*
* `remove(name)` - unsets the value of a cookie
* `getParam(name, param)` - gets the value stored in the given parameter within cookie `name` (only works for some FT cookies which use a predefined syntax for separating parameters)
* `setParam(name, param, value)` - sets the value stored in the given parameter within cookie `name` (only works for the AYSC FT cookie)

## Supported FT cookies

The following FT cookies are supported for setting and fetching key-value data from within the cookie

* `AYSC`
* `FT_U`
* `FT_Remember`
* `FT_User`
* `FTQA`

Example:

```javascript
// Get the value of slot 2 in the AYSC cookie
var val = require('o-cookies').getParam('AYSC', '02');
```
