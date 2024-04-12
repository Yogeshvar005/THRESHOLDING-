## EX-08 THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.


### Software Required
1. Anaconda - Python 3.7
2. OpenCV
 
### Algorithm
#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.
### Program
```python
DEVELOPED BY: YOGESHVAR
REGISTER NO: 212222230180
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/5a9f0712-6fcc-4b9f-b8f2-45e67ce7d8ba)

#### Read the Image and convert to grayscale
```python
image = cv2.imread("seal.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("seal.jpg",0)
```
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/ef092b0b-e497-4fc5-8dff-b0405ffc9e7e)

#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/c829aee8-c8c4-4fdf-ac92-38d17e2ed888)

#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/392ee54a-ceec-4aef-949d-0c053c161113)

#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/2ba62a3f-7d0b-4c4e-8c82-4b2e5a17af97)

#### Display the results
```python
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
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/4dbbb7b6-043f-4f29-8d98-fcf964d3abdb)
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/629d4462-00b3-4888-ba38-ecde167f29c6)
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/8a83892e-211c-4fea-869f-751f10fbc33f)
![image](https://github.com/Yogeshvar005/THRESHOLDING-/assets/113497367/993e8bce-30c3-4028-a3cf-6cbdbacc6aff)


### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
