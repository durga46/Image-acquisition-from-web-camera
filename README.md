## EX.NO:02
## Date:07.04.2022
# <p align="center">  Image-Acquisition-from-Web-Camera</p>

## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)
<br>

### Step 2:
Write the captured image using cv2.imwrite("JayashreeRao.jpg",frame)
<br>

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
<br>

### Step 4:
display the image until the loop gets over
<br>

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
<br>
<br>

## Program:
``` Python
### Developed By: DURGADEVI P
### Register No: 212220230011

## i) Write the frame as JPG file
import cv2

videocaptureobject = cv2.VideoCapture(0)

while(True):
    ret,frame = videocaptureobject.read()
    cv2.imwrite("Pic1.jpg",frame)
    result = False 
videocaptureobject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllwindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[height//2:, width//2:] = smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows(



## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllwindows()
```
</br>
</br>
</br>
</br>
</br>
</br>
## Output
### i) Write the frame as JPG image
![output](./static/img/p1.jpeg)
</br>
</br>


### ii) Display the video
![output](./static/img/p2.jpeg)
</br>
</br>


### iii) Display the video by resizing the window
![output](./static/img/p3.jpeg)
</br>
</br>



### iv) Rotate and display the video
![output](./static/img/p4.jpeg)
</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
