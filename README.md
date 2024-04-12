# EX-08 THRESHOLDING
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
Use Otsu's method to segment the image and display the results.
## Program
```
DEVELOPED BY: SHARAN M J
REGISTER NO: 212222240097
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("thresholding.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("thresholding.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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
![Screenshot 2024-04-12 093046](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/2fa7e2fe-13e5-4deb-9759-be41802b1001)

### Global Thresholding
![Screenshot 2024-04-12 093131](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/a620f2b2-1c6d-424a-a28f-8a8c55f8854f)
![Screenshot 2024-04-12 093141](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/c6a52f97-672b-4b85-8900-e6365e9437ad)
![Screenshot 2024-04-12 093154](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/98db9f21-c498-45eb-9f89-b93acf4eac45)
![Screenshot 2024-04-12 093202](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/d21ac96c-ed46-4dbb-b81c-e8f452969817)
![Screenshot 2024-04-12 093211](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/7ad443e4-8125-4281-8186-b6df842842b5)

### Adaptive Thresholding
![Screenshot 2024-04-12 093217](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/ecfc8ad9-325a-4411-94bb-420379f77831)
![Screenshot 2024-04-12 093223](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/17c127d0-013a-478a-bcfd-db088123b51d)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-12 093232](https://github.com/SHARAN-MJ/THRESHOLDING-/assets/119560305/b339fe40-6085-46ba-8bc8-d375155f5de3)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
