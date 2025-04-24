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

## Code 
## DEVELOPED BY: THARUN D
## REGISTER NUMBER: 212223240167
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('got.jpg')

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
```

## Output
### Input image and grayscale image
![Screenshot 2025-04-23 204828](https://github.com/user-attachments/assets/ada604ee-28aa-4f16-a621-cac5ec1424a0)
![Screenshot 2025-04-23 204834](https://github.com/user-attachments/assets/2093f7dd-65e1-46c0-8a2b-19e4a88e610a)


### Canny Edge detector output
![Screenshot 2025-04-23 204840](https://github.com/user-attachments/assets/dd8280c5-1ca4-4e15-a731-ae6999375057)


### Display the result of Hough transform
![Screenshot 2025-04-23 204846](https://github.com/user-attachments/assets/0eb76a1c-4333-4710-9a04-6d55cc040a58)



## Result

Thus,The Python program to detect the lines using Hough Transform run successfully.
