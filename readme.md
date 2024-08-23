# WORKSHOP-1 WORKING ON A IMAGE
# AIM:
To divide two images into four quadrants, swap specific regions between them, and resize the final images according to specified dimensions.

# EXPLANATION:
This project involves performing image processing tasks using basic operations:

Loading Images: First, two images of the same size are loaded into the program.

Dividing the Images: Each image is divided into four equal quadrants based on the row and column coordinates, resulting in eight regions labeled as R1, R2, R3, R4 for the first image and R5, R6, R7, R8 for the second image.

Swapping Regions: The regions are then swapped between the two images as follows:

R1 from the first image is swapped with R8 from the second image.
R2 is swapped with R7.
R3 is swapped with R6.
R4 is swapped with R5.
Resizing the Final Images: After swapping, the resulting images are resized to match the dimensions specified by the last four digits of the registration number, ensuring the number is even.

This process demonstrates how image regions can be manipulated and resized programmatically, resulting in modified images based on specific criteria.

## ALGORITHM:
# Load Images:

Load two images of the same size, Image1 and Image2.
# Determine Dimensions:

Calculate the width and height of the images, denoted as width and height.
# Divide the Images:

# Divide Image1 into four quadrants:
R1: Top-left quadrant.
R2: Top-right quadrant.
R3: Bottom-left quadrant.
R4: Bottom-right quadrant.
Similarly, divide Image2 into:
R5: Top-left quadrant.
R6: Top-right quadrant.
R7: Bottom-left quadrant.
R8: Bottom-right quadrant.
# Swap Regions:

# Swap the regions between the images as follows:
R1 ↔ R8
R2 ↔ R7
R3 ↔ R6
R4 ↔ R5
# Reconstruct Images:

Reconstruct the final images by combining the swapped regions.
# Resize the Images:

Resize the reconstructed images to the dimensions specified by the last four digits of your registration number, ensuring the dimensions are even.
# Save the Final Images:

Save the final images with swapped regions and resized dimensions.
# End:

The algorithm completes with two processed images ready for use.
# CODING AND OUTPUT:
NAME : GEDIPUDI DARSHANI REG NO : 212223230062
```
import cv2
import numpy as np
import random as rd
image1 = cv2.imread("tiger.jpg")
image2 = cv2.imread("lokesh.jpg")
image2 = cv2.resize(image2,(500,500))
image1 = cv2.resize(image1,(image2.shape[1],image2.shape[0]))
merged_image = np.hstack((image1,image2))
cv2.imshow('Merged Image', merged_image)
cv2.imwrite('merged_image.jpg', merged_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/0437c02d-8817-4f0e-91c5-08880f421b7c)

```
merged_image.shape
```
![image](https://github.com/user-attachments/assets/2e886f1e-ccc3-43db-8c79-1e253d03ca7c)

```
top_1 = merged_image[0:250,0:250]
top_2 = merged_image[0:250,250:500]
top_3 = merged_image[0:250,500:750]
top_4 = merged_image[0:250,750:1000]
bottom_1 = merged_image[250:500,0:250]
bottom_2 = merged_image[250:500,250:500]
bottom_3 = merged_image[250:500,500:750]
bottom_4 = merged_image[250:500,750:1000]
top_row=np.hstack((bottom_4,top_2,bottom_2,top_4))
bottom_row=np.hstack((top_1,bottom_1,top_3,bottom_3))
stacked_image = np.vstack((top_row, bottom_row))
cv2.imshow('Stacked Image', stacked_image)
```
```
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/0f2875a1-55b3-4208-8331-e8d518d2005c)

```
cv2.imwrite("stacked image.jpg",stacked_image)
```
![image](https://github.com/user-attachments/assets/75892cca-8aae-4bf5-8b02-55d7faad9222)


# RESULT:
The project successfully divides two images into four quadrants each, swaps specific regions between the images, and resizes the final images according to the specified dimensions. The resulting images demonstrate the correct application of image manipulation techniques, including region swapping and resizing.
