---
layout: page
title: Volgenmodel-nipype 
description: overview volgenmodel-nipype
---

Volgenmodel-nipype is the port of volgenmodel to nipype. 
It generates atlas based on minimum deformation model.

The program code requires input images in *.mnc* format.

The pipeline is built on nipype framework using python script; as a result it uses Nipype input function
such as *DataGrabber* to read the input files. The remaining functions of the algorithm such as *Resampling*, *vol-centre*
are nodes of the nipype-pipeline as demonstrated in the following section,
  
  
```python
resample = pe.MapNode( interface=Resample(sinc_interpolation=True), 
                       name='resample_' + snum_txt, 
                       iterfield=['input_file', 'transformation']) 
```  
  
  

The user should verify their input data format and working directory before sending it to DataGrabber. As demonstrated *FAST_EXAMPLE_BASE_DIR*
is the path to the input files while *UNI-DEN*/*normStepSize_* is the file type we are calling in this example.
  
  
```python
FAST_EXAMPLE_BASE_DIR = '/data/lfs2/model-mie/controls/'

workflow.base_dir = os.path.abspath(FAST_EXAMPLE_BASE_DIR)

datasource = pe.Node(interface=nio.DataGrabber(sort_filelist=True), name='datasource_mouse') 
datasource.inputs.base_directory = os.path.abspath(FAST_EXAMPLE_BASE_DIR) 
datasource.inputs.template = '*/*UNI-DEN*/*normStepSize_.mnc' 
```
  
  
The complete method used to generate the model is described in the [paper](http://www.ncbi.nlm.nih.gov/pubmed/25620005) 
and *volgenmodel* program code follows a similar approach in atlas generation.

The imaging pipeline allows users to change the resolution level, step size and fit stages of the model being
generated. The following section of the code should be reset in order to do this.

Resolution can be reset, using
 
  

```python
default_conf = [ {'step': 16, 'blur_fwhm': 16, 'iterations': 4}, 
                 {'step':  8, 'blur_fwhm':  8, 'iterations': 8}, 
                 {'step':  4, 'blur_fwhm':  4, 'iterations': 8}, 
                 {'step':  2, 'blur_fwhm':  2, 'iterations': 4}, 
                ] 
```
  
  
and fit stages can be set using the following section of the code. Note is order to obtain atlas with fine
details, one should maintain a fit stage of atleast 16 iterations. Step size can be reset using *opt['model_min_step]*.
  
  
  
```python
 opt['fit_stages'] = 'lin,lin,lin,0,0,0,0,1,1,1,1,2,2,2,2,3,3,3',
```
  
  
The final model can be found in *'/volgenmodel_final_output'*.

One can also run the above imaging pipeline using Docker.
There is a provision to enable researchers to clone the volgenmodel-nipype repository and run the model with 
help of Docker. The git repository contains dockerfile which is used to build and run the volgenmodel-nipype 
pipeline in the docker container.

For more information on Docker and implementation of CAI imaging pipelines, use the following link.


GitHub link [volgenmodel-nipype](https://github.com/CAIsr/volgenmodel-nipype)
  
  

<dl>

<dd> <h3 style="color:#990099;"> Contributors: </h3> </dd>

<dd> <blockquote> <div style="background-color:#e6e6ff; font-style:normal; font-family:Times New Roman;"> <br>

A. Janke <br>
<br>
S. Bollmann  <br>
<br>
C. Hamalainen <br>
<br>
</div></blockquote> </dd>

</dl>


  
  
  



