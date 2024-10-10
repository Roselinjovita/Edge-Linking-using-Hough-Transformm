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
## PROGRAM
```
DEVELOPED BY : ROSELIN MARY JOVITA.S
REG NO: 212222230122
```

### Input image 
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('house.jpg')  # Replace with your image path
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```

### Ouput
![Screenshot 2024-10-10 102539](https://github.com/user-attachments/assets/0c9821fc-f3e6-439e-8959-fdf8911a740f)


### Grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image,
cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
### Output


![Screenshot 2024-10-10 102549](https://github.com/user-attachments/assets/d0e98842-03c5-4b2e-8d24-861ffd4ca592)


### Canny Edge detector output
```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
### Output
![Screenshot 2024-10-10 102602](https://github.com/user-attachments/assets/7137282c-35d9-4ef1-92e7-714a826f0ec1)


### Display the result of Hough transform
```
lines = cv2.HoughLinesP(canny_edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=100, maxLineGap=100)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
### Output

![Screenshot 2024-10-10 102610](https://github.com/user-attachments/assets/22483672-218e-4668-b4fd-6764fbcdca17)

### Result
Thus,The Python program to detect the lines using Hough Transform run successfully.
