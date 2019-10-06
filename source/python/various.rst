Various
=======

Avoid getter and setter methods

**No**::

   person.set_age(40)

**Yes**::

   person.age = 40


Use one line per statement

**No**::

   print('a'); print('b')

   if <complex statement> and <simple statement>:
       # do something

**Yes**::

   print('a')
   print('b')

   cond = <complex statement>
   if cond and <simple statement>:
       # do something

Don't explicitly compare to True or False

**No**::

   if x == True:
       print('true')

**Yes**::


   if x:
       print('true')


Use the with statement when dealing with files


**No**::

   f = open('file.txt')
   a = f.read()
   ...
   f.close()

**Yes**::


   with open('file.txt') as f:
    for line in f:
        ...


Don’t use fancy encodings if possible
