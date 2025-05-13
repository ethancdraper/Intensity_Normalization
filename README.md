# Intensity_Normalization

Comparing automated intensity normalization techniques for white matter hyperintensity quantification

Authors: Ethan C. Draper, Rachel Wagner, & Udunna C. Anazodo

Montreal Neurological Institute, McGill University

Please see the references file and ensure all tools, data, and previous work are appropriately credited.


Installation
  Install FSL: https://fsl.fmrib.ox.ac.uk/fsl/docs/#/install/index 
  Install R: https://rstudio-education.github.io/hopr/starting.html
  Install HypperMapp3r: https://hypermapp3r.readthedocs.io/en/latest/install.html
    - Note HypperMapp3r was built on an older version of python, so in 2025 on the Cedar cluster of Compute Canada, I had to:
    1. pip install -e ".[hypermapper_gpu]"
    2. Edit setup.py to a current version of tensorflow and keras
  Download data: The present study used the following data sources:
    1. https://fcon_1000.projects.nitrc.org/indi/retro/SIMON.html
    2. https://dataverse.nl/dataset.xhtml?persistentId=doi:10.34894/AECRSD
    3. https://adni.loni.usc.edu/data-samples/adni-data/
    For alternative data, each participant requires T1w and T2 FLAIR scans.

The following protocol outlines each step of this analysis: https://www.protocols.io/private/9A1CEC97116611F0B4460A58A9FEAC02
Alternatively, the analysis was performed by:
1. Preprocessing T1 data
2. Preprocessing T2 data
3. Performing intensity normalization on T1 data
4. Performing intensity normalization on T2 data
5. Running tissue segmentation on T1 data
6. Running tissue segmentation on T2 data
7. Linear registration of T2 data to T1 data
8. Running HyperMapp3r to segment WMH 
