********************
Statistical Analyses
********************

Univariate Analyses
===================

General Linear Model
--------------------

Correlation Method
^^^^^^^^^^^^^^^^^^
 
For the Correlation Method, the Haemodynamic Response Function (HRF,
*hrf(t)*) has to be specified. Perseus first asks the user to select from three
choices: *linear - fixed*, *linear - free* parameters or *non-linear*. Then, one specific
function has to be selected and the (fixed) parameters have to be specified:

1.  **Linear HRFs:**

    a.  Fixed parameters
 
        *  Gamma function (3 fixed parameters to set, one free parameter). 
     
           :math:`hrf(t)=\begin{cases}\dfrac{(t-T_0)^{n-1}}{\lambda^n(n-1)!} e^{-t/\lambda} &&& \text{for } t>T_0 \\0&&& \text{for } t<T_0\end{cases}`
           
           The parameters :math:`T_0`, :math:`\lambda` and :math:`n` can be chosen by the user.
 
        *  Difference of two gamma functions (5 fixed parameters to set, 1 free parameter). 
        
           :math:`\underline{x}=[  x_{1}, ...,  x_{n}]^{T}`
        
           The parameters :math:`a`, :math:`\lambda_1`, :math:`\lambda_2`, :math:`n_1` and :math:`n_2` can be chosen by the user. :math:`C` is the integral of the terms in square brackets.

  
