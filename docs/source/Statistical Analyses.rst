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

    b.  Estimated parameters
    
        The HRF is modelled as sum of :math:`I` basis functions :math:`b_i(t)` weighted by factors :math:`\theta_i`(see Friston et al. 1998):
        
        
        This allows to integrate only once, thus enormously speeding up the calculations. The basis functions can be chosen by the user:
        
        *  Three gamma probability density functions (no fix parameters to set, 3 free parameters).
           As suggested by Friston et al 1998:
           
           
        *  Finite Impulse Response FIR (1 fix parameter to set, :math:`I` free parameters).
           See Ashby 2019 (p. 32). The basis functions are series of delta functions. There is one impulse for each TR, se the user has to specify the assumed length of :math:`l_HRF` of the HRF, and the number of delta functions :math:`I` is calculated by:
           
           
           where the brackets denote the *floor function*. The :math:`I` basis function are:
           
           
           
  
