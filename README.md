# EDGE-DETECTION
# Name: ELAKYA L 
# Reg no: 212225230066

## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('sv.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

## Output

### Input Image 

<img width="258" height="311" alt="image" src="https://github.com/user-attachments/assets/30cdbd31-f93d-470a-9129-c462106ef1db" />


### 1. Sobel Edge Detector

<img width="256" height="314" alt="image" src="https://github.com/user-attachments/assets/22fe5d35-4df5-4b41-873f-13fe0e8e0861" />


### 2. Laplacian Edge Detector

<img width="254" height="313" alt="image" src="https://github.com/user-attachments/assets/4c58770f-872e-4cce-93ae-792b9f90e863" />


### 3. Canny Edge Detector

<img width="252" height="343" alt="image" src="https://github.com/user-attachments/assets/d53c5c9c-ed05-4210-b939-edcf29c09330" />


## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
