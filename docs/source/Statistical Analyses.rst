********************
Statistical Analyses
********************

Univariate Analyses
===================

General Linear Model
--------------------

Correlation Method
^^^^^^^^^^^^^^^^^^^
 
For the Correlation Method, the Haemodynamic Response Function (HRF,
*hrf(t)*) has to be specified. Perseus first asks the user to select from three
choices: *linear - fixed*, *linear - free* parameters or *non-linear*. Then, one specific
function has to be selected and the (fixed) parameters have to be specified:

1.  **Linear HRFs:**

    a.  Fixed parameters
 
        *  Gamma function (3 fixed parameters to set, one free parameter). 
     
           .. math:: `hrf(t)=\begin{cases}\dfrac{(t-T_0)^{n-1}}{\lambda^n(n-1)!} e^{-t/\lambda} &&& \text{for } t>T_0 \\0&&& \text{for } t<T_0\end{cases}`
           :label: 1
           
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
           See Ashby 2019 (p. 32). The basis functions are series of delta functions. There is one impulse for each TR, se the user has to specify the assumed length of :math:`l_{HRF}` of the HRF, and the number of delta functions :math:`I` is calculated by:
           
           
           where the brackets denote the *floor function*. The :math:`I` basis function are:
           
           
           
        *  Gamma functions with derivate (3 or 5 fix parameters to set, 2 free parameters). One of the HRF functions with fixed parameters is selected (Equations 1 or 2, here denoted as :math:`b(t)`, indicating that it is a base function and not the HRF), and its (temporal) derivate :math:`\dot{b}(t)` is calculated. The HRF then becomes:
        
        
        
           **The derivative is normalised such that :math:`b(t)` and :math:`\dot{b}(t)` have the same sum of squares**
           
           
2.  **Non-Linear HRFs:**
    
    a.  Balloon model
    
    b.  Volterra series
    
    Whatever HRF is chosen, in the Correlation Method the BOLD response is then calculated by folding the HRF with the event boxcar function :math:`N(t)`:
    
    
    
    As all the possible HRF choices can be written as weighted sum of basis functions :math:``, the parameters to be optimised :math:`\theta` can be pulled out of the integral, thus only :math:`I` integrals have to be solved numerically for every timestep:
    
    
    
    The :math:`I * \text{timesteps}` values :math:`x_i(t)` will then be the content of the design matrix of the GLM, and the parameters :math:`\theta` will be optimised to fit the observed data. Then the estimated :math:`\theta\text{s}` undergo hypothesis testing. Typically the null hypothesis:
    
    
    
    which is tested against the alternative:
    
    
    
    Thus, a voxel is thought to be task-related if any of the free parameters is (statistically significant) larger than zero.
    
    **Comment: using your own HRF**
    
    It is possible to use user-defined HRFs. To do so, an array with data points approximating the HRF must be provided, together with specifications about what timesteps this array has. The HRF must not have values of :math:`t` ¡ :math:`0` and must be :math:`0` at :math:`t = 0`.

3.  Currently, there is only the option to test ONE LINEAR hypothesis. This hypothesis must be able to be written in the following way:


    
    Where :math:`\beta` is the vector of free parameters fitted in the previous step, and :math:`c` is a vector defined by the user. As example, let us assume that :math:`\beta_1` is the free parameter associated with an event of type A while :math:`\beta_2` is the free parameter associated with an event of type B. We now want to ask if a voxel is more responsive to A than to B. Then, the vector :math:`c` would be:
    
    
    
    Here, we assumed that also a baseline :math:`B_0` and drift :math:`\Delta` parameters are included, so the :math:`\beta` vector is:
    
    
    
    The user can indicate the vector :math:`c`, which will then be tested for the null hypothesis stated in eq. 15
