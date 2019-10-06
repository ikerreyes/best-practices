Lambda expressions
==================


Restrict lambda expressions to places where
no assignments are needed (to be embedded in larger expressions)

**No**::

   f = lambda x: x*2


**Yes**::

   def f(x):
       return x*2

   df.groupby('X').apply(lambda x: x*2)

