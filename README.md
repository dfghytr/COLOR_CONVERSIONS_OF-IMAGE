# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii) Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.

### Step2:
Draw a line from the top-left to the bottom-right of the image. o Draw a circle at the center of the image. o Draw a rectangle around a specific region of interest in the image. o Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
Convert the image from RGB to HSV and display it. o Convert the image from RGB to GRAY and display it. o Convert the image from RGB to YCrCb and display it. o Convert the HSV image back to RGB and display it.

### Step4:
Access and print the value of the pixel at coordinates (100, 100). o Modify the color of the pixel at (200, 200) to white.

### Step5:
Resize the original image to half its size and display it.

### Step6:
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

### Step7:
Flip the original image horizontally and display it. o Flip the original image vertically and display it.

### Step8:
Save the final modified image to your local directory.

## Program:
### Developed By: Abdul kalaam k m
### Register Number: 212223230003
### i) Read and display the image:
```
import cv2
image = cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png', 1)
if image is None:
    print("Error: Image not found. Please check the file path.")
else:
    image = cv2.resize(image, (200, 300))
    cv2.imshow('Shaik Shoaib Nawaz', image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
### ii)Write the image:
```
    import cv2
    image=cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png',0)
    cv2.imwrite('shoaib.png',image)
```
### iii)Shape of the Image:
```
    import cv2
    image=cv2.imread('kalam.png',1)
    print(image.shape)
```
### iv)Access rows and columns:
```
    import random
    import cv2
    image=cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
### v)Cut and paste portion of image:
```
 import cv2
   image=cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png',1)
   image=cv2.resize(image,(400,400))
   tag =image[130:200,110:190]
   image[110:180,120:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
### vi) BGR and RGB to HSV and GRAY:
```
import cv2
img = cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png',1)
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
### vii) HSV to RGB and BGR:
```
import cv2
img = cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png')
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
### viii) RGB and BGR to YCrCb:
```
import cv2
img = cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### ix) Split and merge RGB Image:
```
import cv2
img = cv2.imread('Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### x) Split and merge HSV Image:
```
import cv2
img = cv2.imread("Desktop/dipt/COLOR_CONVERSIONS_OF-IMAGE/kalam.png",1)
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









## Output:

### i) Read and display the image:

![Screenshot 2024-09-26 153909](https://github.com/user-attachments/assets/eda8d584-ac90-487c-ad2c-6c9505f33feb)

<br>
<br>

### ii)Write the image:
![Screenshot 2024-09-26 155242](https://github.com/user-attachments/assets/751f7423-999a-498d-91cc-93e2ab555f7c)

<br>
<br>

### iii)Shape of the Image:
![Screenshot 2024-09-26 155430](https://github.com/user-attachments/assets/e61e20d7-55e3-49ff-87d9-39d483033720)

<br>
<br>

### iv)Access rows and columns:


<br>
<br>

### v)Cut and paste portion of image:
![Screenshot 2024-09-26 160349](https://github.com/user-attachments/assets/d97fc033-06df-4668-9b59-adb3252b11dc)

<br>
<br>

### vi) BGR and RGB to HSV and GRAY:
![Screenshot 2024-09-26 153909](https://github.com/user-attachments/assets/48db0655-a413-416d-bd47-471b5565eed8)
![Screenshot 2024-09-26 160804](https://github.com/user-attachments/assets/7c0c15d2-2c02-488a-9107-1ba7828b1159)
![Screenshot 2024-09-26 160819](https://github.com/user-attachments/assets/d5ce2c42-bddf-4e64-b103-e986dacc6106)
![Screenshot 2024-09-26 160812](https://github.com/user-attachments/assets/be4a5cb6-36d4-4f4c-a4ef-a7313cb4c683)
<br>
<br>

### vii) HSV to RGB and BGR:
![Screenshot 2024-09-26 153909](https://github.com/user-attachments/assets/925cd3f4-b07f-4787-824e-d358d168fc22)
![Screenshot 2024-09-26 161132](https://github.com/user-attachments/assets/ba888505-3993-4930-9d9e-86ca62e47492)
![Screenshot 2024-09-26 161141](https://github.com/user-attachments/assets/a97ab824-2124-4de1-8e4c-f5621528d635)

<br>
<br>

### viii) RGB and BGR to YCrCb:
![Screenshot 2024-09-30 152243](https://github.com/user-attachments/assets/ed2d44f1-8c48-4286-a8fd-1cff2cec3e84)
![Screenshot 2024-09-30 152255](https://github.com/user-attachments/assets/b14d83d6-20fb-4688-9dd3-bdd347024763)
![Screenshot 2024-09-30 152314](https://github.com/user-attachments/assets/337a4593-b498-44ba-a4a0-fccf14a73aca)

<br>
<br>

### ix) Split and merge RGB Image:
![Screenshot 2024-09-30 152452](https://github.com/user-attachments/assets/b15a6fa7-90f7-4753-be39-c04c9e959aa5)
![Screenshot 2024-09-30 152500](https://github.com/user-attachments/assets/3e91c11e-fc51-42bc-9c91-ee7c5a31bae3)
![Screenshot 2024-09-30 152524](https://github.com/user-attachments/assets/d19a539a-1008-4e38-8bf0-c045d57c11d7)
![Screenshot 2024-09-30 152513](https://github.com/user-attachments/assets/c7dbc672-7306-4427-a291-42b98f62a21d)

<br>
<br>

### x) Split and merge HSV Image:
![Screenshot 2024-09-30 152642](https://github.com/user-attachments/assets/b43a48e8-8e1d-4635-a254-74fb7aac4b29)
![Screenshot 2024-09-30 152650](https://github.com/user-attachments/assets/bfff4172-2028-44f2-b50e-718c22aebf35)
![Screenshot 2024-09-30 152659](https://github.com/user-attachments/assets/f7bdde87-496a-4dc8-b63a-616343cf7c65)
![Screenshot 2024-09-30 152706](https://github.com/user-attachments/assets/4b35c28a-e17f-4243-b1ee-2e67513c19f1)

<br>
<br>




## Result:
    Thus the images are read, displayed, and written ,and color conversion was performed successfully using the python program.







