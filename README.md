# User guides for the OMERO R API
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ome/omero-guide-r/master?filepath=notebooks)

[![Documentation Status](https://readthedocs.org/projects/omero-guide-r/badge/?version=latest)](https://omero-guides.readthedocs.io/en/latest/r/docs/index.html)

[![Actions Status](https://github.com/ome/omero-guide-r/workflows/repo2docker/badge.svg)](https://github.com/ome/omero-guide-r/actions)

[![Actions Status](https://github.com/ome/omero-guide-r/workflows/sphinx/badge.svg)](https://github.com/ome/omero-guide-r/actions)

The documentation is deployed at [Use R API](https://omero-guides.readthedocs.io/en/latest/r/docs/index.html)


This guide demonstrates how to use the OMERO R API.

To run the notebooks, you can either [run on mybinder.org](https://mybinder.org/v2/gh/ome/omero-guide-r/master?filepath=notebooks) or build locally with [repo2docker](https://repo2docker.readthedocs.io/).


To build locally:

 * Install [Docker](https://www.docker.com/) if required
 * Create a virtual environment and install repo2docker from PyPI.
 * Clone this repository.
 * Run ``repo2docker``
 * Depending on the permissions, you might have to run the command as an admin

```
pip install jupyter-repo2docker
git clone https://github.com/ome/omero-guide-r.git
cd omero-guide-r
repo2docker .
```

See also [setup.rst](https://github.com/ome/omero-guide-r/blob/master/docs/setup.rst)


This is a Sphinx based documentation. 
If you are unfamiliar with Sphinx, we recommend that you first read 
[Getting Started with Sphinx](https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html).
