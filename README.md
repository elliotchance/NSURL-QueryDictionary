[![Build Status](https://travis-ci.org/itsthejb/NSURL-QueryDictionary.svg?branch=master)](https://travis-ci.org/itsthejb/NSURL-QueryDictionary)
[![Build Status](https://travis-ci.org/itsthejb/NSURL-QueryDictionary.svg?branch=develop)](https://travis-ci.org/itsthejb/NSURL-QueryDictionary)

(Travis is does not yet support iOS7)

NSURL-QueryDictionary
=====================

Just a simple NSURL category to make working with URL queries more pleasant.

* `-[NSURL queryDictionary]` extract the URL's query string as key/value pairs.
* `-[NSURL URLByAppendingQueryDictionary:]` append the specified key/value pairs to the URL, with existing query handled. Note that behaviour for overlapping keys/values is undefined.

The parsing components of the above are also available separately as:

* `-[NSString URLQueryDictionary]` split a valid query string into key/value pairs.
* `-[NSDictionary URLQueryString]` the reverse of above; create a URL query string from an `NSDictionary` instance.

Queries with empty values are converted to `NSNull` and vice versa as of v0.0.5.

##Version history

**v0.0.7**

Fixed a potential issue/static analyser false positive with thanks to [Adam Lickel](https://github.com/lickel).

**v0.0.6**

Added optional flag to sort the dictionary's keys alphabetically when generating the URL. This makes the generated URLs more deterministic, which helps (for example) if you are running unit tests to inspect your URLs and would like to test the absolute string, rather than having to recreate a query dictionary.

**v0.0.5**

Covered an additional empty value case - URL query component has separator, but empty value.

**v0.0.4**

Added handling for keys with no value, empty value or `NSNull`.

**v0.0.3**

Split the query string parsing components out into `NSString` and `NSDictionary` categories for additional flexibility.

**v0.0.2**

Added support for dictionary keys other than NSString. Currently just uses `-description`, but this is ok for `NSNumber` and `NSDate` and a few others, so may be sufficient.

**v0.0.1**

Initial release.

Have fun!
---------

[MIT Licensed](http://jc.mit-license.org/) >> [jon.crooke@gmail.com](mailto:jon.crooke@gmail.com)
