# Image-Handling-and-Pixel-Transformations-Using-OpenCV 
### NAME:MARINO SARISHA T
### REG NO:212223240084
## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** MARINO SARISHA T
- **Register Number:** 212223240084

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```
img = cv2.imread('Eagle_in_Flight.jpg')
gray_image = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
plt.imshow(img_gray, cmap='gray')
plt.axis("off") 
plt.show()
```
![Screenshot 2025-03-07 102909](https://github.com/user-attachments/assets/e04e8015-1384-43cb-88ff-5c9abc2f39ab)

#### 2. Print the image width, height & Channel.
```
img.shape
```
![Screenshot 2025-03-07 102925](https://github.com/user-attachments/assets/cd4ec345-6358-4002-89ab-c1011687cf52)

#### 3. Display the image using matplotlib imshow().
```
img = cv2.imread("Eagle_in_Flight.jpg")
plt.imshow(img[:, :, ::-1]);
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 103630](https://github.com/user-attachments/assets/ed0fd24a-4409-4159-beba-e40458d9401e)

#### 4. Save the image as a PNG file using OpenCV imwrite().
```
img2 = cv2.imwrite('Eagle.png',img)
```
#### 5. Read the saved image above as a color image using cv2.cvtColor().
```
img_copy = cv2.imread('Eagle.png')
img_rgb = cv2.cvtColor(img_copy, cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```
plt.imshow(img_rgb)
plt.axis("off")
plt.show()
img_copy.shape
```
![Screenshot 2025-03-07 110917](https://github.com/user-attachments/assets/45567777-3b89-4a00-8996-b4e289c8706b)

#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
image_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
cr = image_rgb[0:450,200:550] 
plt.imshow(cr)
plt.title("Cropped Region")
plt.axis("off")
plt.show()
cr.shape
```
![Screenshot 2025-03-07 111824](https://github.com/user-attachments/assets/2938024e-79b7-4aef-95f4-21850cc1cede)

#### 8. Resize the image up by a factor of 2x.
```python
res = cv2.resize(cr, (900, 700))
plt.imshow(res)
plt.title("Resized image")
plt.axis("off")
res.shape
```
![Screenshot 2025-03-07 231641](https://github.com/user-attachments/assets/b9d5bfc7-039b-4849-9174-758e6d02b5c3)


#### 9. Flip the cropped/resized image horizontally.
```python
flip= cv2.flip(res,1)
plt.imshow(flip)
plt.title("Flipped Horizontally")
plt.axis("off")
flip.shape
```
![Screenshot 2025-03-07 231733](https://github.com/user-attachments/assets/ba4195a8-9fe2-4299-a437-f1c9b7e0f01b)

#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
img=cv2.imread('Apollo-11-launch.jpg')
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
```
![Screenshot 2025-03-07 114246](https://github.com/user-attachments/assets/bec7cd81-d16b-427a-bab5-87a511b45d5f)

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = cv2.putText(img, "Apollo 11 Saturn V Launch, July 16, 1969", (300, 700),cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)  
plt.imshow(text, cmap='gray')  
plt.title("New image")
plt.axis("off")
plt.show()  
```
![Screenshot 2025-03-07 114304](https://github.com/user-attachments/assets/7ce48473-32da-48c7-a047-186720beec22)


#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
cv2.rectangle(img, (450,650),(800,50),(255,0,255), thickness = 3)
plt.imshow(img) 
plt.title("Image with rectangle")
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 114343](https://github.com/user-attachments/assets/61419149-dacf-4bab-9242-115669094b1f)

#### 13. Display the final annotated image.
```python
plt.title("Annotated image")
plt.imshow(img)
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 114356](https://github.com/user-attachments/assets/858ad763-d5ff-4303-a116-74bff4e64158)

#### 14. Read the image ('Boy.jpg').
```python
img_3 =cv2.imread('boy.jpg')
img_3_rgb= cv2.cvtColor(img_3, cv2.COLOR_BGR2RGB) 

```

#### 15. Adjust the brightness of the image.
```python
m = np.ones(img_3_rgb.shape, dtype="uint8") * 75
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img_3_rgb, m)  
img_darker = cv2.subtract(img_3_rgb, m)  

```
#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
plt.title("Original Image")
plt.imshow(img_3_rgb)
plt.axis("off")
```
![Screenshot 2025-03-07 225626](https://github.com/user-attachments/assets/8680d5af-c92d-4403-a804-cefc1b943801)

```
plt.title("Brighter Image")
plt.imshow(img_brighter)
plt.axis("off")
```
![Screenshot 2025-03-07 225039](https://github.com/user-attachments/assets/d3699e99-1701-4636-b5f1-1d2a0c161f71)
```
plt.title("Darker Image")
plt.imshow(img_darker)
plt.axis("off")
```
![Screenshot 2025-03-07 225030](https://github.com/user-attachments/assets/29379921-4d98-4ac2-ba95-80986ab8a58f)

#### 18. Modify the image contrast.
```python
matrix1 = np.ones(img_3_rgb.shape, dtype="float32") * 1.5
matrix2 = np.ones(img_3_rgb.shape, dtype="float32") * 3.0
img_higher1 = cv2.multiply(img_3_rgb.astype("float32"), matrix1).clip(0,255).astype("uint8")
img_higher2 = cv2.multiply(img_3_rgb.astype("float32"), matrix2).clip(0,255).astype("uint8")
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
plt.title("Original Image")
plt.imshow(img_3_rgb)
plt.axis("off")
```
![Screenshot 2025-03-07 225626](https://github.com/user-attachments/assets/64a587a2-c349-4dac-a22a-2c8374302883)

```
plt.title("Lower Contrast")
plt.imshow(img_higher1)
plt.axis("off")
```
![Screenshot 2025-03-07 225055](https://github.com/user-attachments/assets/18467b43-7122-42bf-a947-8a8210ee9686)

```
plt.title("Higher Contrast")
plt.imshow(img_higher2)
plt.axis("off")
```
![Screenshot 2025-03-07 225108](https://github.com/user-attachments/assets/057fbb2d-8a34-4bc2-980f-17633fdd358a)

#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
b, g, r = cv2.split(img_3_rgb)
```
```python
plt.title("Blue Color")
plt.imshow(b)
plt.axis("off")
```
![Screenshot 2025-03-07 231045](https://github.com/user-attachments/assets/d3c47310-18b1-4f56-b924-1f3cbe0a11c2)
```
plt.title("Green Color")
plt.imshow(g)
plt.axis("off")
```
![Screenshot 2025-03-07 231056](https://github.com/user-attachments/assets/12ee820e-47a1-4438-8e34-988dd6e177f6)
```
plt.title("Red Color")
plt.imshow(r)
plt.axis("off")
```
![Screenshot 2025-03-07 231107](https://github.com/user-attachments/assets/5304dea8-7e27-446d-98b5-005f67bec859)

#### 21. Merged the R, G, B , displays along with the original image

```
merged_rgb = cv2.merge([r, g, b])
plt.imshow(merged_rgb)
plt.title("Merged RGB Image")
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 230702](https://github.com/user-attachments/assets/f2758460-9fe4-4d04-98ec-0e95aed9716a)

#### 22. Split the image into the H, S, V components & Display the channels.
```python
hsv_img = cv2.cvtColor(img_3_rgb, cv2.COLOR_RGB2HSV)
h, s, v = cv2.split(hsv_img)
```
```
plt.imshow(h)
plt.title("Hue Channel")
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 225156](https://github.com/user-attachments/assets/18137a96-a9ce-455b-9ec0-260e738ca8bc)
```
plt.imshow(s)
plt.title("Saturation Channel")
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 225206](https://github.com/user-attachments/assets/77fced4c-ab29-4b4d-9e64-8e36745059a3)

```
plt.imshow(v)
plt.title("Value Channel")
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 225215](https://github.com/user-attachments/assets/7b2117f0-7cf0-4635-a8a6-ca233f37adaf)

#### 23. Merged the H, S, V, displays along with original image.
```
merged_hsv = cv2.merge([h, s, v])
plt.imshow(merged_rgb)
plt.title("Merged HSV Image")
plt.axis("off")
plt.show()
```
![Screenshot 2025-03-07 225227](https://github.com/user-attachments/assets/a347509d-fbac-481a-aaed-17935bd7ad77)

## Output:
- **i)** Read and Display an Image.
 ![Screenshot 2025-03-07 103630](https://github.com/user-attachments/assets/ed0fd24a-4409-4159-beba-e40458d9401e)
- **ii)** Adjust Image Brightness.
![Screenshot 2025-03-07 225626](https://github.com/user-attachments/assets/bce2aca5-bf7d-4ec4-897a-0b80052b2b2c)
![Screenshot 2025-03-07 225039](https://github.com/user-attachments/assets/c487ce20-6a73-4cc0-910b-136c5fb64441)
![Screenshot 2025-03-07 225030](https://github.com/user-attachments/assets/50793486-740a-437e-9740-afbdf76cf24a)

- **iii)** Modify Image Contrast.
![Screenshot 2025-03-07 225055](https://github.com/user-attachments/assets/86bdc429-f3bb-453e-8e9e-ce69566e9105)
![Screenshot 2025-03-07 225108](https://github.com/user-attachments/assets/d612b273-74eb-4df8-b742-cdcbb2dc1c4e)

- **iv)** Generate Third Image Using Bitwise Operations.
![Screenshot 2025-03-07 225156](https://github.com/user-attachments/assets/2c1c5515-adcb-4a6e-a98e-79cd5aecc171)
![Screenshot 2025-03-07 225206](https://github.com/user-attachments/assets/2d98b9d5-952c-469e-a08e-064f84136272)
![Screenshot 2025-03-07 225215](https://github.com/user-attachments/assets/75c158ec-a010-4537-bb8c-a827863cbb2a)

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

