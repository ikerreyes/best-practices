Temporary files and dirs
========================

The `tempfile library <https://docs.python.org/3.6/library/tempfile.html>`_
contains the utilities to deal with temporary files and directories.

Use the high level interface, because you do not need to worry about
cleaning the temporary files.

**Possible**::

   directory = tempfile.mkdtemp()
   ...
   shutil.rmtree(directory)


**Better**::

   directory = tempfile.TemporaryDirectory()
   ...


**Best**::

   with tempfile.TemporaryDirectory() as tmpdirname:
       ...

