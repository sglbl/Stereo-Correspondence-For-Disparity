# Stereo-Correspondence-For-Sparse-Disparity
Implementation of **Stereo Correspondence Algorithm** that Uses Feature Based Methods to Find *Sparse Disparity*

## Feature Based Method That Is Used

 * Sift With Norm L2 Brute Force Matcher
 * ORB With Flann Matcher
 * Canny Edge Feature Detector with Norm Hamming Brute Force Matcher
 -------------------
 
 Data (Sawtooth, Venus, Bull, Poster, Barn 1, Barn 2 images) were taken from http://vision.middlebury.edu/stereo/data/scenes2001/ 
 
 Submission includes report that describes features selected and feature matching algorithm.
 
 ## Algorithm
```python
Create Sift/Orb/Fast_With_Brief object
Turn images into grayscale
if (edgeDetector selected)
  turn grayscale images to edge images with Canny
  Detect keypoints using fast object created above
  Detect descriptors using brief object and keypoints
else
  Detect keypoints and descriptors using object
  
Create matcher object (L2/NORM HAMMING/FLANN)
Call match() / knnMatch() using descriptors on arguments
Find good matches by checking distances of >%70 difference
Call drawMatches() to see the corresponding matches
Create empty disparity map with image height x width

For every match in good Matches
  Get point coordinates from keyPoints
  Find disparity by subtracting xVals of matching points
  Make disparity as eight times absolute value of it
Print implemented disparity map and openCV disparity map
```

Requirements
  * Python version: 3.10.4
  * OpenCV version: 4.5.5
  * Numpy and matplotlib
  
 ## Examples
  Sift With Bf Norm L2
  
  ![image](https://user-images.githubusercontent.com/64928475/175523110-a5871a16-7901-431f-8ed9-0eb0a2ea9e14.png)
  
  Orb With Flann
  
  ![image](https://user-images.githubusercontent.com/64928475/175523299-2b5eca36-e3d4-436d-9dcc-1bc3616a8055.png)
  
  Edge with Fast Brief Norm Hamming
  
  ![image](https://user-images.githubusercontent.com/64928475/175523582-0e419998-002c-49e4-9fb4-6af2ac7a76d7.png)

 
