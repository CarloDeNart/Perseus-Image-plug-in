********************
Multivariate Analyses
********************

Functional MRI is mostly known for analysing event-related behaviour. This is typically done for each voxel individually - for each voxel it is tested if it shows task-related activity. Thus, the signal to be analysed is univariate, it has only one dimension (data from one voxel). In this type of analysis, #voxels statistical analyses of univariate signals are performed. But increasingly research moves towards the analysis of the brain as a whole, that is, all voxels are analysed together. Then, the signal to be analysed is multivariate, it has #voxels dimensions.In this type of analysis, one statistical analysis of a signals with #voxels dimensions is performed. 
In Perseus, so far you can perform two very common analyses of a multivariate signal: Principal Component Analysis (PCA) and Independent Component Analysis (ICA). 

Principle Component Analysis
=====================

Independent Component Analysis
=====================

Motivation
--------------------

The idea behind Independent Component Analysis (ICA) is that the observed signal is a mixture of independent source signals. As an example, consider the cocktail party problem (https://en.wikipedia.org/wiki/Cocktail_party_effect). You are at a party and talking to your crush, so you really want to understand every word. However, many other people are speaking in the room, and the sound that reaches your ears is a mixture of all words that are spoken. The problem now is to split the messy sound that reaches your ears into meaningful sentences - what your crush is saying, what the crazy guy at the bar is yelling, etc. In more fancy words, you want to "separate the sources of your signal". This problem is called "blind source separation" (https://en.wikipedia.org/wiki/Signal_separation). 

In neuroscience, it is assumed that the overall activity of the brain - as measured by fMRI - is a mixture of signals as well. The idea is that there are independent functional networks in the brain that are active at the same time. The overall signal measured by fMRI is then the mixture of the signals of all these sub-networks. The idea is now to extract these independent functional networks, and then to analyse them in subsequent steps. This might allow, for example, to find differences in particular sub-networks between different groups. For example, the most robust sub-neteork is called Default Mode Network (https://en.wikipedia.org/wiki/Default_mode_network) and it is often proposed that the activity patterns in this network might allow to diagnose diseases such as Alzheimer's or Autism [ref needed].  

When one uses ICA to analyse fMRI data, one first has to decide wether to perform spatial or temporal ICA. So far, Perseus only allows spatial ICA. The outcome of this analysis will be so-called independent components, which are the sub-networks of the brain. Each network is located at specific regions (which do not need to be adjacent), and has a specific timecourse. Thus, the outcome of the ICA analyses is 1) a set of 3D maps of components and 2) a time series of activity for each component. At most #timesteps components (sub-networks) can be inferred from the data, but typically much fewer are of interest. 

Theory
--------------------

For a gentle introductino to ICA we refer to an excellent tutorial on arXiv: https://arxiv.org/abs/1404.2986 . For a general idea, also consider Wikipedia (https://en.wikipedia.org/wiki/Independent_component_analysis). The algorithm we use is called FastICA (https://en.wikipedia.org/wiki/FastICA).

Prerequisite: Flattening the data
^^^^^^^^^^^^^^^^^^^

ICA in general
^^^^^^^^^^^^^^^^^^^

FastICA algorithm 
^^^^^^^^^^^^^^^^^^^


Usage
--------------------
