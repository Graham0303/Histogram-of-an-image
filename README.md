# Histogram and Histogram Equalization of an image
## AIM:
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the necessary libraries and read two images, Color image and Gray Scale image.
### Step 2:
Calculate the Histogram of Gray scale image and any one channel of the color image.
### Step 3:
Display the histograms.
### Step 4:
Equalize the grayscale image.
### Step 5:
Display the equalized grayscale image.

## Program:
```python
# Developed By: Graham stanes
# Register Number: 212220230020

import cv2
import matplotlib.pyplot as plt
gray_img=cv2.imread("img1.jpg",0)
color_img=cv2.imread("img.jpg",-1)
gray_img=cv2.cvtColor(gray_img,cv2.COLOR_BGR2RGB)
color_img=cv2.cvtColor(color_img,cv2.COLOR_BGR2RGB)
plt.title("Color Image")
plt.axis("off")
plt.imshow(color_img)
plt.show()
plt.title("Gray Scale Image")
plt.axis("off")
plt.imshow(gray_img)
plt.show()

# Write your code to find the histogram of gray scale image and color image channels.

hist=cv2.calcHist([gray_img],[0],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel("grayscale value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

# Display the histogram of gray scale image and any one channel histogram from color image

hist=cv2.calcHist([color_img],[0],None,[256],[0,256])
plt.title("Histogram of Color Image:Red Channel")
plt.xlabel("Intensity value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

# Write the code to perform histogram equalization of the image. 

equ=cv2.equalizeHist(cv2.imread('img1.jpg',0))
equ=cv2.cvtColor(equ,cv2.COLOR_BGR2RGB)
plt.title("Equalised Image")
plt.axis("off")
plt.imshow(equ)
plt.show()

```
## Output:
### Input Grayscale Image and Color Image

![image](https://user-images.githubusercontent.com/75235150/169487663-2889adf6-3634-4aa7-83b4-c6f9e9c2395d.png)
![image](https://user-images.githubusercontent.com/75235150/169487685-d5de2a71-7f8c-403a-9b84-b0f1ae079afd.png)


### Histogram of Grayscale Image and any channel of Color Image
![image](https://user-images.githubusercontent.com/75235150/169487744-db821f60-1229-4eca-8cad-28b2badff739.png)
![image](https://user-images.githubusercontent.com/75235150/169487756-2902c986-5bf8-4df3-8c5c-63907f84f190.png)


### Histogram Equalization of Grayscale Image

![image](https://user-images.githubusercontent.com/75235150/169487808-32e2055e-56b0-49b1-91f2-f2427019a1eb.png)

## Result:

Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
