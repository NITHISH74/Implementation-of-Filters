# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

### Step 2:
Convert the saved BGR image to RGB using cvtColor().
### Step 3:
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.
### Step 4:
Apply the filters using cv2.filter2D() for each respective filters.


### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().


## Program:

```
Developed By   :NITHISHWAR S
Register Number: 212221230071
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("duckgo.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
```

### 1. Smoothing Filters

i) Using Averaging Filter
```
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(8,8))
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
ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

iv) Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter
![image](https://user-images.githubusercontent.com/94164665/168848211-a712bd38-7bad-491e-b101-2cffb821f9de.png)

ii) Using Weighted Averaging Filter
![image](https://user-images.githubusercontent.com/94164665/168848366-8cfe6635-e172-47e9-8d52-2485cad59200.png)

iii) Using Weighted Averaging Filter
![image](https://user-images.githubusercontent.com/94164665/168848483-f217c268-2f44-4901-87b4-38f8ed05aaa2.png)
iv) Using Median Filter
![image](https://user-images.githubusercontent.com/94164665/168848602-c5727a71-ef03-4b7e-906b-0316fdfecce2.png)

### 2. Sharpening Filters
i) Using Laplacian Kernal
![image](https://user-images.githubusercontent.com/94164665/168848665-60c56bb7-b949-48d4-83e2-797553ddce06.png)

ii) Using Laplacian Operator
![image](https://user-images.githubusercontent.com/94164665/168848777-90beee5c-a93d-4c52-94bd-f7dbe1348cfa.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
