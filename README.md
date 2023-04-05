# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()
<br>

### Step2:
Print the image using imshow()
<br>

### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image
<br>

### Step4:
cv2.equalize() is used to transform the gray image to equalized form
<br>

### Step5:
The Histogram of gray scale image and color image is shown.
<br>

## Program:
```python
# Developed By: Vishranthi A
# Register Number: 212221230124
```
# Write your code to find the histogram of gray scale image and color image channels.
```python
import cv2
import matplotlib.pyplot as plt

# Histogram for Grayscale image
grayscale_img=cv2.imread("gray.jfif")
plt.imshow(grayscale_img)
plt.show()
hist=cv2.calcHist([grayscale_img],[0],None,[256],[0,255])

# Histogram for BGR image for a single channel
color_img=cv2.imread("cat.png")
hist1=cv2.calcHist([color_img],[1],None,[256],[0,255])
plt.imshow(color_img)
plt.show()
```
# Display the histogram of gray scale image and any one channel histogram from color image
```python
#Plotting histogram for Grayscale image
plt.figure()
plt.title("Histogram")
plt.xlabel("Grayscale value")
plt.ylabel("Pixel Count")
plt.stem(hist)
plt.show()

#Plotting histogram for BGR image -Single Channel
plt.figure()
plt.title("Histogram for BGR image")
plt.xlabel("BGR intensity value")
plt.ylabel("Pixel Count")
plt.stem(hist1)
plt.show()
```
# Write the code to perform histogram equalization of the image. 
```python
#Histogram equalization for Grayscale image
import cv2
Gray_image=cv2.imread('gray.jfif',0)
equalize=cv2.equalizeHist(Gray_image)
#Resizing image 
Gray_image= cv2.resize(Gray_image, (270,190))
equalize= cv2.resize(equalize, (270,190))
#Output
cv2.imshow('GRAY IMAGE',Gray_image)
cv2.imshow('EQUALIZED IMAGE',equalize)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
### Input Grayscale Image and Color Image
<br>
![image](https://user-images.githubusercontent.com/93427278/230112460-5cc1d153-09eb-4bd8-aee0-ba4a7b8871f2.png)

<br>
![image](https://user-images.githubusercontent.com/93427278/230112607-f06fc7ad-c8f5-4647-a727-dab5fe2ecac4.png)

<br>

### Histogram of Grayscale Image and any channel of Color Image
<br>
![image](https://user-images.githubusercontent.com/93427278/230112917-59f6c5a9-4a45-4cc5-89c6-2261ea4c2907.png)

<br>
![image](https://user-images.githubusercontent.com/93427278/230113011-ca1a9f2d-2703-4f2f-97d5-65a14d1622d3.png)

<br>

### Histogram Equalization of Grayscale Image
<br>
![image](https://user-images.githubusercontent.com/93427278/230113485-3a7ecdcd-1a31-48f4-9ef3-f9d509be31a6.png)

<br>

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
