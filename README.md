# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1
Import the necessary libraries (cv2, numpy, matplotlib.pyplot) and read the input image using cv2.imread().
</br>
</br> 

### Step 2
Define the kernels for the filters, such as an averaging kernel for smoothing (e.g., a 5x5 matrix of ones divided by 25) and a Laplacian kernel for sharpening.
</br>
</br> 

### Step 3
Apply the smoothing filters to the original image using functions like cv2.filter2D() for the averaging filter, cv2.GaussianBlur() for Gaussian blur, and cv2.medianBlur() for median blur.
</br>
</br> 

### Step 4
Apply the sharpening filter using cv2.filter2D() with the Laplacian kernel, and then add this filtered output to the original image to create the final sharpened image.
</br>
</br> 

### Step 5
Display the original, smoothed, and sharpened images side-by-side using matplotlib.pyplot.imshow() and plt.subplot() for comparison.
</br>
</br> 

## Program  Developed By :
- **Name:** Suman G 
- **Register Number:**  212223240163
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python

import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("jpeg.jpeg")
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
ii) Using Weighted Averaging Filter
```Python


kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
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
```Python



gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
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
iv)Using Median Filter
```Python


median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()


```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python



kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
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
```Python


laplacian=cv2.Laplacian(image2,cv2.CV_64F)
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

</br>
<img width="915" height="535" alt="image" src="https://github.com/user-attachments/assets/41c29ad2-863c-4dc3-b525-34ccb07f3711" />

</br>


ii)Using Weighted Averaging Filter

</br>
<img width="878" height="473" alt="image" src="https://github.com/user-attachments/assets/c09a5490-30c4-41be-8d9b-6640cb5393af" />

</br>

iii)Using GaussianBlur
<img width="916" height="492" alt="image" src="https://github.com/user-attachments/assets/ce3df5d2-afce-4654-9076-d9da8d25eac9" />


iv) Using Median Filter

</br>
<img width="893" height="542" alt="image" src="https://github.com/user-attachments/assets/3bdc8323-ce3b-4e6b-b630-c8e908b8ee50" />

</br>

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

</br>
<img width="898" height="487" alt="image" src="https://github.com/user-attachments/assets/5d1ba33e-e218-4f35-acd1-f3cde9ed5ad9" />

</br>

ii) Using Laplacian Operator
</br>
<img width="878" height="476" alt="image" src="https://github.com/user-attachments/assets/50b3dbb5-fbed-4969-840a-82f95699302c" />

</br>
</br>


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
