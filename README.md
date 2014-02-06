data-uri-to-buffer
==================
### Generate a Buffer instance from a [Data URI][rfc] string
[![Build Status](https://travis-ci.org/TooTallNate/node-data-uri-to-buffer.png?branch=master)](https://travis-ci.org/TooTallNate/node-data-uri-to-buffer)

This module accepts a ["data" URI][rfc] String of data, and returns a
node.js `Buffer` instance with the decoded data.


Installation
------------

Install with `npm`:

``` bash
$ npm install data-uri-to-buffer
```


Example
-------

``` js
var dataUriToBuffer = require('data-uri-to-buffer');

// plain-text data is supported
var uri = 'data:,Hello%2C%20World!';
var decoded = dataUriToBuffer(uri);
console.log(decoded.toString());
// 'Hello, World!'

// base64-encoded data is supported
uri = 'data:text/plain;base64,SGVsbG8sIFdvcmxkIQ%3D%3D';
decoded = dataUriToBuffer(uri);
console.log(decoded.toString());
// 'Hello, World!'
```


API
---

### dataUriToBuffer(String uri) → Buffer

The `type` property on the Buffer instance gets set to the Content-Type portion of
the "mediatype" portion of the "data" URI, or defaults to `"text/plain"` if not
specified.

The `charset` property on the Buffer instance gets set to the Charset portion of
the "mediatype" portion of the "data" URI, or defaults to `"US-ASCII"` if not
specified.


License
-------

(The MIT License)

Copyright (c) 2014 Nathan Rajlich &lt;nathan@tootallnate.net&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[rfc]: http://tools.ietf.org/html/rfc2397
