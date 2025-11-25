========
pyformat
========

.. image:: https://github.com/myint/pyformat/actions/workflows/build.yml/badge.svg
    :target: https://github.com/pyformat/actions/actions/workflows/build.yml
    :alt: Build status

.. image:: https://coveralls.io/repos/github/myint/pyformat/badge.svg
    :target: https://coveralls.io/github/myint/pyformat
    :alt: Coverage status

*pyformat* formats Python code to follow a consistent style.


Features
========

- Formats code to follow the PEP 8 style guide (using autopep8_).
- Removes unused imports (using autoflake_).
- Formats docstrings to follow PEP 257 (using docformatter_).
- Makes strings all use the same type of quote where possible (using unify_).


Installation
============

From pip::

    $ pip install --upgrade pyformat


Example
=======

After running::

    $ pyformat --in-place example.py

This code:

.. code-block:: python

   def launch_rocket   ():



       """Launch
   the
   rocket. Go colonize space."""

   def factorial(x):
       '''

       Return x factorial.

       This uses math.factorial.

       '''
       import math
       import re
       import os
       return math.factorial( x );
   def print_factorial(x):
       """Print x factorial"""
       print( factorial(x)  )
   def main():
       """Main
       function"""
       print_factorial(5)
       if factorial(10):
         launch_rocket()

Gets formatted into this:

.. code-block:: python

   def launch_rocket():
       """Launch the rocket.

       Go colonize space.

       """


   def factorial(x):
       """Return x factorial.

       This uses math.factorial.

       """
       import math
       return math.factorial(x)


   def print_factorial(x):
       """Print x factorial."""
       print(factorial(x))


   def main():
       """Main function."""
       print_factorial(5)
       if factorial(10):
           launch_rocket()


.. _autoflake: https://github.com/myint/autoflake
.. _autopep8: https://github.com/hhatto/autopep8
.. _docformatter: https://github.com/myint/docformatter
.. _unify: https://github.com/myint/unify
