---
layout: page
title: Data Conversion
description: Overview of data conversion and types
---

<dl>
<dd> <h2 style="color:#990099;"> Dicom to Minc: </h2> </dd>
</dl>
dcm2mnc from the minc package can be used. Make sure you have minc sourced in your .bashrc: source /data/lfs2/software/ubuntu14/minc-itk4-1.9.11-20160202/minc-toolkit-config.sh
```python
dcm2mnc [options] file1 file2 file3 ... destdir
```  
   
<dl>
<dd> <h2 style="color:#990099;"> Dicom to Nifti: </h2> </dd>
</dl>
Chris Rorden's dcm2nii works well for this job:
```bash
dcm2nii <options> <sourcenames>
```  

<dl>
<dd> <h2 style="color:#990099;"> SPM & MATLAB: </h2> </dd>
</dl>
SPM has a converter from dicom to Nifti build in. After starting SPM, click SPM -> Util -> DICOM Import 



<dl>
<dd> <h2 style="color:#990099;"> Others: </h2> </dd>
</dl>
Other conversions could be done using mri_convert included in FreeSurfer. Make sure to source FreeSurfer: 
```bash
export FREESURFER_HOME=/data/lfs2/software/ubuntu14/freesurfer-v6beta-2016-05-14-centos6
source $FREESURFER_HOME/SetUpFreeSurfer.sh
```
then run mri_convert:
```bash
mri_convert [options] <in volume> <out volume>
```

