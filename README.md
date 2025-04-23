![image](https://github.com/user-attachments/assets/907282f6-4fa4-4860-89fa-436d8cc87b0b)# Implementation-of-filter
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


## Program:
### Developed By   : HARSHITHA V
### Register Number: 212223230074

```
#import the libraries
import cv2
import matplotlib.pyplot as plt
import numpy as np

# Load and convert the image to RGB
image_bgr = cv2.imread(r"C:\Users\admin\Downloads\digitalimage\cat.jpeg")
image2 = cv2.cvtColor(image_bgr, cv2.COLOR_BGR2RGB)
```
### 1. Smoothing Filters

i) Using Averaging Filter
```Python

# Define and apply the average filter kernel
kernel = np.ones((11, 11), np.float32) / 121  # 11x11=121
filtered_image = cv2.filter2D(image2, -1, kernel)  # Use image2 here, not image_rgb

# Plot original and filtered images
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.imshow(image2)  # Use image2 here, which is the RGB version
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(filtered_image)
plt.title("Average Filtered Image")
plt.axis("off")

plt.show()

```
ii) Using Weighted Averaging Filter
```Python
#define the weighted average kernel
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16

#apply the weighted average filter
image3=cv2.filter2D(image2,-1,kernel1)

#display the filtered image
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

```
iii) Using Gaussian Filter
```Python
#gaussian blur filter
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)

#display the gaussian blurred image
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```
iv)Using Median Filter
```Python
#apply median blur with kernel size 13
median=cv2.medianBlur(image2,13)

#plot original and median blurred images
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
#define a custom laplacian kernel for edge enhancement
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])

#apply the custom kernel using filter2D
image3=cv2.filter2D(image2,-1,kernel2)

#plot original and filtered images
plt.figure(figsize=(9,9))
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
#apply Laplacian operator to detect edges
laplacian=cv2.Laplacian(image2, cv2.CV_64F)

#display the Laplacian image
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter

![image](https://github.com/user-attachments/assets/a4f11869-f356-42a4-b446-96fdce75671d)


ii)Using Weighted Averaging Filter

![image](https://github.com/user-attachments/assets/1bfe4c4e-9bf3-4994-aaea-cd1bef59ab72)


iii)Using Gaussian Filter

![image](https://github.com/user-attachments/assets/69bd4639-c693-4c83-a080-30107eba1534)


iv) Using Median Filter

![image](https://github.com/user-attachments/assets/8d30e4fe-7513-4187-bb01-48f882db95f9)


### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

![image](https://github.com/user-attachments/assets/ee08f051-7e68-4233-a7fc-bb2a936fc303)


ii) Using Laplacian Operator

![image](https://github.com/user-attachments/assets/8ac9d2c3-d080-4ad4-9aac-76080210c703)



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
