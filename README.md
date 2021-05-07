# musurf-reader
## Functions for importing µsurf confocal microscope binary file formats

### µsurf File Formats
Type | Function 
------------ | -------------
.orginal   | Contains measurement properties as well as height and intensity data. Subimages were stitched to a whole image.
.nms       | Same structure as .orginal, but contains the data changed by the µsoft software (filtering, fitting, ...). Same content as .orginal when no post-processing took place.
.sms       | Contains a list of the measurement's subimages, each containing height and intensity information.
.smt       | Same content as .sms file, but signals the microscope µsoft software to stitch the subimages on file import.
.smi       | Contains image stitching information
.txt       | Human-readable height data as ASCII table
<br/>

### Supported File Features
Support for OM_MS_2.0 file versions only.
<br/>
<br/>

Type | Supported Features
------------ | -------------
.orginal <br /> .nms   | x and y coordinates, height and intensity data 
.sms <br /> .smt       | x and y coordinates, height and intensity data for each individual image
.smi       | (experimental) image count in x and y direction as well as the image overlap parameter
.txt      | x and y coordinates and height data
<br/>

### Usage
Function names consist of `read` + `file extension`  
  
**Example:**
```python
import musurf_reader as mur

# load whole measurement
x, y, image, intensity = mur.readnms("D:\Measurement.nms")

# or load individual images in a measurement
x, y, images, intensities = mur.readsms("D:\Measurement.sms")

```
<br/>
  
### Required Packages
`numpy, struct`
  
Tested with Python 3.8 and PyCharm 2020.3.2
