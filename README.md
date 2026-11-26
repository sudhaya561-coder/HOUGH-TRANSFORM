# EXP 7 : HOUGH-TRANSFORM

# REG NO :212225230287
# NAME : UDHAYA S

# AIM:
To write a Python program to detect the lines using Hough Transform.

# Algorithm / Procedure :

1. Import the required libraries: OpenCV, NumPy and Matplotlib.
2. Read the input image using `cv2.imread()` and convert it into a grayscale image.
3. Apply the Canny edge detection algorithm using `cv2.Canny()` to detect edges.
4. Apply the Hough Transform using `cv2.HoughLines()` to detect straight lines.
5. Draw the detected lines on the original image using `cv2.line()`.
6. Display the input image and final output image using Matplotlib.

# PROGRAM :
~~~ PYTHON
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('udhaya.jpeg')  # Replace 'image.jpg' with your image path
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
 #Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off');
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
# Draw detected lines on the original image
if lines is not None:  # lines is None when nothing is detected
    for line in lines:
        x1, y1, x2, y2 = line.reshape(-1)  # Works for shape (1,4) and (4,)
        cv2.line(image, (x1, y1), (x2, y2), (0, 0, 255), 2)  # Red in BGR (no green)
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off');

~~~
# OUTPUT :
```
<img width="327" height="465" alt="image" src="https://github.com/user-attachments/assets/ef55db7e-cc80-4527-bd7c-87168aa08501" />
```


```
<img width="327" height="465" alt="image" src="https://github.com/user-attachments/assets/a7c1c477-38ff-4818-88a6-7774cbdf604c" />
```

```
<img width="320" height="453" alt="image" src="https://github.com/user-attachments/assets/d775c98a-5391-4f74-9868-cbccce6028c5" />
```

```
<img width="325" height="458" alt="image" src="https://github.com/user-attachments/assets/da356c9b-bd04-4232-b0dd-538fa83e56f3" />
```

```
<img width="342" height="467" alt="image" src="https://github.com/user-attachments/assets/c71cdf17-8188-46f5-9b2d-90e2ae727c67" />

```


**Result:**
Thus, the Hough Transform is implemented successfully to detect straight lines in the input image.
