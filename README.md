matlab-xunit-doctests
=====================

DocTests extension for matlab-xunit

What is this good for?  Well, often it's nice to have examples in your
documentation.  Well, now you can automatically run those examples to
make sure that they still produce the expected output.  This helps
prevent documentation rot.

If you're doing serious testing, it's best not to use DocTests for that,
because real unit testing frameworks like xUnit are much more flexible
and powerful.  In addition, documentation is supposed to be
documentation, and if you fill up your help file with lots of arcane
manipulations, no one will thank you.

What does a DocTest look like?  Here's a simple one::

        function sum = add2(num)
        %add2 Add two to a number
        %
        % Example:
        %
        % >> add2(88)
        % ans =
        %   90
        %

        sum = num + 2;

The DocTest system also has a limited ability to detect that an expected
exception was thrown, e.g. if you want to make sure an error message is
printed.  It is not sensitive to whitespace (it collapses all whitespace
to a single space when comparing the real result with the example).  It
also supports ``***`` as a wildcard.

Running
-------

The method for causing DocTests to be run is a little bit in flux.  For
the moment, the best way is to copy the ``testDocTestsHere.m`` file from
``xunit/`` into a directory that contains functions with doctests.  Then,
you can use the normal xUnit ``runxunit`` function to run both unit and
doctests.

Origin
------

Originally written by [Thomas Grenfell Smith](https://github.com/tgs/) as part of matlab-xunit. Now broken out into its own xunit extension.

License
-------

[BSD 2-Clause](http://opensource.org/licenses/bsd-license.php)
