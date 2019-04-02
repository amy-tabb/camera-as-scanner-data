# camera-as-scanner-data

Comments/Bugs/Problems: amy.tabb@ars.usda.gov

Example data to use with comparion repository, [amy-tabb/camera-as-scanner](https://github.com/amy-tabb/camera-as-scanner)

Another companion repository is [amy-tabb/aruco-pattern-write](https://github.com/amy-tabb/aruco-pattern-write)

~March 2019.  


# How and when to cite this work

This README file is to accompany code produced by Amy Tabb as a companion to a paper.  The paper provides a full protocol to use the code:

To be announced.  Email for a draft.


Code release citation:

@misc{tabb2019code_using,
	title = {Code from: {Using} cameras for precise measurement of two-dimensional plant features},
	url = {https://data.nal.usda.gov/dataset/code-using-cameras-precise-measurement-two-dimensional-plant-features},
	urldate = {2019-04-01},
	publisher = {Ag Data Commons},
	author = {Tabb, Amy},
	year = {2019},
}


If you use this code in project that results in a publication, please cite at a minimum the paper above.  Otherwise, there are no restrictions in your use of this code.  However, no guarantees are expressed or implied.

# Underlying ideas

Computer vision explanation: The code in [amy-tabb/camera-as-scanner](https://github.com/amy-tabb/camera-as-scanner) takes an image of an object on top of an aruco calibration pattern, calibrates the camera using the detected aruco information as well as EXIF tag information, and undistorts and computes the homography from the current location of the aruco calibration pattern in the image to its location in physical space.  Then the image is warped to match the coordinate system of the aruco coordinate system, scaled by a user-selected parameter. 

This dataset provides examples of properly-formatted input images and accompanying text files, as well as a successful run where the option of writing intermediate results has been selected.  Details about how to format the directories is found in the README of [amy-tabb/camera-as-scanner](https://github.com/amy-tabb/camera-as-scanner). 

- `iphone6`. is a directory of input files using the camera of a iPhone 6 cellular phone. 
- `iphone6_results`. is the directory of results created from running [amy-tabb/camera-as-scanner](https://github.com/amy-tabb/camera-as-scanner) on `iphone6`.
- `CanonEOS60D`. is a directory of input files using a DSLR camera from Canon, model name EOS 60D.
- `CanonEOS60D_results.` is the directory of results created from running [amy-tabb/camera-as-scanner](https://github.com/amy-tabb/camera-as-scanner) on `CanonEOS60D`.

See the `Write directory format` section of [amy-tabb/camera-as-scanner](https://github.com/amy-tabb/camera-as-scanner)'s README for details of all of the files; briefly for this example, `warped_ORIGINALFILENAME.jpg` is the original image, transformed such that 10 pixels corresponds to 1 millimeter on the two dimensional plane of the calibration pattern.
