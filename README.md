# WP1.4_data_formats

## Formats Used with XNAT

### NIfTI

NIfTI, the [Neuroimaging Informatics Technology Initiative](https://nifti.nimh.nih.gov/), defines two data formats: NIfTI-1 and NIfTI-2. These are both aimed at storing 3D and 4D data with the minimum possible overhead. The formats contain virtually no metadata at all. Relationships between data contained in the files are defined by their relative location on the filesystem and with sidecar JSON. BIDS, [Brain Imaging Data Structure](https://bids.neuroimaging.io/), defines one method of organising these data.

Internal representation of each data point can have one of many integer and floating point types, which one is in use is stored in the minimal header. NIfTI files are often gzipped to save space.

NIfTI files are in widespread use. They are proving popular as simple to use mask storage for machine learning research. NVIDIA's Clara uses NIfTI as one of its file formats.

### NRRD

NRRD, [Nearly Raw Raster Data](http://teem.sourceforge.net/nrrd/), is another low overhead format aimed at storing 3D and 4D data for image processing and visualisation. Like NIfTI, NRRD contains no metadata to define relationships between data.