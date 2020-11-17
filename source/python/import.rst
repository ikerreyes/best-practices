Importing
=========

To increase readability,
the best practice is to import **whole modules**.
Then, it is clear where the functions come from.
In addition, it helps to avoid circular imports.

**No**::

   from os import *
   from os import listdir

**Yes**::

   import os
   import os.path
   from os import path


Only classes are "allowed" to be imported directly as long as there are not name clashes::

   from somewhere import ThisClass


Put imports at the top of the module and
divide them in 3 sections:

- System
- 3rd party
- Local
