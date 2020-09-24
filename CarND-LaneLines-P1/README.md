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
---------------------------------------------------------------------------------------------------------------------------
## Used Functions

Grayscale: Returns a gray scaled version of the input image using cv2.cvtColor method.

Gaussian Blur : Applies a Gaussian blur to the provided image using cv2.GaussianBlur method.

Canny Transform: Use a Canny transformation to find edges on the image using cv2.Canny method.

Region of Interest: Eliminate parts of the image that are not interesting for lane detection

Hough Line Transform: Use a Hough transformation to find the lines on the masked image using cv2.cv2.HoughLinesP. It also adjust a line to the set of lines returned by the Hough transformation in order to have a clearer-two-lines representation of the road lines using np.polyfit method.

Weighted Image: Merges the output of hough transform with the original image to represent the lines on it.

---------------------------------------------------------------------------------------------------------------------------
## Images Generated from Pipeline

![f](https://github.com/csharpshooter/UDA-SDCND/blob/master/CarND-LaneLines-P1/test_images/output/test_combined.png)
---------------------------------------------------------------------------------------------------------------------------
## Videos Generated from Pipeline

[![Solid White Right Generated Video](https://github.com/csharpshooter/UDA-SDCND/blob/master/CarND-LaneLines-P1/test_videos_output/solidWhiteRight.mp4)

[![Solid Yellow Left Generated Video](https://github.com/csharpshooter/UDA-SDCND/blob/master/CarND-LaneLines-P1/test_videos_output/solidYellowLeft.mp4)

----------------------------------------------------------------------------------------------------------------------------
## Shortcomings
I have observed some problems with the current pipeline:

* In the challenge video at around second 5 the lane is covered by some shadow and I believe my code fails to detect it. I am trying to fix this issue by applying the HSL color filtering as another pre-processing step but currently it is not completed.
* Straight lines do not work when there are curves on the road.
* Hough Transform is tricky to get right with its parameters. I am not sure I got the best settings.

----------------------------------------------------------------------------------------------------------------------------
## Future Improvements
* One approach would like to implement a lane detector whch would consider the data from previous input frames.
* Also would like to be better identify lanes, I we can convert image to HSV and HSL format for preprocessing
* One further step to explore would be to calculate the weighted average of line coefficients , giving a higher weight to more recent coefficients as they belong to more recent frames; I believe frame locality would play a critical role in getting near-perfect lines on video.
* In the future, I also plan to use deep learning to identify lanes and compare those results against what I obtained with a pure computer vision approach.

#### All code is available on Github.
----------------------------------------------------------------------------------------------------------------------------


