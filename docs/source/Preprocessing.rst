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

1. **Path to SPM**: specify the path to SPM folder, exactly as MatLab does.
2. **Number of slices**: how many slices are present in each image, this information is obtained measuring the Z axis. 
3. **Repetition Time (TR)**: time in seconds to acquire a full image, this information can be found in the *.json* file. If TR is -1 it means either the *.json* file is not readable/present or TR is not present in it.
4. **Reference slice**: the number of the starting slice. 
5. **Slice order**: depending on the scanner used, slices can be consequential or interleaved. Consequential ones can be *bottom -> up* (starting from the first one) or *up -> bottom* (starting from the last one). Interleaved means that the scanner process through all even or odd slices first and then returns to the starting point to fill the empy spaces. Interleaved can start from the bottom and be *bottom -> up (even first)* (starting from slice 2) or *bottom -> up (odd first)* (starting from number 1); they can start from the top too and be *top -> down (even first)* or *top -> down (odd first)*. To know the slice order consult the *.json* file, it should report at what time point each slice was acquired allowing to understand their which order. 
6. **Select runs**: this command allows to select which runs, sessions either subjects should be processed. *All runs* will process all the images in the selected *image collection*, *select BIDS enetities* allows to select either all subjects, sessions or runs, *select manually* allows to select directly which images to process.

Head Motion Correction (SPM)
=============================

Small head and neck movements commonly happen during the scanning session, especially in fMRI considering the time it takes. Head motion correction removes small movements and allows every image in the time series to be superimposable. Although if the subject mooved too much during the session the correction will not be enough and it is recommended to remove the images from the time series.

The output consist in a new image series containing the corrected images and an image representing the mean of all functional images and a matrix. In the matrix reports the information on how much every image has been shifted, it is possible also to visualize it --*insert part in visualization with link*-- . 

Head Motion Correction Parameters
----------------------------------

1. **Path to SPM**:
2. **Selet type of correction**:
3. **select runs**:

Estimate & Reslice Parameters
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. **Quality**:
2. **Separation**: 
3. **Smoothing (FWHM)**:
4. **Num passes**:
5. **Realign interpolation**:
6. **Realign wrapping**:
7. **Resliced images**:
8. **Reslice interpolation**:
9. **Reslice wrapping**:
10. **Masking**:

Estimate & Unwarp Parameters
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. **Quality**:
2. **Separation**: 
3. **Smoothing (FWHM)**:
4. **Num passes**:
5. **Realign interpolation**:
6. **Realign wrapping**:
7. **Basis functions**:
8. **Regularisation**:
9. **Reg. factor**:
10. **Jacobian factor**:
11. **First-order effects**:
12. **Second-order effects**:
13. **Smoothing for unwarp (FWHM)**:
14. **Re-estimate movement params**:
15. **Number of iterations**:
16. **Taylor expansion point**:
17. **Resliced images (unwarp)**:
18. **Interpolation (unwarp)**:
19. **Wrapping (unwarp)**:
20. **Masking**:

Coregistration (SPM)
=====================



Coregistration Parameters
--------------------------

1. **Path to SPM**:
2. **Chose which image should be transformed**:
3. **Select type of correction**:
4. **Objective function**:
5. **Separation**:
6. **Tolerances**:
7. **Histogram smoothing**:
8. **Interpolation**:
9. **Wrapping**:
10. **Masking**:

Normalisation (SPM)
====================



Normalisation Parameters
-------------------------

1. **Path to SPM**:
2. **Choose image to normalise**:
3. **Select type of normalisation**:
4. **Bias regularisation**:
5. **Bias FWHM**:
6. **Tissue probability map**:
7. **Affine regularistion**:
8. **Warping regularisation**:
9. **Smootheness**:
10. **Sampling distance**:
11. **Bounding box**:
12. **Voxel sizes**:
13. **Interpolation**:
14. **Select runs**:

**Normalise anatomical images**:

Segmentation (SPM)
===================



Segmentation Parameters
------------------------

1. **Path to SPM**:
2. **Bias regularisation**:
3. **Bias FWHM**:
4. **Save bias corrected**:
5. **MRF parameter**:
6. **Clean up**:
7. **Warping regularisation**:
8. **Affine regularisation**:
9. **Smootheness**:
10. **Sampling distance**:
11. **Deformation fields**:
12. **Number of Gaussians (tissue number)**:
13. **Native tissue (tissue number)**:
14. **Warped tissue (tissue number)**:
15. **Select runs**:

Smoothing (SPM)
================



Smoothing Parameters
---------------------

1. **Path to SPM**:
2. **FWHM**:
3. **Data type**:
4. **Implicit masking**:
5. **Select runs**:


Masking
========



Masking Parameters
-------------------

1. **Threshold**:
2. **Masks**:
3. **Select runs**:
