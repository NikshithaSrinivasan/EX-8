# EX-8
# THRESHOLDING

## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## PROGRAM:
```
DEVELOPED BY : NIKSHITHA S
REG NO : 212224040220
```
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt


# Read the Image and convert to grayscale
image = cv2.imread('my image.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(1, 1, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')


# Use Global thresholding to segment the image
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)


# Use Adaptive thresholding to segment the image
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)


# Use Otsu's method to segment the image 
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```
## Output :

### Original Image
<img width="157" height="285" alt="image" src="https://github.com/user-attachments/assets/7171c3c8-2fb8-4133-bdf0-cee15efbbbfb" />



### Global Thresholding
 
<img width="158" height="287" alt="image" src="https://github.com/user-attachments/assets/33b725e7-f521-4a9a-b713-2793c775a064" />



### Adaptive Thresholding
 
<img width="160" height="282" alt="image" src="https://github.com/user-attachments/assets/dfcbaa50-3779-4895-89d5-b31a19a708aa" />


### Optimum Global Thesholding using Otsu's Method
 
<img width="163" height="284" alt="image" src="https://github.com/user-attachments/assets/b5dd108f-7735-4f6a-afe1-eb4a032d14e2" />



## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
