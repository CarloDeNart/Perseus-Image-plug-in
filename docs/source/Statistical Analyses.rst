Statistical Analyses
====================

.. _Statistical analyses:

Univariate Analyses
===================

General Linear Model
--------------------

**Correlation Method**
 
For the Correlation Method, the Haemodynamic Response Function (HRF,
*hrf(t)*) has to be specified. Perseus first asks the user to select from three
choices: *linear - fixed*, *linear - free* parameters or *non-linear*. Then, one specific
function has to be selected and the (fixed) parameters have to be specified:

#. **Linear HRFs:**

 #. Fixed parameters
 
 * Gamma function (3 fixed parameters to set, one free parameter). |The parameters T0, sdf and n can be chosen by the user.
 
 * Difference of two gamma functions (5 fixed parameters to set, 1 free parameter). |The parameters a, sf1, sdf2, n1 and n2 can be chosen by the user. C is the integral of the terms in square brackets.

  
