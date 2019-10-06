
Jobs
====

In this document we give some advice to run jobs in the cluster.


Where to submit
---------------

Typically, the :command:`bgqmap submit` command should be run
from the ``login`` node to prevent a waste of resource in
an interactive.


Fast jobs
---------

If you are running lots of jobs whose execution is fast,
make groups of jobs when submitting them (:command:`bgqmap sumbit -g`)
to reduce the overhead of the resource request.


Using the local disk
--------------------

If you are writing a lot of data, specially if you are doing
it in steps, it is highly recommended to use the local disk
of each node rather than any location in the workspace.
This helps the :abbr:`NFS (Network File System)` and
speed ups your computation (which can be a significant amount of time).

The easiest way to use the local disk is to use temporary files and directories.
Each job, has an environment variable :samp:`$TMPDIR` which point to a temporary
folder in the local disk of the node. Each job has a different one, and the folder
is deleted when the job is done.

Using the :samp:`$TMPDIR` variable is easy, even if you create your jobs
with the `bgqmap template <https://bgqmap.readthedocs.io/en/latest/template.html>`_.
Simple use it as your final location:

.. code:: bash

   bgqmap template "python myscript.py input{{1,2,3,4,5}}.txt ${TMPDIR}"

And then you can simply get you result by syncing back your files with a
post-command in the jobs-map file::

   # module load anaconda3/4.4.0
   # source activate myenv
   python myscript.py ${TMPDIR} 1
   python myscript.py ${TMPDIR} 2
   python myscript.py ${TMPDIR} 3
   python myscript.py ${TMPDIR} 4
   python myscript.py ${TMPDIR} 5

   # rsync -vaP ${TMPDIR}/* /my/derised/location/

.. note:: In the above example, the script generates files that do not
   have conflict names amongs other executions. If is the case,
   you can create subfolders (e.g. :code:`python myscript.py ${TMPDIR}/1 1`).
   In such case, ensure your script creates the necessary folder structure.


Writing your bash pipelines
---------------------------

A bash script is a powerful and easy way to create you pipelines.

E.g.::

   #!/bin/bash

   python preprocess.py -i data_in -o data_preprocessed
   python process.py -i data_preprocessed -o my_data
   python postprocess.py -i my_data -o result

For basic cases, adding the :command:`set -e` line at the beginning
of your script, forces that, when any of the commands fails, the script
is terminated.


Asking for resources
--------------------

In many cases we request more resources than need to prevent job fails,
or because one of our jobs takes a lot of resources (memory mainly).
However, asking for less resources will make your jobs to be allocated
faster and will enable you to run more at the same time.


If you do not know how many memory your jobs consume, you can get
this information from ``bgqmap run``::

    iker@bbgcluster$ bgqmap run "myjob myinput myoutput"
    Executing myjob myinput myoutput
    salloc: Granted job allocation 2699046
    salloc: Relinquishing job allocation 2699046
    Elapsed time:  00:10:00
    Memory  10G

.. warning:: This information is not 100% reliable,
   specially if you code has peaks of memory consumption.

If you have only one (or few) jobs that need more memory, you can:

- let **bgqmap** resubmit automatically the job with twice memory
- set more memory for that job in you jobs map file::

       myjob command ## memory=80G

- create a separate job map file for that job

