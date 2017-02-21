---
layout: page
title: Imaging tools  
description: Overview of CAI imaging tools
---

At CAI we have developed imaging workflows using multiple software tools such as MINC, FSL, SPM, FreeSurfer, Nipype etc.
These workflows may use either individual or a combination of the software toolbox mentioned below. 

In this page we provide a brief description of these tools and their functionality and the imaging workflows developed using them at CAI.

<dl>
<dd> <h2 style="color:#990099;"> Minc: </h2> </dd>
</dl>

[MINC](http://www.bic.mni.mcgill.ca/ServicesSoftware/MINC) file format and toolbox was originally conceived by
Peter Neelin to deal with variations in the multiple file formats obtainer from varying scanners and different research groups.
The original file format and tools were based on NetCDF format and was unbale to handle large datasets. As a result a new version,
MINC2 was proposed in 2003. In addition MINC toolkit was developed and is an effort by Dr. Vladimir Fonov. The toolkit consists of 
most commonly used minc tools packaged under 64 bit binary for Debian, Ubuntu and Mac OS X. MINC toolkit also offers interactive
visualization tools such as MINC [register](http://www.bic.mni.mcgill.ca/software/register/register.html) and [Display](http://www.bic.mni.mcgill.ca/software/Display/Display.html). Additional information about software packages, releases and their 
installation can be found [here](http://bic-mni.github.io/#notes-about-versions). There are pre-build virtual machine images available here: https://atlas.hashicorp.com/CoBrALab/artifacts/MINC-VM/types/virtualbox.image 
    
MINC toolbox uses minc(.mnc) data format.
    
Some of the following features offered by MINC file format makes it advatangeous to work with at CAI.

* MINC is inherently N-dimensional where data can be structured with any number of spatial or temporal dimensions.

* MINC is multimodal and can be used to store CT, MRI, PET and other medical imaging data.

* MINC data an be defined in both voxel and world coordinate system.

At CAI the human brain atlas workflow primarily utilizes MINC data type and tools in its pipeline. Further information about the 
atlas can be found at [volgenmodel-nipype](https://github.com/CAIsr/volgenmodel-nipype). Also, prior to the atlas building; 
we convert the necessary DICOM datasets into MINC (.mnc) file format. The atlas workflow implements several of the MINC tools
such as minc bigaverage, resample, volcentre etc. It also conducts linear and nonlinear registration using BestLinReg and Nlpfit
provided by the MINC toolbox. Further information about these tools can be found [here](http://nipype.readthedocs.io/en/latest/interfaces/generated/nipype.interfaces.minc.minc.html); these tools can be executed 
either though the command prompt or the [Nipype](http://nipype.readthedocs.io/en/latest/) workflow.
    
<dl>
<dd> <br> </dd>
</dl>

<dl>
<dd> <h2 style="color:#990099;"> FSL: </h2> </dd>
</dl>

[FSL](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/) offers a comprehensive library of analysis tools for FMRI, MRI and DTI brain
imaging data.
   
An overview of FSL tools can be found [here](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FslOverview). Some of the commonly utilized
tools include [FLIRT](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FLIRT) & [FNIRT](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FNIRT) for linear
and nonlinear registration; [FAST](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FAST) for tissue type segmentation and [MCFLIRT](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/MCFLIRT) for head motion correction.
  
FSL toolbox also comes with FSLView for 3D/4D image, time-series and surface visualization.
   
<dl>
<dd> <br> </dd>
</dl>  

<dl>
<dd> <h2 style="color:#990099;"> SPM: </h2> </dd>
</dl>

[SPM](http://www.fil.ion.ucl.ac.uk/spm/) is an open source software toolkit for analysis of functional
imaging data. The software is a suite of MATLAB functions and subroutines and stands for 'Statistical
Parametric Mapping'. It provides construction and assessment of spatially extended statistical processes
used to test hypotheses about functional imaging data. SPM is a free but copyright software distributed under
GNU General Public License as published by Free Software Foundation.

<dl>
<dd> <br> </dd>
</dl>

<dl>
<dd> <h2 style="color:#990099;"> MATLAB: </h2> </dd>
</dl>
   
MATLAB is a high level language and interactive environment. The matrix based language is a natural way to express computational
mathematics. [MATLAB](https://au.mathworks.com/products/matlab/features.html#matlab_is_designed_for_engineers_and_scientists)
offers toolbox for signal and data analysis; in addition to visualization tools for custom plots, curve fitting and GUI development.
   
A variety of imaging algorithms and data analysis tool have been developed using MATLAB software. As also 
demonstrated in the example for SPM and MATLAB data conversion. It offers object oriented programming.
  
<dl>
<dd> <br> </dd>
</dl>

<dl>
<dd> <h2 style="color:#990099;"> Python: </h2> </dd>
</dl>
   
Python is a friendly and easy to learn software language. It can run on almost all major operating systems
In addition it can also be used for either web-based or stand-alone applications. [Python](https://ww.python.org/)
is object oriented language and can support both multi-processing and multi-threading.
   
Some of its features include dynamic type system, automatic memory management and it is supported by both a comprehensive
standard library and open-source contributions by its users.
   
[Python](https://ww.python.org/) license is administered by Python Software Foundation and is an open-source license.
   
At CAI we use [PyCharm](https://www.jetbrains.com/pycharm/) as our choice of Python interpreter which further allows us to interface
other software toolbox such as Nipype, FreeSurfer, FSL etc.
   
PyCharm offers intelligent code assistance, version controls with Git or SVN in addition to web-development and a powerful debugger
which makes it very attractive for use. 
   
At CAI we use python for efficient and clean implementation of our [Nipype](http://nipype.readthedocs.io/en/latest/) workflows for
image analysis.
   
An example of use of python algorithm for building the human brain atlas can be found at [volgenmodel-nipype](https://github.com/CAIsr/volgenmodel-nipype)
   
<dl>
<dd> <br> </dd>
</dl> 

<dl>
<dd> <h2 style="color:#990099;"> FreeSurfer: </h2> </dd>
</dl>
   
[FreeSurfer](http://freesurfer.net/) is an opens source software for processing and analysing human brain images. 
Some of its features include, image registration, subcortical & cortical segmentation, cortical thickness estimation, fMRI analysis,
tractography etc.
  
At CAI, FreeSurfer is often used for subcortical & cortical segmentation.
   
<dl>
<dd> <br> </dd>
</dl>

<dl>
<dd> <h2 style="color:#990099;"> Mipav: </h2> </dd>
</dl>

[MIPAV](https://mipav.cit.nih.gov/)(Medical Image Processing, Analysis, and Visualization) software
allows quantitative analysis and visualization of medical images of various modalities. It also
provides standard user-interface (UI) and remote sharing of data via internet.

It is a Java based application and hence object-oriented with java plug-in for further extension.
It supports industry-standard image formats such as DICOM, TIFF, Analyze and RAW.

<dl>
<dd> <br> </dd>
</dl>
   
<dl>
<dd> <h2 style="color:#990099;"> Nipype: </h2> </dd>
</dl>
   
Nipype is an open source neuroimaging toolbox based on python language which enables Neuroimaging
in python pipelines and interfaces. 
  
Nipype provides an environment for interactive exploreation of different software packages such as 
ANTS, SPM, FSL, FreeSurfer, Camino, MRtrix, MINC etc. It enables researchers to design imaging workflow 
using multiple software packages of their choice. This facilitates collaboration with different packages
and interaction with different and specialized imaging tools offered by them. The user can select their
choice of software tool to perform certain imaging tasks specific to their applications and design their 
own workflow. 
   
Advantages of [Nipype](http://nipy.org/nipype/0.10.0/) as also stated on their website is given as below,

* easy interaction with multiple softwares 

* combine specialized tools or functions of different software packages
  
* develop new workflows
  
* faster data processing using parallel cores/machines
  
* reproducible research and sharing with community
  
The nipype workflow is a streamlined process which uses several nodes to accomplish the desired 
imaging task. This workflow or pipeline is constructed using multiple nodes where each node provides a 
specific imaging task that is part of the mapflow of the imaging pipeline. A node will have a defined
inputs and outputs and desired workflow is established by connecting these nodes to carry out unique 
function within the pipeline.
  
<dl>
<dd> <br> </dd>
</dl> 

<dl>
<dd> <h2 style="color:#990099;"> Docker: </h2> </dd>
</dl>
   
At CAI, for the purposes of reproducible research we have dockerized our atlas building toolbox into
Docker container, so that people can execute and replicate the study and also use it for further 
testing and analysis with their own datasets. The docker version of the human brain atlas using python,
minc and nipype can be found [here](https://github.com/CAIsr/volgenmodel-nipype).
  
The user should have already installed [Docker](https://docs.docker.com/) on their container and clone the necessary repositories
from [CAISr](https://github.com/CAIsr/volgenmodel-nipype) github to execute the atlas.
  
Docker helps to run applications in a securely isolated container. It is able to package all its
dependencies and libraries. Containers are lightweight, one can run a variety of applications 
that all rely of different libraries and environments on a single kernel. 




