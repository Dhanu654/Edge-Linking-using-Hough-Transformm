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
## Code:
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('nature.png')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2) 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
~~~
## Output

### Input image and grayscale image
![436176198-424fce68-8004-40a9-88da-3f063954efb2](https://github.com/user-attachments/assets/ffa75183-4759-464d-a40f-1b181786c9d8)
![436176251-3183eae1-d996-43cb-96b7-c2c58791c9a7](https://github.com/user-attachments/assets/559439af-e07d-47e5-b9a2-568bb2a8ec12)


### Canny Edge detector output
![436176367-4ec4cbf6-fca2-4239-b5d9-363ac8f0f695](https://github.com/user-attachments/assets/96320c51-2b17-4577-95c1-9b44cf748dd3)
.png)

### Display the result of Hough transform

![436176504-9a7cf645-b1cf-449c-91d0-3a109024f84d](https://github.com/user-attachments/assets/160f7bd0-21dd-4532-b4f8-e3dabe02101a)

## Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.
