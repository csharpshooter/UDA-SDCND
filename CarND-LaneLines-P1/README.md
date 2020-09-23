## Udacity Self Driving Car Nanodegree - Project P1 - Finding Lane Lines on the Road
---------------------------------------------------------------------------------------
## Name : Abhijit Mali
----------------------
## PipeLine 
---------------------------------------------------------------------------------------------------------------------------
In this part, we will cover in detail the different steps needed to create our pipeline, which will enable us to identify and classify lane lines. The pipeline itself will look as follows:

* Convert image to grayscale for easier manipulation
* Apply Gaussian Blur to smoothen edges
* Apply Canny Edge Detection on smoothed gray image
* Trace Region Of Interest and discard all other lines identified by our previous step that are outside this region
* Perform a Hough Transform to find lanes within our region of interest and trace them in red
* Separate left and right lanes
* Interpolate line gradients to create two smooth lines

