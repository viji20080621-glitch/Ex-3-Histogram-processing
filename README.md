# Histogram Equalization Using OpenCV (Grayscale & Color Images)

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

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

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

## Program

### Developed By:
# Name: Vijiyalakshmi A
### Register No: 212225240185

# Grayscale Histogram Equalization
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read original color image
img = cv2.imread("sea.jpg")

if img is None:
    print("Image not found! Check the image filename.")
else:
    # Convert BGR to RGB
    rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    # Convert to grayscale
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

    # Histogram equalization
    equalized = cv2.equalizeHist(gray)

    plt.figure(figsize=(12, 10))

    # Original Color Image
    plt.subplot(3, 2, 1)
    plt.imshow(rgb)
    plt.title("Original Color Image")
    plt.axis("off")

    # Original Grayscale Image
    plt.subplot(3, 2, 2)
    plt.imshow(gray, cmap='gray')
    plt.title("Original Grayscale Image")
    plt.axis("off")

    # Original Histogram
    plt.subplot(3, 2, 3)
    plt.hist(gray.ravel(), bins=256, range=[0, 256], color='black')
    plt.title("Original Histogram")
    plt.xlabel("Pixel Intensity")
    plt.ylabel("Frequency")

    # Equalized Image
    plt.subplot(3, 2, 4)
    plt.imshow(equalized, cmap='gray')
    plt.title("Equalized Image")
    plt.axis("off")

    # Equalized Histogram
    plt.subplot(3, 2, 5)
    plt.hist(equalized.ravel(), bins=256, range=[0, 256], color='black')
    plt.title("Equalized Histogram")
    plt.xlabel("Pixel Intensity")
    plt.ylabel("Frequency")

    plt.tight_layout()
    plt.show()
```

# Color Image Histogram Equalization
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread("sea.jpg")

if img is None:
    print("Image not found!")
else:
    rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    R, G, B = cv2.split(rgb)

    plt.figure(figsize=(12, 10))

    plt.subplot(3, 2, 1)
    plt.imshow(R, cmap='Reds')
    plt.title("Red Channel")
    plt.axis("off")

    plt.subplot(3, 2, 2)
    plt.hist(R.ravel(), bins=256, range=[0, 256], color='red')
    plt.title("Red Histogram")

    plt.subplot(3, 2, 3)
    plt.imshow(G, cmap='Greens')
    plt.title("Green Channel")
    plt.axis("off")

    plt.subplot(3, 2, 4)
    plt.hist(G.ravel(), bins=256, range=[0, 256], color='green')
    plt.title("Green Histogram")

    plt.subplot(3, 2, 5)
    plt.imshow(B, cmap='Blues')
    plt.title("Blue Channel")
    plt.axis("off")

    plt.subplot(3, 2, 6)
    plt.hist(B.ravel(), bins=256, range=[0, 256], color='blue')
    plt.title("Blue Histogram")

    plt.tight_layout()
    plt.show()
```
##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast

<img width="863" height="721" alt="Screenshot 2026-10-30 184959" src="https://github.com/user-attachments/assets/872f2f3e-d154-4002-be36-671df72fc296" />


### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

<img width="785" height="728" alt="Screenshot 2026-10-30 185134" src="https://github.com/user-attachments/assets/ee6b3d84-ad08-420f-8e2e-cc3f2f69c01f" />

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
