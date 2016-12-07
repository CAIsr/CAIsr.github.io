---
layout: page
title: Data Conversion
description: Overview of data conversion and types
---

<dl>
<dd> <h2 style="color:#990099;"> Dicom to Minc: </h2> </dd>
</dl>
dcm2mnc from the [minc package](https://github.com/BIC-MNI/minc-toolkit-v2) can be used. Make sure you have minc sourced in your .bashrc: source /data/lfs2/software/ubuntu14/minc-itk4-1.9.11-20160202/minc-toolkit-config.sh
<br>

<dl>
<dd> <br> </dd>
</dl>
```bash
dcm2mnc [options] file1 file2 file3 ... destdir
```  
   
<dl>
<dd> <h2 style="color:#990099;"> Dicom to Nifti: </h2> </dd>
</dl>
Chris Rorden's [dcm2nii](https://www.nitrc.org/projects/mricron) works well for this job:
<dl>
<dd> <br> </dd>
</dl>
```bash
dcm2nii <options> <sourcenames>
```  

<dl>
<dd> <h2 style="color:#990099;"> SPM & MATLAB: </h2> </dd>
</dl>
[SPM](http://www.fil.ion.ucl.ac.uk/spm/) has a converter from dicom to Nifti build in. After starting SPM, click SPM -> Util -> DICOM Import 



<dl>
<dd> <h2 style="color:#990099;"> Others: </h2> </dd>
</dl>
Other conversions could be done using [mri_convert](https://surfer.nmr.mgh.harvard.edu/pub/docs/html/mri_convert.help.xml.html) included in [FreeSurfer](https://surfer.nmr.mgh.harvard.edu/fswiki). Make sure to source FreeSurfer: 
<dl>
<dd> <br> </dd>
</dl>
```bash
export FREESURFER_HOME=/data/lfs2/software/ubuntu14/freesurfer-v6beta-2016-05-14-centos6
source $FREESURFER_HOME/SetUpFreeSurfer.sh
```
then run mri_convert:



```shell

mri_convert [options] <in volume> <out volume>

```

### Data Storage

<dl>
<dd> <h2 style="color:#990099;"> Imagetrove: </h2> </dd>
</dl>

At CAI we have a comprehensive data storage system available with help of [Imagetrove](https://projects.ands.org.au/id/ERIC08). It is a web-based system used for
storing data generated at CAI with help of different imaging modalities. It also provides easy access of this data to our collaborators in addition to a secured environment for data sharing.

Further information for Imagetrove can be found [here]()


