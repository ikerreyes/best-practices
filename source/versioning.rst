
.. _versioning:

Versioning
==========

Use **git** to keep track of your code versions.

Add **tags** with the version to release commits.

Set your versions as **MAJOR.MINOR.PATCH**:

- *MAJOR*: incompatible API changes
- *MINOR*: new functionality backwards compatible
- *PATCH*: bug fix

.. note::

   In a Python project, indicate the ``version`` in the setup


``0.`` versions does not include PATCH as they are assumed to be unstable until version ``1.0.0``.

Do not make copies of files, add commits to git.

**No** ::

   mod.py
   mod-Copy1.py
   mod_v2.py



Versioning Jupyter notebooks
----------------------------

It is really difficult to have notebooks under version control.
Even non-visible changes can lead to differences and
merging could be not only difficult but a mess where everything breaks.
Moreover, notebooks cannot be shared if two people (or more) need to work at the same time on it.

Despite of being a mess, some advice:

- commit notebooks for particular releases
- put as much logic as you can on scripts
