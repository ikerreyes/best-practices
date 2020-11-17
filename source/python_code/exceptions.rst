Exceptions
==========

Exceptions can be a powerful tool for you
and for code development and usage,
but can also be a drawback
(they can have a huge impact on performance)
when not being used properly.

Probably you are using exceptions
even without noticing.
For example, for lists raise a
``StopIteration`` exception
when you iterate over them (e.g. in a for loop)
and there are no more items left.

You should be aware when to use and when not use exceptions.
**Do not use exceptions for flow-control**.
Exceptions exist for exceptional situations:
events that are not a part of normal execution.

**No**::

   def is_multiple(x, y):
       if x % y == 0:
           return True
       else:
           raise Exception()

**Yes**::

   def is_multiple(x, y):
       if y == 0:
           raise Exception()
       if x % y == 0:
           return True
       else:
           return False

If your code is going to capture exceptions
that you would like to manage or
to set a particular message to help users
or developers what went wrong and where,
a good practice is to define your own
exception class.

User exceptions should typically derive from, at least,
``Exception``::

   class MyPackageError(Exception):
       pass

Most exceptions are defined with names that end in “Error”.

If you want to create a set of exceptions
you can create a base class and derive from that::

   class MyPackageError(Exception):
      pass

   class UserInputError(MyPackage):
      pass

   class ClusterError(MyPackage):
      pass

It is also useful to give a meaningful error message to your exceptions:

.. ipython:: python
   :okexcept:

   class MyPackage(Exception):
       pass

   raise MyPackage('Exception raised')

**No**::

   def f():
       if something_goes_wrong:
           raise Exception()

**Yes**::

   def f():
       if something_goes_wrong:
           raise Exception('This has occurred')


Handling exceptions
-------------------

In Python exceptions are handled with the ``try-except`` clause.

- Avoid try-except whenever is possible
- Limit the try clause to the minimum possible lines
- Indicate the exception you want to capture

**No**::

   def to_int(v):
       try:
           return int(v)
       except:
           None


**Yes**::

   def to_int(v):
       try:
          v = int(v)
       except ValueError:
           return None
       else:
           return v

