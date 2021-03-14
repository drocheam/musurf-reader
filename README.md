# musurf-reader
## Functions for importing µsurf confocal microscope binary file formats

Supports only the OM_MS_2.0 file versions.
  

### Supported Formats:
Format | Supported Features
------------ | -------------
.nms       | x and y coordinates, image and intensity data
.orginal   | same file structure as .nms
.txt      | x and y coordinates and image data
.sms       | x and y coordinates, image and intensity data for each individual image
.smt       | same file structure as .sms
.smi       | (experimental) image count in x and y direction as well as the overlap parameter
  

### Usage
Function names consists of `read` + `file extensions`  

**Example:**
```python
import musurf_reader as mur

# load whole measurement
x, y, image, intensity = mur.readnms("D:\Measurement.nms")

# or load individual images in a measurement
x, y, images, intensities = mur.readsms("D:\Measurement.sms")

```
  

### Required Packages
`numpy, struct`

Tested with Python 3.8 and PyCharm 2020.3.2
