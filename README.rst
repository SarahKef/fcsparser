FCSParser
=================

fcsparser is a python package for reading fcs files. 

.. image:: https://travis-ci.org/eyurtsev/fcsparser.svg?branch=master
   :target: http://travis-ci.org/eyurtsev/fcsparser
   :alt: Build Status


Install
==================

    $ pip install fcsparser

Using
==================

    >>> import fcsparser
    >>> path = fcsparser.test_sample_path
    >>> meta, data = fcsparser.parse(path, reformat_meta=True)

Using to clone an fcs file and modify data

    >>> from fcsparser.api import FCSParser
    >>> path = fcsparse.test_sample_path
    >>> fcs_file = FCSParser(path)
    >>> subset_fcs_file = fcs_file.clone(data=fcs_file.data[:1000])
    >>> subset_fcs_file.write_to_file('/tmp/subset_fcs_file.fcs')

If no data is passed in to `clone`, the entirety of the existing data will be used
in the clone.

A more detailed example can be found here: http://nbviewer.ipython.org/github/eyurtsev/fcsparser/blob/master/doc/fcsparser_example.ipynb


Features
===================

- **python**: 2.7, 3.3, 3.4
- **FCS Formats**: Supports FCS 2.0, 3.0, and 3.1
- **FCS Machines**: BD FACSCalibur, BD LSRFortessa, BD LSR-II, MiltenyiBiotec MACSQuant VYB

Contributing
=================

Pull requests are greatly appreciated. Missing features include:

1. the ability to apply compensation.
2. a set of transformations (hlog, logicle, etc.) that can be applied.

Also fcs files from more devices and more formats are greatly appreciated, especially if the parser fails for them!

Resources
==================

- **Documentation:** https://github.com/eyurtsev/fcsparser
- **Source Repository:** https://github.com/eyurtsev/fcsparser
- **Comments or questions:** https://github.com/eyurtsev/fcsparser/issues

LICENSE
===================

The MIT License (MIT)

Copyright (c) 2013-2015 Eugene Yurtsev

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
