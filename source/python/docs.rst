Documentation
=============


Add docstrings

**No**::

   def typical_function_in_the_lab():
       ...
       v =+ 1
       ...

1 sentence for obvious functions::


   def add_1(v):
       """Add 1"""
       return v+1


Full docstring for non trivial cases.
Start with a summary line,
give a full explanation (even with use cases) and
explain the arguments an the return::

   def create_table(s1, s2):
       """
       Create a enrichment table.

       Args:
          s1 (set): genes to evaluate
          s2 (set): reference genes

       Return:
           table. Amount of genes in s1 that are in s2 for each group of 5 genes.
       """
       ...;


For full docstrings there are several formats.
Although :abbr:`reST (reStructuredText)` format is the
"officially recommended", I prefer
`Google docstrings <http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html>`_
as they are more readable, in my opinion.

You can find examples in https://stackoverflow.com/questions/3898572/what-is-the-standard-python-docstring-format



----

In the Ipython console use ``?`` to access the docstring::

   create_table?

and ``??`` to access the whole code::

   create_table??



Comments
--------

When possible, put them on a line of their own

Use them sparingly and
avoid unnecessary comments

**No**::

   x = x + 1  # Increment x


**Yes**::

   x = x + 1  # Compensate for border


Prefer code readability to writing a lot of comments

**No**::

   # If the sign is a stop sign
   if sign.color == 'red' and sign.sides == 8:
       stop()


**Yes**::

   def is_stop_sign(sign):
       return sign.color == 'red' and sign.sides == 8

   if is_stop_sign(sign):
       stop()


Codetags
--------

Codetags are special markup conventions that serve as reminders
of sections of code that need closer look or revision.

Specially useful can be ``TODO`` or ``FIXME`` tags::

   # TODO: allow list to be passed

   # FIXME: loop should be finite

.. hint::

   In Pycharm they have a tool to to list of the TODO and FIXME entries.
   It can be found under :menuselection:`View --> Tool Windows --> TODO`

