
Data
====

.. |d| replace:: **datasets**
.. |p| replace:: **projects**

There are 2 main folders in the cluster: |p| and |d|.

|d|

   This workspace contains all the datasets that we download from external sources.
   Also any post processing of this data (like filtering, union, formating…)
   that don’t use any of our methods to generate new data goes here.

   If you are about to create one, please follow these rules:

   - give it a meaningful name that clearly identifies it
   - unless it is very clear there is no version for the data
     (e.g. UCSC genomes, which are versioned by their names)
     use a version (e.g. :file:`dataset_name/version`).
     If the external source lacks of version, use the
     creation date (``YYYY-MM-DD``)
   - ALWAYS add a ``README`` file with the name of who has downloaded
     or created this dataset, a short description and an URL or script
     to download or reproduce the dataset


|p|

   Please follow these rules for using |p|:

   - give it a meaningful name that clearly identifies it
   - follow software versioning control and naming
     (see :ref:`version section <versioning>`)

