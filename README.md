# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read image in grayscale
img = cv2.imread('saveetha.jpg', cv2.IMREAD_GRAYSCALE)

# Display original grayscale image
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')
plt.show()

# Display original histogram
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()

# Histogram Equalization for grayscale image
img_eq = cv2.equalizeHist(img)

# Display equalized histogram
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()

# Display equalized grayscale image
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.axis('off')
plt.show()


# Read image in color
img = cv2.imread('saveetha.jpg', cv2.IMREAD_COLOR)

# Convert BGR image to HSV
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Equalize the V (Value) channel
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert HSV back to BGR
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Display color equalized image
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Color Image')
plt.axis('off')
plt.show()

# Display histogram of equalized color image
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()


# Compare original and equalized color images
plt.figure(figsize=(20, 10))

plt.subplot(2, 2, 1)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')
plt.axis('off')

plt.subplot(2, 2, 2)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.axis('off')

plt.show()


# Compare original and equalized histograms
plt.figure(figsize=(15, 4))

plt.subplot(1, 2, 1)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.subplot(1, 2, 2)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.show()
```
### Developed By:
**Name:**S.jana shravin

### Register No:
212224243003

---

##  Output
<img width="1237" height="372" alt="download" src="https://github.com/user-attachments/assets/db1df898-e4b2-46df-8257-ac7972b311f6" />
<img width="1298" height="414" alt="download" src="https://github.com/user-attachments/assets/147f421e-f844-4038-bdf1-30ee9b2140bd" />
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/1e4d7cb3-deb4-4413-9817-b05f4db72592" />
<img width="475" height="434" alt="download" src="https://github.com/user-attachments/assets/7990e1ea-4fd9-4693-ad65-840865fe6ef8" />
<img width="475" height="434" alt="download" src="https://github.com/user-attachments/assets/ec30a798-a09a-492a-9ca0-6ca07104ebd5" />
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/b24d1ffb-6c93-46e1-802c-95ef09dfac7e" />
<img width="475" height="434" alt="download" src="https://github.com/user-attachments/assets/94f326ca-17c5-402f-b4ab-0817d16f0d0e" />
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/4eceda43-a4a3-43d1-b6a0-49a5f5760288" />

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
