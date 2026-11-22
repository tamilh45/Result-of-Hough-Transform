#  Lane Detection

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

Step 1: Import Libraries

Step 2: Read the Image

Step 3: Convert to Grayscale

Step 4: Display Images

Step 5: Thresholding

Step 6: Region of Interest (ROI)

Step 7: Edge Detection (Canny)

Step 8: Gaussian Blur

Step 9: Hough Transform

Step 10: Lane Detection Logic

---
##  Instructions

* Fill ONLY in `# Your Code Here` sections
* Do NOT change existing code
* Run step-by-step
* Verify outputs

---
##  Developed By

## Name: Tamil Pavalan M    
## Reg. No: 212223110058

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('q7.jpg')  # Replace 'image.jpg' with your image path
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(719.5), np.float64(-0.5))

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(719.5), np.float64(-0.5))

# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(719.5), np.float64(-0.5))

# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(719.5), np.float64(-0.5))
```
---

##  Expected Output

* Original image

<img width="632" height="392" alt="image" src="https://github.com/user-attachments/assets/e4a7e659-9501-4b06-aaf2-37aa99a33ff7" />

* Grayscale image

<img width="642" height="397" alt="image" src="https://github.com/user-attachments/assets/18e7a7ee-ed29-4f26-8152-65b23c572d70" />

* Canny Edge Detector image

<img width="637" height="387" alt="image" src="https://github.com/user-attachments/assets/072e41aa-7b05-486f-9879-aacdf598a198" />

* Result of Hough Transform

<img width="636" height="391" alt="image" src="https://github.com/user-attachments/assets/f167c3f2-2720-46cf-a6a6-5ab710393981" />

---

## Result

Thus, the Result of Hough Transform is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---


