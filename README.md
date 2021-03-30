# hand_counting
# This is the capstone project of the computer vision course in Udemy.
Before we start the project, it is always good to have a good background of domanin knowledge and math which stand behind the conding lines. 
This project has two main parts, including hand segmentation and fingers counting. 
1. Hand segmentation part consits of 4 steps: manually selecting ROI, computing the running average background value of 60 frames, detecting hand and applying the threshold value for hand isolation. Threshold value highly depends on how uniform the color and overall shape inside the ROI.
2. Finger counting part will use Convex Haul to draw polygon around the hand, then we compute the hand center and its euclidean distances to extreme points (top, left, right, bottom). From then, we draw the circle which center is the hand center, and radius is equal to 90% of the longest enclidean distance. Any point that out of the circle but still within 2 times of circle circumfence is considered as an extended finger. This is how the finger counting works.

Require python libraries:
conda install opencv
conda install numpy
conda install scikit-learn
