# EX-8 - THRESHOLDING
# Name : Selvaganesh B
# Reg.No : 212224230258
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

## Program

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```PY
image = cv2.imread('spide.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('spide.jpg',0)
```
### Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```PY
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

<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/fe04c86e-626c-461c-a6f9-d68c4f3bbb65" />


### Global Thresholding

<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/930f1fb7-1252-4a6b-b3ae-80f01369f486" />
<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/22032bb2-010a-4d03-8ae5-6269e15e87b8" />
<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/60af197f-850d-419a-a18d-1ffb44574ded" />
<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/80d5d557-4606-499b-ba45-0f5e21712128" />
<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/fb31f24f-a267-42bd-98f4-9c6a74aebbd5" />

### Adaptive Thresholding

<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/921e8dae-bda8-460d-98e4-227475736352" />

<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/aa41a84d-cd65-4c98-a7a8-4bf942fb1739" />

### Optimum Global Thesholding using Otsu's Method

<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/a727e95c-4e5a-4147-a5a3-b83c3ffcf465" />

<img width="794" height="238" alt="download" src="https://github.com/user-attachments/assets/16c2b9cd-ff27-427a-a616-2f2ed48f8910" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
