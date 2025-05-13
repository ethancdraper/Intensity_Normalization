# Intensity_Normalization

Comparing automated intensity normalization techniques for white matter hyperintensity quantification

Authors: Ethan C. Draper, Rachel Wagner, & Udunna C. Anazodo

Montreal Neurological Institute, McGill University

Please see the references file and ensure all tools, data, and previous work are appropriately credited.

Installation
  Install FSL: https://fsl.fmrib.ox.ac.uk/fsl/docs/#/install/index 
  Install HypperMapp3r: https://hypermapp3r.readthedocs.io/en/latest/install.html
    - Note HypperMapp3r was built on an older version of python, so in 2025 on the Cedar cluster of Compute Canada, I had to:
    1. pip install -e ".[hypermapper_gpu]"
    2. Edit setup.py to a current version of tensorflow and keras
    
  Download data: The present study used the following data sources:
    1. https://fcon_1000.projects.nitrc.org/indi/retro/SIMON.html
    2. https://dataverse.nl/dataset.xhtml?persistentId=doi:10.34894/AECRSD
    3. https://adni.loni.usc.edu/data-samples/adni-data/ (the subset of ADNI participants analyzed in this study have been listed)
    For alternative data, each participant requires T1w and T2w or T2 FLAIR scans.

It is assumed that all data is in NIFTI format. If in another format, this must be converted before using the pipeline. If in DICOM format, one tool is: https://github.com/rordenlab/dcm2niix

If manual annotations are available and will be compared to HyperMapp3r outputs, please also install FreeSurfer: https://surfer.nmr.mgh.harvard.edu/fswiki/DownloadAndInstall

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
9. *Optional: If manual annotations are available and will be compared to HyperMapp3r outputs, perform Dice and Jaccard Index.

Acknowledgement:
The research team appreciates funding from the following sources which supported the first author: the Quebec Research Fund - Health (Master’s Training Scholarship; 2024 - 2025), the Canadian Institute of Health Research (Master’s Graduate Scholarship; 2023 - 2024), and the Natural Sciences and Engineering Research Council of Canada (Discovery Grant; 2024 - 2025). This research was enabled in part by support provided by the Digital Research Alliance of Canada (alliance​can​.ca). 
