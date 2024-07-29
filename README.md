The gaze estimation is a project where we will try to estimate where the eye is looking using Python with OpenCV.
We are taking the frames in real-time from the webcam, so to detect the eyes we will use face landmarks detection approach. We can find 68 specific landmarks of the face. To each point there is a specific index assigned.<br><br>
![landmarks_points](https://github.com/user-attachments/assets/23f1ee5c-979c-48c6-b546-34e992bcdec8)
<br><br>
We will divide our image into two sides, right and left, and draw our estimation on it.<br>
To do this, we need to detect the gaze direction of the eyes, whether they are looking left or right.<br>
When the eye looks left, the sclera (white part) fills the right side of the eye. When the eye looks right, the sclera fills the left side. When looking straight ahead, the sclera is evenly distributed.<br>
The goal is to divide the eye into two parts and determine which part shows more sclera.
<br><br>
![image](https://github.com/user-attachments/assets/a3f9529f-bcac-4a20-a5f6-6eced7f70045)
<br><br>
If more sclera is visible on the right, the eye looks left and vice versa. To detect sclera, convert the eye image to grayscale, apply a threshold, and count the white pixels. Compare the white pixels in the left and right parts to get the gaze ratio.
<br><br>
![image](https://github.com/user-attachments/assets/06411ee8-4532-4348-bf89-cc7282d477d4)
<br><br>
I'll use a vertical line as a reference and have the person look up and down to record the maximum (looking up) and minimum (looking down) lengths. We then calculate the ratio based on these lengths, with using the sclera for estimation.
<br>
or maybe there another ideas (I'm still working on it)
<br>
### The output Shoudl be as follow:
<br><br>
the ration we calculated is mapped to corresponding pixels on the frame<br>
![image](https://github.com/user-attachments/assets/ac3d3a49-7871-4f59-a843-771c25a34e4f)
<br><br>
## sample:
<br><br>
![gaze_detection_2-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/089710dd-08cb-4f18-b06e-deb3d270c46c)







