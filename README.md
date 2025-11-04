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
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image = cv2.imread("input.png")   # Read the image (color)
image_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

# Global Thresholding
ret, thresh_dipt1 = cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret, thresh_dipt2 = cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret, thresh_dipt3 = cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret, thresh_dipt4 = cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret, thresh_dipt5 = cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Otsu's Thresholding
ret, thresh_dipt6 = cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Adaptive Thresholding
thresh_dipt7 = cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,
                                     cv2.THRESH_BINARY,11,2)
thresh_dipt8 = cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                     cv2.THRESH_BINARY,11,2)

# Display the results
titles = ["Gray Image", "Binary", "Binary Inverse", "To Zero",
          "To Zero Inverse", "Truncate", "Otsu", "Adaptive Mean", "Adaptive Gaussian"]

images = [image_gray, thresh_dipt1, thresh_dipt2, thresh_dipt3,
          thresh_dipt4, thresh_dipt5, thresh_dipt6, thresh_dipt7, thresh_dipt8]

for i in range(9):
    plt.figure(figsize=(8,4))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis("off")
    
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(images[i], cmap="gray")
    plt.axis("off")
    
    plt.show()

```
## Outputs
<img width="500" height="700" alt="Screenshot 2025-11-04 193444" src="https://github.com/user-attachments/assets/d9cc5bdb-306b-499d-a55c-16cb6c066226" />
<br>
<img width="500" height="700" alt="Screenshot 2025-11-04 194437" src="https://github.com/user-attachments/assets/34a5967b-2ee1-4fb5-9b94-84f249f90709" />
<br>
<img width="500" height="700" alt="Screenshot 2025-11-04 194452" src="https://github.com/user-attachments/assets/bb059406-6313-4066-a2d6-5466700fff4e" />
<br>
<img width="500" height="750" alt="Screenshot 2025-11-04 194509" src="https://github.com/user-attachments/assets/ae14a19f-8f43-4fd4-844a-b75baf95ff66" />
<br>
<img width="500" height="700" alt="Screenshot 2025-11-04 194522" src="https://github.com/user-attachments/assets/1387863e-8482-4008-87f6-1c2b56ee845a" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
