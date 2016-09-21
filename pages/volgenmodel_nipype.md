---
layout: page
title: Volgenmodel-nipype 
description: overview volgenmodel-nipype
---

Volgenmodel-nipype is the port of volgenmodel to nipype.
It creates nonlinear models from a series of input MINC files

Requires input images in .mnc format.

The pipeline is built on nipype framework with python script, as a result it uses DataGrabber to read the input files.
The user should verify their input data format before sending it to DataGrabber.

The method used to generate the model is described in the [paper](http://www.ncbi.nlm.nih.gov/pubmed/25620005) and is similar
to volgenmodel mentioned previously.

The final model can be found in '/volgenmodel_final_output'.

The imaging pipeline allows users to change the resolution level and step size of the model being generated.

There is also a provision to enable researchers to clone the volgenmodel-nipype repository and run the model with 
help of Docker.

GitHub link [volgenmodel-nipype](https://github.com/CAIsr/volgenmodel-nipype)


