# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
python
# Developed By: Srivatsan G
# Register Number: 212223230216

## program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
gray_image = cv2.imread('th.jpg', cv2.IMREAD_GRAYSCALE)
```

```plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')
```

## output:

![image](https://github.com/user-attachments/assets/9ade9f53-ce16-4773-9489-e067621ce4b3)

```
plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
```

![image](https://github.com/user-attachments/assets/2da7af41-66b4-4bc5-bdd3-5a95a8339d7d)

```
equalized_gray_image = cv2.equalizeHist(gray_image)
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
```

![image](https://github.com/user-attachments/assets/4e7d985c-a194-4fd5-b69a-dc83247eaee7)

```
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')
```

![image](https://github.com/user-attachments/assets/8a481858-4152-4e25-8b3d-723540e0a20f)

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
color_image = cv2.imread('th (1).jpg')
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
```

![image](https://github.com/user-attachments/assets/3f31030f-55d7-4d96-b441-aa81c2570479)

```
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
```

![image](https://github.com/user-attachments/assets/177bdc45-9fd6-4c34-9d3c-89c47daf8955)
```
blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])
equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])
```


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
