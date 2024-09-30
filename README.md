# Implementation-of-filter
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
Apply the required filters for the image separately

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.
 

## Program:
```
Developed By    : SUDHIR KUMAR. R
Register Number : 212223230221
```


### 1. Smoothing Filters

#### i) Using Averaging 

```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB) 

# Create an averaging kernel
kernel = np.ones((11, 11), np.float32) / 121  # 11x11 kernel for averaging

# Apply the averaging filter
image3 = cv2.filter2D(image2, -1, kernel)

# Display the original and filtered images
plt.figure(figsize=(10, 8))

# Original Image
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

# Averaging Filtered Image
plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Averaging Filter Applied")
plt.axis("off")

plt.show()
```

#### ii) Using Weighted Averaging Filter

```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

# Define the kernel for a weighted average filter
kernel1 = np.ones((5, 5), np.float32) / 25
image3 = cv2.filter2D(image2, -1, kernel1)

plt.figure(figsize=(8, 8))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")

plt.show()
```

#### iii) Using Gaussian Filter

```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
gaussian_blur = cv2.GaussianBlur(image2, (15, 15), 0)

plt.figure(figsize=(8,8))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")

plt.show()
```

#### iv)Using Median Filter

```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median = cv2.medianBlur(image2, 5)

plt.figure(figsize=(8, 8))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(median)
plt.title("Median Blurred Image")
plt.axis("off")

plt.show()
```

### 2. Sharpening Filters

#### i) Using Laplacian Linear Kernal

```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB) 

kernel = np.ones((11, 11), np.float32) / 121 
blurred_image = cv2.filter2D(image2, -1, kernel)

kernel2 = np.array([[-1, -1, -1], [-1, 8, -1], [-1, -1, -1]])
sharpened_image = cv2.filter2D(image2, -1, kernel2) 

plt.figure(figsize=(10, 4))

plt.subplot(1, 3, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(sharpened_image)
plt.title("Sharpened Image")
plt.axis("off")

plt.show()
```

#### ii) Using Laplacian Operator

```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB) 

laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.figure(figsize=(8,8))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Image")
plt.axis("off")

plt.show()
```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![Screenshot 2024-09-30 160503](https://github.com/user-attachments/assets/dcb155e6-4381-483e-831c-dcf8d120575e)

ii)Using Weighted Averaging Filter

![Screenshot 2024-09-30 160621](https://github.com/user-attachments/assets/48cd502b-7e9f-4847-a15f-711b6db0e6e3)

iii)Using Gaussian Filter

![Screenshot 2024-09-30 160800](https://github.com/user-attachments/assets/e6077293-f6bb-42d3-8d10-8d60c050dce0)

iv) Using Median Filter

![Screenshot 2024-09-30 160906](https://github.com/user-attachments/assets/8104e1d8-59ee-4cc8-9f78-8f0aef2fbb6a)

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

![Screenshot 2024-09-30 161012](https://github.com/user-attachments/assets/4015233e-1347-4bf7-aed5-1a6925be8991)

ii) Using Laplacian Operator

![Screenshot 2024-09-30 161132](https://github.com/user-attachments/assets/0aebe2be-4285-435f-836f-daa0cca1e3a6)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
