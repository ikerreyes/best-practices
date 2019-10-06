
Functions
=========

Functions should be:

- easy to read: meaningful name and arguments
- easy to change: adding something (a new keyword argument) does not break
  other parts

Be explicit (whenever possible)

**No**::

   def point(*args):
       # do something

**Yes**::

   def point(x, y):
       # do something

Respect arguments order when calling the function

**No**::

   point(y=7, x=3)

**Yes**::

   point(3, 7)

Do not use arbitrary argument list if you can pass a list


**No**::

   send(message, *args):
      # send message

   message('Hi', 'Lancelot', 'Gallahad')

**Yes**::

   send(message, recipients):
      # send message

   message('Hi', ['Lancelot', 'Gallahad'])

Do not add arguments (typically keyword arguments) for cases you won't use.
It is often harder to remove an optional argument (and its logic inside the function)
that was added “just in case” and is seemingly never used,
than to add a new optional argument and its logic when needed.

Sometimes the `YAGNI <https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it>`_
principle is a good approach to follow:
do not add a logic untill you really need it.

If possible, try to keep a single exit point, instead of multiple return statements.
