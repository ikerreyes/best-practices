
Logging
=======

Use ``print`` when you want to display a help statement for
a command line application.
For the `rest <https://docs.python.org/3/howto/logging.html#when-to-use-logging>`_,
use the `logging library <https://docs.python.org/3/library/logging.html>`_.

**No**::

   def f():
       print('Loading the data...')
       ...
       print('Computing')
       ...

**Yes**::

   def f():
       logging.debug('Loading the data...')
       ...
       logging.debug('Computing')
       ...
