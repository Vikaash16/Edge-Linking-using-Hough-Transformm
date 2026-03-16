
# Edge-Linking-using-Hough-Transformm
## DEVELOPED BY : Vikaash P
## REG NO : 212223240180
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

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program :

###  Input image and grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("TK.JPG",0)
img_c=cv2.imread("TK.JPG",1)
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

### Canny Edge detector 
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
###  Hough transform
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="1325" height="374" alt="image" src="https://github.com/user-attachments/assets/8d48eb85-119d-4176-b513-08ddd3af04a4" />


### Canny Edge detector output
<img width="667" height="406" alt="image" src="https://github.com/user-attachments/assets/9df4fa65-aada-4e67-bdd7-55945ea806db" />


### Display the result of Hough transform
<img width="666" height="401" alt="image" src="https://github.com/user-attachments/assets/b680aaf2-93b0-41bd-8b71-1b3e95a4e6f5" />

