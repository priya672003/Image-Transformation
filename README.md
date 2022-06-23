### EX.NO : 05

### DATE : 

# <p align="center"> Image-Transformation </p> 
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step1:

Import the necessary libraries and read the original image and save it as a image variable.

### Step2:

Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]])
translated_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step3:

Scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]])
scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step4:

Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]])
sheared_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))


### Step5:

Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]])
reflected_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

### Step6:

Rotate the image using angle=np.radians(45) M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]])
rotated_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step7:

Crop the image using cropped_img=input_img[20:150,60:230]

### Step8:

Display all the Transformed images.


## Program:

Developed By: PRIYADARSHINI R

Register Number:212220230038

i)Image Translation

```python3

import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image=cv2.imread("img.jpg")
input_image=cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
rows,cols,dim = input_image.shape
M = np.float32([[1,0,100],
               [0,1,100],
               [0,0,1]])
translated_image = cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()

```

ii) Image Scaling

```python3
M=np.float32([[1.5,0,0],
             [0,1.8,0],
             [0,0,1]])
scaled_img=cv2.warpPerspective(input_image,M,(cols*2,rows*2))
plt.axis('off')
plt.imshow(scaled_img)
plt.show()

```

iii)Image shearing

```python3

rows,cols,dim=input_image.shape
M_x=np.float32([[1,0.5],
             [0,1,0],
             [0,0,1]])
M_y=np.float32([[1,0,0],
               [0.5,1,0],
               [0,0,1]])
sheared_img_xaxis=cv2.warpPerspective(input_image,M_x,(int(cols*1.5),int(rows*1.5)))
sheared_img_yaxis=cv2.warpPerspective(input_image,M_y,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
plt.imshow(sheared_img_xaxis)
plt.show()
plt.axis('off')
plt.imshow(sheared_img_yaxis)
plt.show()

```
iv)Image Reflection

```python3

M_x=np.float32([[1,0,0],
               [0,-1,rows],
               [0,0,1]])
M_y=np.float32([[-1,0,cols],
               [0,1,0],
               [0,0,1]])
reflected_img_xaxis=cv2.warpPerspective(input_image,M_x,(cols,rows))
reflected_img_yaxis=cv2.warpPerspective(input_image,M_y,(cols,rows))
plt.axis('off')
plt.imshow(reflected_img_xaxis)
plt.show()
plt.axis('off')
plt.imshow(reflected_img_yaxis)
plt.show()

```

v)Image Rotation

```python3 

angle=np.radians(45)
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotated_img=cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(rotated_img)
plt.show()

```
vi)Image Cropping

```python3

cropped_img=input_image[300:450,300:430]
plt.axis('off')
plt.imshow(cropped_img)
plt.show()

```

## Output:
### i)Image Translation

![image](https://user-images.githubusercontent.com/81132849/166143886-d0356d48-017d-47d2-9b03-3f15b9304f1a.png)


### ii) Image Scaling

![image](https://user-images.githubusercontent.com/81132849/166143890-89dfdae1-c0c1-4e20-abf9-c9023839baf4.png)


### iii)Image shearing

![image](https://user-images.githubusercontent.com/81132849/166143901-1ce2bd95-42f9-4a29-a326-f3c3382c6898.png)

![image](https://user-images.githubusercontent.com/81132849/166143906-9c800898-c5e9-4c20-aa27-2f579801e979.png)



### iv)Image Reflection

![image](https://user-images.githubusercontent.com/81132849/166143912-f3755616-898f-4b61-abfb-09920632ea24.png)

![image](https://user-images.githubusercontent.com/81132849/166143914-6522d062-0c18-42e2-baa9-36caaf32b418.png)




### v)Image Rotation

![image](https://user-images.githubusercontent.com/81132849/166143924-b79b001d-c385-4e2d-8a14-f46c153a7c17.png)



### vi)Image Cropping

![image](https://user-images.githubusercontent.com/81132849/166143955-f6a64557-17d6-4e1d-bf34-2439ffa3272b.png)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
