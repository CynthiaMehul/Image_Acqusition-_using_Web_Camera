
### Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Import required libraries.
<br>

### Step 2:
Create an instance of video capture object and capture the video through your webcam.
<br>

### Step 3:
Display the image and then resize the window to display the smaller sized image. 
<br>

### Step 4:
Rotate the image and display it.
<br>

### Step 5: 
End the program.
<br>

## Program:

``` Python
### Developed By: Cynthia Mehul J
### Register No: 212223240020

## i) Write the frame as JPG file

import cv2
import matplotlib.pyplot as plt
obj = cv2.VideoCapture(0)
while (True):
    ret,frame = obj.read()
    cv2.imwrite("img.jpeg",frame)
    result=False
obj.release()
cv2.destroyAllWindows()

## ii) Display the video

img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('PIC',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
</br>
![image](https://github.com/user-attachments/assets/6d5e8b5d-45b9-4978-a2e0-3728363cca0f)
</br>

### ii) Display the video
</br>
![image](https://github.com/user-attachments/assets/658a9af7-68a6-4acb-963a-029fce5c2cd4)
</br>

### iii) Display the video by resizing the window
</br>
![image](https://github.com/user-attachments/assets/99d7a551-7765-4384-9c25-da2e54c170ad)
</br>

### iv) Rotate and display the video
</br>
![image](https://github.com/user-attachments/assets/e8a0ab32-0738-4ce1-a631-e8c0cc6dc35e)
</br>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
