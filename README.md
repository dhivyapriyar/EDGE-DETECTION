# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('bike.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

canny_edges = cv2.Canny(gray_image, 50, 150)

plt.figure(figsize=(12, 12))

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

plt.tight_layout()
plt.show()
```
## Output:
### SOBEL EDGE DETECTOR
![image](https://github.com/user-attachments/assets/5c5937d8-b409-4edd-8f8f-75eaa416c322)

![image](https://github.com/user-attachments/assets/b88720b3-1044-40b4-8615-d2427b575a48)

### LAPLACIAN EDGE DETECTOR
![image](https://github.com/user-attachments/assets/382b9d39-b937-42c8-a54d-94249263f91b)


### CANNY EDGE DETECTOR
![image](https://github.com/user-attachments/assets/f9eb677e-8979-4f54-9f91-5fe87865de0c)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
