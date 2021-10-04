**************
Basic Usage
**************

In this section basic commands like loading or saving data and visualizing images are explained. 

.. _load:

Load Data
===========

There are three different commands that allows to import a dataset into Perseus structure: one for data that follows the BIDS structure, one for fMRIprep output and lastly a general importer that allows to select and load a specific file. 

BIDS Upload
------------

The easiest way to load data into Perseus is the BIDS (`BIDS rules <https://bids.neuroimaging.io/>`_) upload option. If
your project is stored in a folder which follows the BIDS rules, just select this
folder and all the necessary data will be read in automatically.

it is important that in the folder also the file containing the events and the one with the MRI scan parameters are present in the *.json* format. The events files is required to specify at which time a certain task or event was performed. The parameters file allows Perseus to acquire automatically the information of each functional run, like for example the **repetition time**. Without these files the program can still upload images, although it will be impossible to run the statistical analyses.

To allow Perseus to identify correctly to which subject, session and run each functional images belongs to, it is important to keep the BIDS naming convention. For example: naming the file in this way *sub-01_ses-mri_task_run-01_bold.nii* allows to assign to the *.nifti* to subject-01, session-01 (task related) and run-01.

fMRIprep Upload
----------------

If `fMRIprep <https://fmriprep.org/en/stable//>`_ is the preferred choice to run the preprocessing, Perseus can still be used for statistical analyses. With this command it is possible to upload images from fMRIprep output: Perseus will navigate through the output directory and select only those images needed. To do so is sufficient to select fMRIprep output directory.

Generic Upload
---------------



.. _data-type:

Data Types
===========

After importing the selected files an *image collection* will be created. This collection contains images and other information, the following section describes how these files are stored.

.. _functional:

Functional Images
------------------



.. _anatomical:

Anatomical Images
------------------



Parameter Maps
---------------


.. _save:

Save Data
==========

There are two possible way to save the data: using the nifti exporter or saving Perseus session.

**Nifti Exporter**: the command allows to export only nifti files. Select the *image collection* wanted to be exported, then the export command allows to select the output directory and chose which images of the whole collection will be saved.

**Save Session**: go to *file* and select *save* or *save as*. This allows to save a *.sps* file that cointains all images and the workflow network. After loading in Perseus the *.sps* file the session will be reopened exacly as it was when saved.

Lastly it is possible to create a *.PDF* file containing only the network reporting all processing steps. To do so select the *.PDF* icon called *Export graphics*.

.. _visualize:

Visualize Images
=================

The *Image viewer* command, under *Visualization*, allows to visualize the selected *image collection*. After running this command a small box will appear under the *image collection*, by clicking on it a section will appear on the left showing images and what the *image collection* contains.

Remember that colors are assigned randomly and they can be changed at any time. If the images are too small it is possible to enlarge them by making the window where they appear wider. 

Make Overlay
-------------



Select Regions of Interest
===========================

