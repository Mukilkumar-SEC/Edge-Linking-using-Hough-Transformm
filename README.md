# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program:
```
import cv2
import matplotlib.pyplot as plt
```
```
image = cv2.imread('dog.jpg')  
```
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/bbcfa939-be43-41f1-9023-05fd37a46db2)

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/9672f142-3213-4195-a41f-f0fe9c510ae5)

```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
```
```
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/07cbb354-b7a7-4715-8afd-4f2dcf14685f)

```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)

```
```
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()

```
![image](https://github.com/user-attachments/assets/0ea0fa71-7591-4b5c-b73b-c29e968ad9bf)

## Result: 
Thus the python program to detect the lines using Hough Transform was successfully completed.
 
