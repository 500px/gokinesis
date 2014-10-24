gokinesis
=========
Golang client library for Kinesis

This was created by reverse-engineering the protocol used by the official Python
client:
    http://aws.amazon.com/blogs/aws/speak-to-kinesis-in-python/

Some notes on this protocol can be found in the wiki:
    https://github.com/nieksand/gokinesis/wiki/KCL-Protocol


## Usage
To build the example:

1. cd gokinesis
2. ``export GOPATH=`pwd` ``
3. cd examples/trivial
4. go build .

Note that the KCL daemon uses stdin and stdout to communicate with the client.
Any program output should go elsewhere (e.g. stderr or a file).

To run the example, see the documentation for the official Python client
library.


## Design
Originally I planned to use a channel for incoming records.  However the
request/reply protocol used by the KCL daemon puts restrictions on when
checkpointing can happen.  The current design resembles the approach taken by
the official Python client library.


## License
The MIT License (MIT)

Copyright (c) 2014 Niek J. Sanders

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
