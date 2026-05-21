# Edge-Linking-using-Hough-Transformm
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

## Program:
### Name: SANJAI U
### Register Number: 212224240145
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('oph.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.show()

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()

edges = cv2.Canny(gray_image, 50, 150) 
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
if lines is not None:  
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
plt.show()
```
## Output
### Input image

<img width="698" height="515" alt="image" src="https://github.com/user-attachments/assets/daaddc2f-c14c-466a-b435-260ab6fa18e0" />

### Grayscale image


<img width="667" height="517" alt="image" src="https://github.com/user-attachments/assets/e4b9b7fc-ed60-4b7d-a4e6-95183b2f6e16" />

### Canny Edge detector output

<img width="688" height="527" alt="image" src="https://github.com/user-attachments/assets/afa705c9-fd41-40e8-b95f-6167c680d463" />


### Display the result of Hough transform

<img width="678" height="527" alt="image" src="https://github.com/user-attachments/assets/145c33b4-2332-4077-8e08-ad4206127b08" />


## Result:
Thus we have successfully detected lines by using Hough Transform.
