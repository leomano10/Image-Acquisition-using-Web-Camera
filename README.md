# Experiment No: 02 – Image Acquisition using Web Camera

**Name:** manorajapriyan.l.e  
**Reg. No:** 212225040227

---

# Aim

To acquire images and videos using a web camera and perform basic operations such as capturing an image, displaying live video, resizing the video, and rotating the video using OpenCV.

---

# Software Required

- Python 3.x
- OpenCV (`cv2`)
- Matplotlib
- Jupyter Notebook

---

# i) Capture and Save a Frame as JPG File

## Program

```python
import cv2
import matplotlib.pyplot as plt

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()

captured_image = cv2.imread("captured_frame.jpg")

plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()
```

---

# ii) Display the Live Video

## Program

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

# iii) Display the Video by Resizing the Window

## Program

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

# iv) Rotate and Display the Video

## Program

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

# Output

## i) Captured Frame

<p align="center">
  <img width="608" height="450" alt="image" src="https://github.com/user-attachments/assets/0d8fcb52-ccc6-4810-98c1-47f5663b9d80" />

</p>

---

## ii) Live Video Display

<p align="center">
  <img width="603" height="455" alt="image" src="https://github.com/user-attachments/assets/2c214316-284f-43cb-a399-309f1759129b" />

</p>

---

## iii) Resized Video Display

<p align="center">
  <img width="303" height="455" alt="image" src="https://github.com/user-attachments/assets/00f1a872-2122-4e31-b0f4-43fbd54f4a8b" />

</p>

---

## iv) Rotated Video Display

<p align="center">
  <img width="342" height="461" alt="image" src="https://github.com/user-attachments/assets/ab82b94e-d0d5-4440-a391-266f1af1e2b4" />

</p>

---

# Result

Successfully acquired images from the webcam, saved a frame as a JPG file, displayed the live webcam video, resized the video, and rotated the video using OpenCV.
