# LipoRadiomicsFeatures
Script to compute the features used in the paper: Vos, M., Starmans, M. P. A., Timbergen, M. J. M., van der Voort, S. R., Padmos, G. A., Kessels, W., ... & Visser, J.J.. (2019). Radiomics approach to distinguish between well differentiated liposarcomas and lipomas on MRI. The British journal of surgery, 106(13), 1800..

## Installation
The feature extraction is done using Python2, and has been tested on version 2.17.11.
Only the PREDICT package, version 2.1.3, and the subsequent dependencies are required
for the feature extraction, which can be installed through pip:

    pip install "PREDICT==2.1.3"

## Usage
The ExtractFeatures.py script can be used to extract all features. We provided
you with the exact same configuration file that was used in the study. The
script can be easily modified to use your own data instead of the
provided example data and requires:

1. An image in ITK Image format, e.g. .nii, .nii.gz, .tiff, .nrrd, .raw
2. A segmentation in ITK Image format.
3. Optionally, metadata in DCM format

Extracting the features from the example data should take less than 10 seconds.
Using a larger image and/or mask may result in a longer computation time.

## Known Issues

### Pyradiomics
The PyRadiomics package we use requires numpy in the installation, hence
you may need to install numpy manually beforehand:

    pip install "numpy==1.16.4"

From version 2.2.0 and above, PyRadiomics removed a function and might throw
this error:

'''AttributeError: 'module' object has no attribute "RadiomicsFeaturesExtractor"'''

This can be overcome by downgrading to version 2.1.2:

    pip install "pyradiomics==2.1.2"

### Missingpy
Missingpy verion 0.2.0 may throw an ascii error: in that case, manually
remove and reinstall the package:

    pip uninstall missingpy
    pip install "missingpy==0.2.0"
