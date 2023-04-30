# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
## Step1:
Import the necessary packages.

## Step2:
Create the Text using cv2.putText.

## Step3:
Create the Global thresholding to segment the image.

## Step4:
Create Adaptive thresholding to segment the image.

## Step5:
Otsu's method to segment the image.

## Step6:
End the program.

## Program
~~~
 Developed by:Deepika J
 Register number:212221230016
 ~~~
~~~
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("r2.png")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(gray_img,'gray')
plt.title('Gray image')
plt.axis('off')

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(gray_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[gray_img,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()   
   ~~~
## Output

### Original Image
![e](https://user-images.githubusercontent.com/94747031/235337846-15e2c844-afd6-42c3-9d1d-6ff3434723c4.png)

### Global Thresholding
![g](https://user-images.githubusercontent.com/94747031/235337854-a93aa9f6-048b-4022-97b7-964c219468e8.png)
![Uploading f.png…]()
![j](https://user-images.githubusercontent.com/94747031/235338001-16a0b4c5-7ff7-4136-ad5f-b21cedddf22c.png)
![h](https://user-images.githubusercontent.com/94747031/235338073-b402be15-0dab-4ef5-9789-10f1c4797e03.png)

### Adaptive Thresholding
![l](https://user-images.githubusercontent.com/94747031/235337883-84ebccc3-f2a0-4341-a8dc-b240c80a33a5.png)
![m](https://user-images.githubusercontent.com/94747031/235338045-eb28c0e4-3789-47f1-b004-e46f01fa553a.png)
### Optimum Global Thesholding using Otsu's Method
![k](https://user-images.githubusercontent.com/94747031/235337872-3f85a27d-7b58-4e26-ab15-51a8087a0ac5.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
