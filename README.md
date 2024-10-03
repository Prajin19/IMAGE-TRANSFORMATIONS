# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Translation moves an image from one location to another along the x-axis, y-axis, or both.
Translation: Moves the image by (50, 100) pixels.

### Step2:
Scaling changes the size of an image by enlarging or shrinking it.
Scaling: Enlarges the image by 1.5x.

### Step3:
Shearing distorts(curved or unnaturally) the shape of an image by shifting one axis, making parallel lines slanted.
Shearing: Applies a shear transformation with a factor of 0.5.

### Step4:
Reflection creates a mirror image of the original by flipping it across a specific axis
Reflection: Flips the image horizontally.

### Step5:
Rotation turns an image around a fixed point (usually the center) by a specified angle.
Rotation: Rotates the image by 45 degrees.
### Step 6:
Cropping removes parts of an image, usually by specifying a rectangular region of interest (ROI).
Cropping: Crops the image to a specific region.

## Program:
```
Developed By: Prajin S
Register Number: 212223230151
```
### Loading the image
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('cow.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(12, 8))
plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('on')
```
### i)Image Translation
```python
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]]) 
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.subplot(1, 1, 1)
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('on')
```

### ii) Image Scaling
```python
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.subplot(1, 1, 1)
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('on')
```


### iii)Image shearing

```python
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.subplot(1, 1, 1)
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('on')
```

### iv)Image Reflection
```python
reflected_image = cv2.flip(image_rgb, 1) 
plt.subplot(1,1,1)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('on')
```



### v)Image Rotation
```python
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.subplot(1,1,1)
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('on')
```



### vi)Image Cropping
```python
cropped_image = image_rgb[50:300, 100:400]
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('on')
plt.show()
```


## Output:
### Loading the image
![image](https://github.com/user-attachments/assets/adb633ee-60ab-44a1-8339-da5973f4c069)

### i)Image Translation
![image](https://github.com/user-attachments/assets/81bc2a68-2583-4515-9972-caaf8d1c03c1)


### ii) Image Scaling
![image](https://github.com/user-attachments/assets/c344f832-b7cd-4b76-95bd-ea6ca27d2761)


### iii)Image shearing
![image](https://github.com/user-attachments/assets/21800e67-c8c3-4931-a3d6-1c41edb54c02)



### iv)Image Reflection
![image](https://github.com/user-attachments/assets/85fbd3e8-5dee-424d-b72a-894c61ea6d3a)



### v)Image Rotation
![image](https://github.com/user-attachments/assets/15f1ec7c-a3d3-4348-8708-f8925cc8c676)




### vi)Image Cropping
![image](https://github.com/user-attachments/assets/72ad2472-0a6c-48cc-a302-c7b74f3a2675)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
