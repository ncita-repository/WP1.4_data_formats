# WP1.4_data_formats
### NCITA Repository Unit Work Package 1.4: XNAT-OHIF viewer - Data formats
Specific repositories and projects of the form WP1.x-y are for specific second-level, viewer-related work packages in the NCITA Repository Unit strategy.

The primary aim of WP1.4 is to document and create code related to the use of different data formats used in XNAT and the OHIF image viewer. 

The NCITA Repository Unit site as a whole is at an early stage of the life cycle and does not currently have a formal structure of documentation releases. Please bear with us: things will become more organised as the NCITA project gets into gear! Note that the ICR also releases code related to the XNAT-OHIF image viewer at https://bitbucket.org/icrimaginginformatics/. 

### NIfTI

NIfTI, the [Neuroimaging Informatics Technology Initiative](https://nifti.nimh.nih.gov/), defines two data formats: NIfTI-1 and NIfTI-2. These are both aimed at storing 3D and 4D data with the minimum possible overhead. The formats contain virtually no metadata at all. Relationships between data contained in the files are defined by their relative location on the filesystem and with sidecar JSON. BIDS, [Brain Imaging Data Structure](https://bids.neuroimaging.io/), defines one method of organising these data.

Internal representation of each data point can have one of many integer and floating point types, which one is in use is stored in the minimal header. NIfTI files are often gzipped to save space.

NIfTI files are in widespread use. They are proving popular as simple to use mask storage for machine learning research. NVIDIA's Clara uses NIfTI as one of its file formats. Even though there are facilities to add metadata relating to the DICOM images from which NIFTI data were derived, the lack of required mandatory data and the existence of large quantities of legacy data not conforming to standards such as BIDS create significant difficulties for implementation within the XNAT-OHIF viewer environment. It is not straightforward, for example, during bulk upload to determine the association of different NIFTI images with each other, or which NIFTI images are masks associated with either DICOM or other NIFTI base images.

One of the aims of WP1.4 is to provide convenient tools to allow both user-driven (GUI) and batch (command-line) upload of NIFTI data to XNAT.

### NRRD

NRRD, [Nearly Raw Raster Data](http://teem.sourceforge.net/nrrd/), is another low overhead format aimed at storing 3D and 4D data for image processing and visualisation. Like NIfTI, NRRD contains no metadata to define relationships between data, but is widely used, for example in [3D Slicer](www.slicer.org).
