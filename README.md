# Ex.No: 7 Edge-Linking-using-Hough-Transformm
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
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:
#### Developed by
#### Name : KAMALESHWAR KV
#### Reg No : 212223240063

### Input Image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('chess_board.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
<img width="784" height="531" alt="image" src="https://github.com/user-attachments/assets/73759784-7770-4888-b45e-f77ae6452d53" />

### Grayscale Image:

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
<img width="918" height="630" alt="image" src="https://github.com/user-attachments/assets/4ed93391-8ee1-4ff9-b18d-bdde9fb818a3" />

### Canny Edge Detector:

```
edges = cv2.Canny(gray_image, 50, 150) 
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
<img width="645" height="436" alt="image" src="https://github.com/user-attachments/assets/20f18e73-fd45-4026-85c1-fc86b6a57de5" />

### Result of Hough Transform:

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
<img width="779" height="522" alt="image" src="https://github.com/user-attachments/assets/fc242f94-66ff-4c62-b8b7-d1ff2db9c1fe" />

## Result:
Thus, the image has been successfully converted.





