# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules

### Step2
For performing smoothing operation on a image.

Average filter:
```
avg_kernel=np.ones((13,13),np.float32)/169
average_filter_image=cv2.filter2D(image,-1,avg_kernel)
```
Weighted average filter :
```
wt_avg_kernel=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
wt_average_filter_image=cv2.filter2D(image,-1,wt_avg_kernel)
```
Gaussian Blur:
```
gaussian_blur=cv2.GaussianBlur(image,(31,31),0,0)
```
Median filter:
```
median_blur=cv2.medianBlur(image,11)
```
### Step3
For performing sharpening on a image.

Laplacian Kernel:
```
lap_kernel=np.array([[-1,-1,-1],[-1,8,-1],[-1,-1,-1]])
lap_image=cv2.filter2D(image,-1,lap_kernel)
```
Laplacian Operator:
```
Lap_sharp=cv2.Laplacian(image,cv2.CV_64F)
```
### Step4
Display all the images with their respective filters.
## Program:
### Developed By   : Tamil venthan R S
### Register Number:2122202130054
</br>

```python

import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread('k.jpg')
img1=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

```
### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel=np.ones((13,13),np.float32)/169
image=cv2.filter2D(img1,-1,kernel)
plt.figure(figsize=(10,10))

plt.subplot(1,2,1)

plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image)





```
ii) Using Weighted Averaging Filter
```Python

kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image1=cv2.filter2D(img1,-1,kernel2)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image1)






```
iii) Using Gaussian Filter
```Python

img4=cv2.GaussianBlur(src=img1,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)

plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)






```

iv) Using Median Filter
```Python
img5=cv2.medianBlur(src=img1,ksize=11)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)






```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
img6=cv2.filter2D(img1,-1,kernel3)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img6)







```
ii) Using Laplacian Operator
```Python

img7=cv2.Laplacian(img1,cv2.CV_64F)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img7)









```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
</br>
</br>
![07957da6-ce48-4fd5-b309-29a07e21d3c5](https://user-images.githubusercontent.com/75235477/167808931-1e8793e3-09a9-4c45-a06c-e153a194613e.jpg)


</br>
</br>

ii) Using Weighted Averaging Filter
</br>
</br>

![6f6c1189-d7c5-487c-a1ee-db5daa1040a1](https://user-images.githubusercontent.com/75235477/167809108-12e6b1bb-c231-4f95-a881-ab25ef6c7ed1.jpg)


</br>
</br>

iii) Using Gaussian Filter
</br>
</br>


![b3a1d084-319a-4064-80b5-65ba59eedd0c](https://user-images.githubusercontent.com/75235477/167809458-2403b6a0-ccda-4ebf-8def-3cbb88a4355e.jpg)

</br>
</br>

iv) Using Median Filter
</br>
</br>

![8c6a48fb-0d52-40a0-8f99-8aba5b7a20ef](https://user-images.githubusercontent.com/75235477/167809552-4eb03743-9265-4c24-a876-2736ea3db0a4.jpg)

</br>
</br>

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
</br>
</br>

![15578e74-8bf2-4a55-97ae-a63319ea3de3](https://user-images.githubusercontent.com/75235477/167809671-534e81c4-f820-4c93-9832-4d24eaec4959.jpg)

</br>
</br>

ii) Using Laplacian Operator
</br>
</br>

![9fdad4c1-b7f2-47ba-b361-aff432a2731c](https://user-images.githubusercontent.com/75235477/167809708-b632dd3c-a942-4b8f-9719-a1640cc9cd43.jpg)

</br>
</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
