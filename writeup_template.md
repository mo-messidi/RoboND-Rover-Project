## Project: Search and Sample Return
### Writeup Template: You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

---


**The goals / steps of this project are the following:**  

**Training / Calibration**  

* Download the simulator and take data in "Training Mode"
* Test out the functions in the Jupyter Notebook provided
* Add functions to detect obstacles and samples of interest (golden rocks)
* Fill in the `process_image()` function with the appropriate image processing steps (perspective transform, color threshold etc.) to get from raw images to a map.  The `output_image` you create in this step should demonstrate that your mapping pipeline works.
* Use `moviepy` to process the images in your saved dataset with the `process_image()` function.  Include the video you produce as part of your submission.

**Autonomous Navigation / Mapping**

* Fill in the `perception_step()` function within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()` data (similar to what you did with `process_image()` in the notebook). 
* Fill in the `decision_step()` function within the `decision.py` script with conditional statements that take into consideration the outputs of the `perception_step()` in deciding how to issue throttle, brake and steering commands. 
* Iterate on your perception and decision function until your rover does a reasonable (need to define metric) job of navigating and mapping.  

[//]: # (Image References)

[image1]: ./misc/rover_image.jpg
[image2]: ./calibration_images/example_grid1.jpg
[image3]: ./calibration_images/example_rock1.jpg
[image4]: ./calibration_images/Calibration_image2.png
[image5]: ./calibration_images/Calibration_image3.png
[image6]: ./calibration_images/Calibration_image4.png
[image7]: ./calibration_images/Calibration_image5.png
[image8]: ./calibration_images/Calibration_image0.png
[image9]: ./calibration_images/rover_simulation1.png

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  

You're reading it!

### Notebook Analysis
#### 1. Run the functions provided in the notebook on test images (first with the test data provided, next on data you have recorded). Add/modify functions to allow for color selection of obstacles and rock samples.
The notebook was used for the intial writeup and parameter testing of the functions that will later be added to the perception.py file.

First a perspective transform of the camera image from the robot's perspective to a bird's eye view world perspective was made. A mask used to ensure that only the robots POV is used.

![alt text][image4]

Color thresholds were set to defentiate open terrain, obsticales and collectable rocks.

![alt text][image5]
![alt text][image6]

The robot images were then converted world coordinates and then to robot centric distance + angle coordinates for feedback to the robot again.

![alt text][image7]

### Autonomous Navigation and Mapping

The `perception_step()` function within the `perception.py` script was populated with the functions that were created and tested in the notebook with minor changes so the input is taken and the results are returned to the `Rover()` object.


#### 2. Launching in autonomous mode the rover can navigate and map autonomously

The 'drive_rover.py' script was then run and the Unity Robot in World simulator was started with res: 800x600 and Good graphics quality. A mean FPS of 55 was obtain during the run. After 176 seconds 64.0% of the world was mapped with a fidelity of 63.2% and 5 rock samples with located by the robot.

![alt text][image9]


