# Research-Code-Portability-Tutorial
---

## Description 
This repository will review the steps to build a Singularity container from a definition file and implement it into scripts. Furthermore, this repository also covers developing and implementing a configuration file into scripts. Singularity containers and configuration files aim to make coding workflows more efficient and portable. Integrating these features into scripts will be a significant time-saver for research and data analysis work. 

These tutorials are Jupyter Notebooks; some features, such as internal links, may not render in GitHub correctly. Please copy and paste the notebook URL into [nbviewer](https://nbviewer.org/) for full compatibility. 

---

## Changes due to continuum.io legal issues

Recently the creator of anaconda has started demanding payment from academic research group for the continued use of the non-free repositories. To work around this we have moved to miniforge3 instead of miniconda3. Miniforge3 is a srop in replacement for miniconda3, but avoids the legal issues.

In the [Creating-a-Singularity-Container-for-a-Conda-Environment](https://github.com/CW3E/Research-Code-Portability-Tutorial/blob/main/Creating-a-Singularity-Container-for-a-Conda-Environment.ipynb) instructions it mentions the use of miniconda3. Those instructions will be corrected at a different time, for now what you should know is instead of using the provided Singularity definition file instead use the template available at **_/data/projects/containers/miniconda/Singularity.template.def_**. 

Following the rough instuctions found above do:
```
cd /path/to/my/project/
cp /data/projects/containers/miniconda/Singularity.template.def ./Singularity.def
# Optional, select a different base OS by uncommenting lines 3 or 4 and commenting out line 5.
# You likely want to use the default Rocky Linux 9
conda list -p /path/to/my/project/environment --explict > requirements.txt
apptainer build MyContainer.sif Singularity.def
```
