### Thresholding of Images
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

### Software Required
1. Anaconda - Python 3.7
2. OpenCV

### Algorithm

### Step1:
Load the necessary packages requiured for the processing the threshold of the image.

### Step2:
Read the Image using the cv2 instructions and convert it to a grayscale image.

### Step3:
Apply global thresholding on the grayscale image and store the results in threshold variables. Use different thresholding methods to segment the image.

### Step4:
Apply adaptive thresholding on the grayscale image and store the results in the variables th1 and th2. Use different adaptive thresholding methods to segment the immage.

### Step5:
Apply Otsu's method on the grayscale image and store the result in variable th3.

### Step 6:
Create a list titles containing the titles of each image and a list images containing the corresponding images.

### Step 7:
Loop through the images list to display each image alongside its title using plt.subplot(), plt.title(), plt.imshow(), plt.axis(), and plt.show().

### Step 8:
End the program.

## Program
```
Developed By: Silambarasan. K
Register Number: 212221230101
Program to segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.
```

```
# Load the necessary packages:

import cv2
import matplotlib.pyplot as plt
import numpy as np

```
```
# Read the Image and convert to grayscale:

image=cv2.imread("cr.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
```

```
# Use Global thresholding to segment the image:

ret, thresh1 = cv2.threshold(image1,100,220,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,90,160, cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,140,220,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,225,270,cv2.THRESH_TOZERO_INV)
```

```
# Use Adaptive thresholding to segment the image:

th1 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 3)
th2 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 3)
```

```
# Use Otsu's method to segment the image:

ret2, th3 = cv2.threshold(image1, 150, 255, cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

```
# Display the results:

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (Truncate)",
       "Threshold Image (To Zero)","Threshold Image (To Zero-Inverse)","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)","Otsu"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
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
![s1](https://github.com/simbu07/Thresholding/assets/94525786/a8af1d3f-535b-4632-9456-d23bd1e1aabd)


### Global Thresholding
![s2](https://github.com/simbu07/Thresholding/assets/94525786/f39c2c9d-2ab7-4005-8c52-7647bda8f186)
![s3](https://github.com/simbu07/Thresholding/assets/94525786/1f70820c-5fbc-483a-a082-5b06e52cfd55)
![s4](https://github.com/simbu07/Thresholding/assets/94525786/fb754ff1-da96-46e5-a7ca-dcc2de8851ed)


### Adaptive Thresholding
![s5](https://github.com/simbu07/Thresholding/assets/94525786/5399c096-7fa5-4cda-acd0-63e1540870f9)


### Optimum Global Thesholding using Otsu's Method
![s6](https://github.com/simbu07/Thresholding/assets/94525786/59cd3311-ff40-4cba-8825-d3e7b30c302a)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

