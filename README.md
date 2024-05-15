# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
DEVELOPED BY :MOHAMMED IMTHIYAS .M
Register number: 212222230083
```

```python
# Load the necessary packages
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('lap.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('lap.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image


![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/90e139cb-71e8-41f8-b219-059367a72f3f)


### Global Thresholding

![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/45f75b12-0249-4116-b6fa-6a8c785393e7)

![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/0fb89e9b-790f-4736-8c91-a9b92aca20df)


![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/494087c0-a019-4c82-a936-1029cf286ba2)

![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/d18a8ee4-6225-45df-8e0c-b36254bfa811)

![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/8215cb90-6943-4a20-8ad5-e0abfa2eeef7)


### Adaptive Thresholding

![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/ab46da54-8890-4f39-84e3-79f7d7573e42)

![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/242fdd28-0eb3-43b1-8de5-226be76fafa1)


### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/Subhikshaa13/Thresholdingg/assets/118787344/c41ee243-8d2c-4997-8a4e-87d895a68811)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
