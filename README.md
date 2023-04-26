# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
# Step 1 :
Read image and convert it to grayscale image.

# Step 2 :
Find the edges in the image using canny detector and display.

# Step 3:
Detect points that form a line using HoughLinesP.

# Step 4:
Draw lines on the image.

# Step 5:
Display the result.


## Program:
DEVELOPED BY : R BRINDHA
REG NO : 212222230023

# Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("/content/r.jpg",0)
img_c=cv2.imread("r.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```


# Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```


# Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=200)
```


# Draw lines on the image
```
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```


# Display the result
```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()

```
## Output

### Input image and grayscale image
![Screenshot_20230426_012953](https://user-images.githubusercontent.com/118889143/234511591-3f8caff9-a165-47e2-bcee-44131aa58eb5.png)

### Canny Edge detector output
![Screenshot_20230426_013005](https://user-images.githubusercontent.com/118889143/234511664-0fe75883-487b-4372-8507-730fe21a37b8.png)

### Display the result of Hough transform
![Screenshot_20230426_013013](https://user-images.githubusercontent.com/118889143/234511736-17cb5422-0801-4bea-aa55-8324aff3ef59.png)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
