# Drowesiness-detection for drivers (Using opencv,dlib)
Drowsiness detection using opencv and dlib
the detection algorithm detects drivers drowsiness using the following paramerts

1. Detection of yawning 
2. Detection of heavy blinking
3. Detection of Head Bobbing (Both sideways and down)
4. Counts blinks

*I have created a virtual env and uploaded the entire thing as there were many libs to be installed


![1](/Images/ss.png)
## Yawning detection
![2](/Images/IMG-9033.jpg)
## Bobbing detection
![3](/Images/IMG-9031.jpg)


## Principles behind algorithm 

1. Yawning 
Yawning detection is done by first  marking specific points on lips and traking them.The code is specificly marked with 6 point on the lips namely two on corners and 4 on lower and upper lip. Sum Euclidean distance between lower and upper lip point which is then divied by distance between corners of lips to give a ratio of open mouth. If the ratio is greater then 0.35 for 3 seconds that is seen to be a person yawning.

2. Heavy blinking 
Blinking detection is done similiar to yawning detection just the ration and time differs to be 0.10 and 0.7s. For heavy blinking detection for perticular time intervals(15 seconds) number of blinks and duration of blinks are recorded.We have set a threshold for heavy blnking to be 10 blinks in 15 seconds each blink to be almost 0.5s long.

3. Head Bobbing detection 
For this the algorithm continuesly detects the difference of specific points in the x-y cordinate systems. The algorithm specificaly took two points the chin and nose we recorded this points in two frames that differs 15 frames from each other. We calculated euclidean distance between this points and formed vectors that then gives direction and magnitude of movement.Thresholds were set for bot horzontal and vertical directions that helped us detect the final movement of head.
