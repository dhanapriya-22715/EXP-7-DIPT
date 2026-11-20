# EXP NO:7-Record-HOUGH TRANSFORM
## NAME : Dhanappriya S
## REG NO :212224230056

# Aim:
To detect straight lines in an input image using the Canny edge detector and the Probabilistic Hough Transform (HoughLinesP) in OpenCV.
# Procedure:
1. **Start** the program and import the required libraries (`cv2`, `numpy`, and `matplotlib.pyplot`).
2. **Load** the input image using `cv2.imread()`.
3. **Convert** the loaded BGR image into a grayscale image using `cv2.cvtColor()`.
4. **Detect edges** in the grayscale image using the Canny edge detector (`cv2.Canny()`).
5. **Apply Hough Transform** (`cv2.HoughLinesP()`) on the edge-detected image to find the start and end coordinates $(x_1, y_1, x_2, y_2)$ of straight line segments.
6. **Draw the detected lines** onto the image using `cv2.line()` for each set of coordinates.
7. **Display** the original image, grayscale image, Canny edge image, and the final image with detected lines using `matplotlib.pyplot.imshow()`.
8. **Stop** the program.v

# Code:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('photo.jpg')  # Replace 'image.jpg' with your image path
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
# Output:
<img width="807" height="557" alt="image" src="https://github.com/user-attachments/assets/3f60a5cf-914c-41db-9384-f4d100ad06b7" />
<img width="880" height="575" alt="image" src="https://github.com/user-attachments/assets/16908cdf-9f02-495b-b876-a55e63f63a94" />
<img width="858" height="558" alt="image" src="https://github.com/user-attachments/assets/e2ce9002-261b-48b6-a66e-c4e863267c22" />
<img width="841" height="532" alt="image" src="https://github.com/user-attachments/assets/58a11deb-128c-45e6-84e1-f921a4201738" />

# Result:
Thus to detect straight lines in an input image using the Canny edge detector and the Probabilistic Hough Transform (HoughLinesP) in OpenCV was verified succssfully.



