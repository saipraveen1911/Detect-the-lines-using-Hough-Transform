# Detect-the-lines-using-Hough-Transform

##  Developed By: SAI PRAVEEN C

## Register: No: 212225230239

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```
image = cv2.imread('sai1.jpeg') 
```

---

###  Step 3: Convert to Grayscale

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

###  Step 5: Display Images

```

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
```

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

### Step 6: Edge Detection (Canny)

```
edges = cv2.Canny(gray_image, 50, 150)
```

```
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

---


###  Step 7: Hough Transform

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line.flatten()
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```

---

# Step 8: Display the result of Hough Transform (Image with lines):
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```

---

## Output:

## Original image:

<img width="315" height="417" alt="image" src="https://github.com/user-attachments/assets/5f67cda2-8fed-474f-a545-5b5d9af16ea4" />

## Grayscale image:

<img width="331" height="428" alt="image" src="https://github.com/user-attachments/assets/e91f6112-93a4-4a2a-9108-3ae60ebaebb9" />


## Canny Edge Detector:

<img width="325" height="422" alt="image" src="https://github.com/user-attachments/assets/6ac8c085-f695-4619-857b-d2e2dccc9e14" />

## Hough Transform:

<img width="316" height="420" alt="image" src="https://github.com/user-attachments/assets/80f8e9f8-6254-4771-a16f-92915e23343a" />


## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
