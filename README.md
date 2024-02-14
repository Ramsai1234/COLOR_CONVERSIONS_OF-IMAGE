# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By:P.Ramsai
### Register Number: 212221240041

### i) Read and display the image
```
import cv2
colorImage = cv2.imread("flower.jpg",1)
cv2.imshow('ramsai',colorImage)
cv2.waitKey(0)

```
![Screenshot 2024-02-14 182534](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/40d5302e-9f73-40f6-afcb-0d3011e86aa0)




### ii)Write the image
```
import cv2
image=cv2.imread('flower.jpg',0)
cv2.imwrite('new1.jpg',image)

```
![image](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/a68ced56-1ff7-4e7e-afa7-116559e38b58)



### iii)Shape of the Image
```
import cv2
image=cv2.imread('flower.jpg',1)
print(image.shape)

```
![image](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/93fae797-c315-4ef3-b677-85037cc99886)


### iv)Access rows and columns
```
import cv2
import random
colorImage = cv2.imread('flower.jpg',1)
for i in range(100):
    for j in range(colorImage.shape[1]):
        colorImage[i][j]=[random.randint(0,255),random.randint(0,160),random.randint(0,255)]
cv2.imshow('ramsai',colorImage)
cv2.waitKey(0)

```
![Screenshot 2024-02-14 183353](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/6502a644-5d9e-4c72-8332-2dc76a4174f9)



### v)Cut and paste portion of image
```
import cv2
color_img = cv2.imread('flower.jpg',1)
tag = color_img[20:80,20:80]
color_img[90:150,90:150] = tag
cv2.imshow('ramsai',color_img)
cv2.waitKey(0)

```
![Screenshot 2024-02-14 191954](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/e7f10169-93f6-41a6-8e84-1668b7cfdf96)



### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('dip.jpeg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
![Screenshot 2024-02-14 184058](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/4e581578-5270-444f-801b-72d5af2e1293)



### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('dip.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
![Screenshot 2024-02-14 184934](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/a6320cf3-2911-441e-801e-c8fe5ae8a84f)


### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('dip.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
![Screenshot 2024-02-14 202655](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/0396977b-b0ae-4ef5-bab7-9fb4e648a538)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('dip.jpeg',1)
img = cv2.resize(img,(300,200))
​
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
​
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
​
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
​
cv2.waitKey(0)
cv2.destroyAllWindows()

```
![image](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/abe2804f-7202-48a8-89c3-8a2d4815bcad)


### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("dip.jpeg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
![image](https://github.com/Ramsai1234/COLOR_CONVERSIONS_OF-IMAGE/assets/94269989/da9a834c-864a-4f04-a919-de27a5485b2d)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







