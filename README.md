# EXP 08 : THRESHOLDING
### NAME : HARI PRIYA M
### REGISTER NO : 212224240047

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the input image and convert it into a grayscale image.
<br>

### Step2:
Apply global thresholding by manually choosing a threshold value and segmenting the image based on it.
<br>

### Step3:
Apply adaptive thresholding, where the threshold value is calculated automatically for different regions of the image.
<br>

### Step4:
Apply Otsu's thresholding, which chooses the best threshold value automatically based on image histogram.
<br>

### Step5:
Display the original image and the segmented images obtained from global, adaptive, and Otsu thresholding.
<br>

## Program

```python

import cv2
import matplotlib.pyplot as plt

# Step 1: Load the image and convert it to grayscale
image = cv2.imread("input.png") 
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Step 2: Apply Global Thresholding (Manually selected threshold)
_, global_thresh = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

# Step 3: Apply Adaptive Thresholding
adaptive_thresh = cv2.adaptiveThreshold(
    gray, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2
)

# Step 4: Apply Otsu's Thresholding
_, otsu_thresh = cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Step 5: Display all results
titles = ["Original Image", "Global Thresholding", "Adaptive Thresholding", "Otsu Thresholding"]
images = [gray, global_thresh, adaptive_thresh, otsu_thresh]

plt.figure(figsize=(10, 7))

for i in range(4):
    plt.subplot(2, 2, i+1)
    plt.imshow(images[i], cmap="gray")
    plt.title(titles[i])
    plt.axis("off")

plt.show()

```
## Output

### Original Image, Global Thresholding, Adaptive Thresholding and Optimum Global Thesholding using Otsu's Method

<img width="859" height="700" alt="Screenshot 2025-11-04 193444" src="https://github.com/user-attachments/assets/4d2b5181-b26f-4c8a-8170-05b8e24fb8c3" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
