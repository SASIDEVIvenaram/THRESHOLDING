# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## Program

```python
### Developed By: SASIDEVI V
### Register No: 212222230136

# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread("ff.webp",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("ff.webp",0)

# Use Global thresholding to segment the image
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Otsu's method to segment the image 

thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
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
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/4b657853-b914-4947-aa4e-ad03742a7295)



### Global Thresholding
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/2bf2cfca-9016-4ed7-bea7-1c9d2e88c5c2)
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/4fc9e48f-a8cf-4e2a-b962-80d42ec53db9)
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/9d44811b-05cf-464b-9d4b-d6aa11dac98d)
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/f1b7bf86-38a4-43d9-b129-488cd36c8fab)
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/f2839ff7-c9cc-402d-b664-b8f63ab30531)

### Adaptive Thresholding
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/1ce70633-f304-4be5-b300-d381dd8e8ddb)
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/86850383-79e9-441e-a542-01b97642c7d7)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/SASIDEVIvenaram/THRESHOLDING/assets/118707332/6c2452a1-54d6-442a-bbf9-e380123fd063)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

