
Spacing
=======

Indent with 4 spaces, not tabs


Limit lines to 80-100 characters:

**No**::

   text = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. In a interdum ante. Vivamus blandit interdum justo a finibus. Fusce placerat ante nulla, eget malesuada magna tempor non. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur iaculis quis eros ultrices sagittis. Vivamus eget sem quis est ullamcorper dignissim.'

**Yes**::

   text = ('Lorem ipsum dolor sit amet, consectetur adipiscing elit. In a interdum ante.'
           'Vivamus blandit interdum justo a finibus. Fusce placerat ante nulla, eget malesuada'
           'magna tempor non. Lorem ipsum dolor sit amet, consectetur adipiscing elit. '
           'Curabitur iaculis quis eros ultrices sagittis. Vivamus eget sem quis est ullamcorper dignissim.')




Use blank lines to separate functions and classes, and larger blocks of code inside functions:


**No**::

   def f():
      ...
   def g():
      ...
      ...

**Yes**::

   def f():
      ...


   def g():
      ...

      ...


Use spaces around operators and after commas, but not directly inside bracketing constructs:

**No**::

   def f( a,g ):
       b=a
       return b[ g ]

**Yes**::

   def f(a, g):
       b = a
       return b[g]

