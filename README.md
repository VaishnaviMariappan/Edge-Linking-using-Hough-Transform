# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.
### Step2:
Load a image using imread() from cv2 module.
### Step3:
Convert the image to grayscale.
### Step4:
Using Canny operator from cv2,detect the edges of the image
### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.
### Step 6:
Display the image and end the program.

## Program:
```Python
import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("i.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()

edge = cv2.Canny(img,100,200)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()

lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)

for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)
    
plt.imshow(edge)
plt.axis('off')
plt.show()
```
## Output

### Input image and grayscale image
![output](./output1.png)
<br>

### Canny Edge detector output
![output](./output2.png)
<br>


### Display the result of Hough transform
![output](./output3.png)
<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
