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
DEVELOPED BY: Mathiyazhagan.A
REGISTER NO: 212222240063
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("spidy.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("spidy.jpg",0)
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

![Screenshot 2024-04-09 114124](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/ed996b64-014e-4891-b6b9-87d33fccd551)

### Global Thresholding
![Screenshot 2024-04-09 114136](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/fda8e55a-ef49-4f49-9d0e-6e2cd9c82325)
![Screenshot 2024-04-09 114155](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/75a7097e-1419-49b9-b889-2938247e2451)
![Screenshot 2024-04-09 114206](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/a5e468df-9a53-4630-8f93-7ea1ad4a75b2)

![Screenshot 2024-04-09 114215](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/4b18c1ac-2251-4b8c-a8c1-b27874b95ec4)

![Screenshot 2024-04-09 114225](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/720c1b92-bac0-45d0-a138-374f0deeec55)

### Adaptive Thresholding

![Screenshot 2024-04-09 114241](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/60185479-26c8-40e2-96b6-2a95fbcfd7af)


![Screenshot 2024-04-09 114250](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/8a16b506-034d-402f-b525-b92d835d03c5)

### Optimum Global Thesholding using Otsu's Method

![Screenshot 2024-04-09 114233](https://github.com/Mathiofficial/THRESHOLDING-/assets/118787327/499e84f9-023d-4b11-8ef3-c978228997bf)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
