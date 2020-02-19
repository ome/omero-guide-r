Installing rOMERO-gateway
=========================

rOMERO-gateway will use rJava to communicate with an OMERO server.

**Install in a Conda environment**
----------------------------------

In this section, we show how to install rOMERO-gateway in a `Conda <https://conda.io/en/latest/>`_ environment.


- Install `Miniconda <https://docs.conda.io/en/latest/miniconda.html>`_ if necessary.

- If you do not have a local copy of the `omero-guide-r repository <https://github.com/ome/omero-guide-r>`_, first clone the repository::

    $ git clone https://github.com/ome/omero-guide-r.git

- Go into the directory::

    $ cd omero-guide-r

- Create a programming environment using Conda::

    $ conda create -n rgateway

- Install dependencies and some packages used in the notebooks using an installation file::

    $ conda env update -n rgateway --file binder/environment.yml

- Run a bash script to install rOMERO-gateway and the Java dependencies::

    $ bash binder/postBuild


**Install in RStudio**
----------------------

See :doc:`rstudio`


.. toctree::
   :maxdepth: 1
   :hidden:

   rstudio
