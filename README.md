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

## Program & Output:
### Input image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('c.jpg')  # Replace with your image path
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
![Screenshot 2024-10-10 103646](https://github.com/user-attachments/assets/9841b992-ea89-4201-8312-3c2b379de3b6)


### Grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
![Screenshot 2024-10-10 103657](https://github.com/user-attachments/assets/17151e65-54e4-4519-bedc-b6c840b67b51)

### Canny Edge detector output
```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
![Screenshot 2024-10-10 103705](https://github.com/user-attachments/assets/218400cd-f0a5-46a4-87c3-1d310944ccb2)


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

![Screenshot 2024-10-10 103713](https://github.com/user-attachments/assets/25edf5ea-3708-4d0b-81e9-680debb9da7c)


### Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.

