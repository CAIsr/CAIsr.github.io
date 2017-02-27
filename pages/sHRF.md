---
layout: page
title: sHRF
description: supplementary Hemodynamic Response Function modelling based on fMRI
---

sHRF is a toolkit representing supplementary Hemodynamic response function for fMRI.

This toolkit is developed by Zuyao Shan and David Reutens.

For in-depth information about the toolkit and methodology involved and publication/material related to this toolbox, please cite the following paper

*'Shan ZY, Wright MJ, Thompson PM, McMahon KL, Blokland GAM, de Zubicaray GI, Martin NG, Vinkhuyzen AE, Reutens DC, 'Modeling of the Hemodynamic Responses
in Block Design fMRI Studies". J of Cerebral Blood Flow & Metabolism. 2013 Nov [paper](https://www.ncbi.nlm.nih.gov/pubmed/24252847)'*

CAIsr [github] (https://github.com/CAIsr/sHRF) provides complete toolbox with source code along with the docker file. Further information regarding the toolbox can be obtained from the readme file.

<dl>
<dd> <br> </dd>
</dl>

![alt text](/images/screenshot_sHRF.png)

<dl>
<dd> <br> </dd>
</dl>

Installation prerequisites: 

1. You will need MATLAB toolbox already installed in your computer.

2. You will also need a copy of the sHRF toolbox

3. SPM8 

You need to download and unzip the sHRF toolbox on your computer. The path to this toolbox should be added to MATLAB path by using 'addpath'
Make sure you have spm8 already insatlled on your computer or you can download and install SPM8 on your computer from [here](http://www.fil.ion.ucl.ac.uk/spm/software/download/)
You will be asked to complete an online registration form for SPM. Once you have downloaded SPM8 ensure that it too is added to the MATLAB path.
Note: This toolkit has been tested with only SPM8. If using docker, no need to download spm8 as it will be carried out by docker image.

An example data is already provided with the toolkit. It includes fMRI time-series provided as .mat file.

Once you start matlab ( with all necessary paths added), type 'sHRF_TC'; no commas. This will open another UI.

The user-interface (UI) will ask for a directory where input data is stored.
It will also ask for location for storage of results generated.
It will then ask for program parameters such as, repetition time, duration etc. Either enter your own choice or use 
the default provided with 'README.txt' with sHRF toolbox.
Select RUN.
The toolkit should generate a display window with your results.
These results will also be stored in .txt file in the storage location provided by you.

<dl>
<dd> <br> </dd>
</dl>

![alt text](/images/sHRF2.png)

<dl>
<dd> <br> </dd>
</dl>

If you wish to test the toolkit with docker on linux computer:

1. Download or git clone the sHRF repository.

   ``` 
   git clone https://github.com/CAIsr/sHRF
   ```
   
2. enter the directory where docker file is located. If you are using command prompt

   ```
   cd sHRF/Docker
   ```
   
3. build the image using

   ```
   docker build --no-cache -t='ia/sHRF' .
   ```
   
4. run the docker container as follows,

   ```
   docker run -it -v "....location of your MATLAB.....":/usr/local/MATLAB/host -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY ia/sHRF
   -r "addpath('/opt/SPM/spm8'), addpath('/opt/sHRF/sHRF_v1.2')"
   ```
   
5. once the matlab gui opens, straight away type 

   ```
   sHRF_TC
   ```

6. This will open another UI and prompt you for inputs as mentioned above.

Note: 

1. Above test for docker has only been conducted for linux OS. In order to run the sHRF toolkit with docker. 
   You need to have already insatlled Docker for linux on your computer.
   You will also have MATLAB install on the host OS, in this case it will be Linux.
   The docker file has been inspired from the following: 1 https://blog.jessfraz.com/post/docker-containers-on-the-desktop/ 2. https://hub.docker.com/r/ninjaben/matlab-support/ 

Note: in docker run command,

1. -v : asks the user to mount the MATLAB directory within the container, as MATLAB is a licensed software and cannot be distributed freely.
        As a result each user has to prvoide their own licensed MATLAB to run the toolbox. This is not transferable within different OS or computers.

2. -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY: are used to open the user GUI within a container for a linux OS. This may not be
      required if not using docker to run the toolkit.


<dl>

<dd> <h3 style="color:#7d1b7e;"> Contributors: </h3> </dd>

<dd> <blockquote> <div style="background-color:#ddccff; font-style:normal; font-family:Times New Roman;"> <br>

Zuyao Shan <br>
<br>
Wright MJ <br>
<br>
Thompson PM <br>
<br>
McMahon KL <br>
<br>
Blokland GAM <br>
<br>
de Zubicaray GI <br>
<br>
Martin NG <br>
<br>
Vinkhuyzen AE <br>
<br>
David Reutens <br>
<br>

</div></blockquote> </dd>

</dl>


