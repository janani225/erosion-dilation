# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the image

### Step2:
Read the colour image and convert it into grayscale

### Step3:
Perform edge detection using canny

### Step4:
Define the kernel size for erosion and dilation

### Step5:
Display all images

## Program:

```python
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Read the color image
input_image_path = 'my photo.jpg'
color_image = cv2.imread(input_image_path)

# Convert the color image to grayscale
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

# Perform edge detection using Canny
edges = cv2.Canny(gray_image, 180, 200)  # You can adjust the thresholds as needed

# Define the kernel size for erosion and dilation
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

# Perform erosion
erosion = cv2.erode(edges, kernel, iterations=1)

# Perform dilation
dilation = cv2.dilate(edges, kernel, iterations=1)

# Display all images
plt.figure(figsize=(15, 10))

plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2, 3, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2, 3, 3)
plt.imshow(edges, cmap="gray")
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()

```

## Output:

![image](https://github.com/janani225/erosion-dilation/assets/113497333/9f1c602a-8f69-4790-9bb2-ea0964987125)



## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
