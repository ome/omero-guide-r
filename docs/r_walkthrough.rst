Analyse data using R (statistical package)
==========================================

R is a free software environment for statistical computing and graphics. See \ https://www.r-project.org/\  for more information. 

Description
-----------

Here we demonstrate how to connect to OMERO using R, load images and
other objects from OMERO and perform image analysis followed up by
statistical analysis in R. We use R as part of a Jupyter notebook. In
the notebook we are going to use the idr0021 data. These are super
resolution microscopy images showing certain proteins around the
centrioles. With these images the authors of the
article \ `Subdiffraction imaging of centrosomes reveals higher-order
organizational features of pericentriolar
material <https://www.nature.com/articles/ncb2591>`__\  showed that the
area around the centrioles has a specific structure. By measuring the
shape and diameter of these proteins and comparing them to each other
they could show that each protein builds a specific part of this
structure, see \ `Figure
1 <https://www.nature.com/articles/ncb2591/figures/1>`__\ . Instead of
manually measuring each centriole ring like the authors did, we are
going to try to do this in an automated way in order to show that there
is a significant difference between these proteins and create a plot
similar to the one seen on \ `Figure
1 <https://www.nature.com/articles/ncb2591/figures/1>`__\ .

We will show:

-  How to connect to OMERO using R.

-  How to load images from OMERO to R.

-  How to perform segmentation of objects in an image in R.

-  How to calculate properties of the segmented objects (e.g. diameter) in R.

-  How to save the properties of the objects as an R dataframe.

-  How to create and save ellipse representations of the ROI for each
   segmented object onto the original image in OMERO.

-  How to save the properties of the objects as attachments in OMERO.

-  How to load images in a whole Dataset or Project from OMERO and perform the steps above on all images.

-  How to perform statistical analysis on the generated data in R and save results back to OMERO.

Setup
-----

In order to be able to connect to OMERO from within R we need the
rOMERO-gateway and rJava packages.

Note: Everything we are going to do there can be done in Rstudio as
well, if the rOMERO-gateway package and its dependencies are available
on your system.

See :doc:`setup`. 

Resources
---------

We will use data from the Image Data Resource (IDR).

-  IDR data `idr0021 <https://idr.openmicroscopy.org/search/?query=Name:idr0051>`__.

-  Notebook `idr0021_Segmentation.ipynb <https://mybinder.org/v2/gh/ome/omero-guide-r/master?filepath=notebooks/idr0021_Segmentation.ipynb>`_.

For convenience, the IDR data have been imported into the training
OMERO.server. This is only because we cannot save results back to IDR
which is a read-only OMERO.server.

Step-by-step
------------

All the steps are described in detail inside the Jupyter notebook. In you are running 
locally or in mybinder, go to:

-  In the *notebooks* folder, select the notebook *idr0021_Segmentation.ipynb*.

Note: We are going to show the image segmentation and feature calculation on a small subset of the idr0021 data. The full analysis of the idr0021 project has already been done and the result saved as ‘Summary from R’ table. We are going to load this table in order to do
the statistical analysis at the end of the notebook.

Here, we give a digest of the steps inside the notebook: The notebook steps will:

#. Fetch the images from OMERO using rOMERO-gateway.

#. Perform image segmentation to identify the protein rings around the centrioles using EBImage in R.

#. Calculate the properties (features) of the identified objects (shape, diameter, etc.) using EBImage.

#. Store these features in R as an R dataframe.

#. The segmentation and feature calculation is a rather costly process. You don’t want to do this all over again. Therefore we save the identified objects (ROIs, region of interests) and the properties back to OMERO using rOMERO-gateway.

#. Perform statistical analysis on that data in R.

#. At the end of the notebook a plot is created which is similar to the one shown in \ `Figure 1 <https://www.nature.com/articles/ncb2591/figures/1>`__\  of the article. One dataset in particular has extreme outliers. OMERO.parade https://github.com/ome/omero-parade can be used to find the images that cause the outliers.

#. Note: OMERO.parade uses the *Summary from R* table that is attached to the project in order to provide enhanced filtering and plotting features.
