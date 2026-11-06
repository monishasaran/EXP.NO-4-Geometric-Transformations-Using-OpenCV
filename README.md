# EXP.NO-4-Geometric-Transformations-Using-OpenCV
# Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

# The program performs the following operations:

Image Translation

Image Scaling (Resizing)

Image Shearing

Image Reflection (Flipping)

Image Rotation

# Software Used
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

# Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image in color mode.

Step 3: Image Translation
Create a translation matrix to shift the image
Move the image 50 pixels to the right and 80 pixels down
Apply transformation using cv2.warpAffine()
Display original and translated images

Step 4: Image Scaling
Resize the image to 0.5× (downscale)
Resize the image to 2× (upscale)
Use cv2.resize()
Display original, downscaled, and upscaled images

Step 5: Image Shearing
Create transformation matrices for:
Horizontal shearing
Vertical shearing
Apply transformations using cv2.warpAffine()
Display original and sheared images

Step 6: Image Reflection
Perform flipping using cv2.flip():
Horizontal reflection
Vertical reflection
Both axes
Display all reflected images

Step 7: Image Rotation
Create rotation matrices for:
45° rotation
90° rotation
Use cv2.getRotationMatrix2D() and cv2.warpAffine()
Display original and rotated images

# Program
# Developed By:
# Name: MONISHA S
# Register No: 212225040258

# CODE:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image
image = cv2.imread('PHOTO.jpeg')

# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')

# Step 2: Image Translation
tx, ty = 100, 50
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')

# Step 3: Image Scaling
fx, fy = 5.0, 2.0
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')

# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')

# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')

# Step 6: Image Rotation
(height, width) = image.shape[:2]
angle = 45
center = (width // 2, height // 2)
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')

# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
```

# Output
<img width="296" height="402" alt="image" src="https://github.com/user-attachments/assets/6e8e95e1-eb58-4080-811d-ef5c2edab157" /> <img width="310" height="397" alt="image" src="https://github.com/user-attachments/assets/1b746d0f-7411-4f11-8903-a77beff89b8d" />
<img width="497" height="301" alt="image" src="https://github.com/user-attachments/assets/ccbad0cc-0f2e-4fa3-aedc-80b418e002d6" /> <img width="297" height="401" alt="image" src="https://github.com/user-attachments/assets/9ebabfbe-1e9e-4b07-ab4c-a79c48cb925e" />
<img width="300" height="402" alt="image" src="https://github.com/user-attachments/assets/629be2cd-b6d2-4766-96f9-4d0502610868" /> <img width="287" height="395" alt="image" src="https://github.com/user-attachments/assets/639ada31-1f3d-4ed7-b055-10b09585401f" />
<img width="492" height="401" alt="image" src="https://github.com/user-attachments/assets/7f7b41ce-5040-4052-82d6-ea35813f2ca2" />

# Result:
Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.








Result
Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
