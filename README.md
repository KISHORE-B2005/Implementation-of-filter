# EXP.5 - Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.


### Step2
Convert the image from BGR to RGB.


### Step3
Apply the required filters for the image separately.


### Step4
Plot the original and filtered image by using matplotlib.pyplot.


### Step5
End the program.

## Program:
```
 Developed By   : KISHORE.B
 Register Number: 212222110020
```

### 1. Smoothing Filters
### i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("BIRD.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/8cf46289-b6fc-44ef-9a82-0bda4e0bc021)

### ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize=(9,9))
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/60cee13e-04de-4308-919f-6a0408ae7158)

### iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(9,9))
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/c58feee2-2b52-4a40-ba91-455b7c320f53)

### iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/d3f21476-4a8f-4eec-9549-f9b7e85c16dc)

### 2. Sharpening Filters
### i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/d9b65ad3-8fad-434f-8993-efa74108f6b8)

### ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize=(9,9))
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/b2e8f84b-737d-46e3-beb4-697db55f1954)

## Result:

Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
