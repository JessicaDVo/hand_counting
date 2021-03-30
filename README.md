# hand_counting project using running average calculation and Convex Haul algorithm.

Before we start the project, it is always good to have a good background of domanin knowledge and math which stand behind the conding lines. 
This project has two main parts, including hand segmentation and fingers counting. 
1. Hand segmentation part consits of 4 steps: manually selecting ROI, computing the running average background value of 60 frames, detecting hand and applying the threshold value for hand isolation. Threshold value highly depends on how uniform the color and overall shape inside the ROI.
2. Finger counting part will use Convex Haul to draw polygon around the hand, then we compute the hand center and its euclidean distances to extreme points (top, left, right, bottom). From then, we draw the circle which center is the hand center, and radius is equal to 90% of the longest enclidean distance. Any point that out of the circle but still within 2 times of circle circumfence is considered as an extended finger. This is how the finger counting works.

# Background subtraction for object tracking
Method: running average – the video sequence is analyzed over a particular set of frames.
1. The objective of the program is to detect active objects from the difference obtained from the reference frame and the current frame.
2. We keep feeding each frame to the given function, and the function keeps finding the averages of all frames.
3. Then we compute the absolute difference between the frames.

# Convex Haul for counting fingers
1. Convex Haul draws a polygon by connecting points around the most external points in a frame. In our case, this set of points is our threshold image of hand and the external contour information
2. Calculate the most extreme points (top, left, right, bottom)
3. Use their intersection to estimate the center of the hand
4. Calculate the distance for the point furthest away from the center
5. Use a ratio of that distance to create a circle (center = center of the hand, radius = % of further distance)
6. Any point out of circle and faraway enough from the ROI is considered as an extended finger.



# Require python libraries:
conda install opencv, conda install numpy, conda install scikit-learn
