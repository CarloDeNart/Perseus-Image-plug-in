**************
Preprocessing
**************

In this part preprocessing steps will be discussed. Remember that *Slice timing*, *Head motion correction*, *Coregistration*, *Normalisation*, *Segmentation* and *Smoothing* require MatLab and SPM to work. For futher information regarding these steps consult `SPM's manual <https://www.fil.ion.ucl.ac.uk/spm/doc/spm12_manual.pdf/>`_.

To avoid errors during the preprocessing it is recommended to proceed through all the steps keeping the following order.

Slice timing (SPM)
===================

To acquire fMRI images the scanner divides the area investigated in slices (2D-planes) and then slices are stacked together to obtain a 3D-image. This causes the last slice to be slightly shifted in time compared to the first acquired one, but in further analyses every image is treated like it was entirerly acquired at the same time. Slice timing allows to correct temporal shifts and smooth eventual artifacts caused by the scanner.

**If repetition time is around one second slice timing is not necessary. Instead in the case repetition time is over two seconds, slice timing significantly increases statistical power in further analyses.**

Slice Timing Parameters
------------------------

If the *.json* file containing the information regarding each functional run is present, Perseus will get autonomously *Repetition Time*. It is still recommended to check if the numbers are correct before proceeding with the slice timing.

1. *Path to SPM*: specify the path to SPM folder, exactly as MatLab does.
2. *Number of slices*: how many slices are present in each image, this information is obtained measuring the Z axis. 
3. *Repetition Time (TR)*: time in seconds to acquire a full image, this information can be found in the *.json* file. If TR is -1 it means either the *.json* file is not readable/present or TR is not present in it.
4. *Reference slice*: the number of the starting slice. 
5. *Slice order*: depending on the scanner used, slices can be consequential or interleaved. Consequential ones can be *bottom -> up* (starting from the first one) or *up -> bottom* (starting from the last one). 
6. *Select runs*: 

Head motion correction (SPM)
=============================



**Usage**



Coregistration (SPM)
=====================



**Usage**



Normalisation (SPM)
====================



**Usage**



Segmentation (SPM)
===================



**Usage**



Smoothing (SPM)
================



**Usage**



Masking
========



**Usage**

