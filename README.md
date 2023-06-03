# Lip-Reading-Model
Using a 3D-Convolution Neural Network Architecture to generate text from the movement of lips from extracted gifs from .mp4 videos.
#### Note that - No sound has been used in this at all.

## Data Aquisition:
2 files :
1. Video format in mpg

![image](https://github.com/itssaiii/Lip-Reading-Model/assets/73930142/deb9c49f-3053-41df-b4d1-71fc545ad9a2)


2. Alignments in .align format where the words of the particular video had been stored



    ![image](https://github.com/itssaiii/Lip-Reading-Model/assets/73930142/d667eef3-c6cc-4c7f-9ad7-4ab908ee7647)
    
    
Dataset Link: 
https://drive.google.com/uc?id=1YlvpDLix3S-U8fd-gqRwPcWXAXm8JwjL

## Data Preprocessing: 
Preprocessing Steps

1.	Create an empty list called frames to store the preprocessed frames.

2.	Use the OpenCV function cv2.VideoCapture to initialize a video capture object pox for reading frames from the video file specified by the path.

3.	Iterate through each frame of the video using a loop that runs for the number of frames in the video (obtained with pox.get(cv2.CAP_PROP_FRAME_COUNT)).

4.	Read each frame using pox.read(), which returns a boolean value ret indicating if the frame was read successfully and the actual frame data.

5.	Convert the frame from RGB color format to grayscale using TensorFlow's tf.image.rgb_to_grayscale function. Grayscale simplifies further processing by representing the image with shades of gray only.

6.	Crop a specific region of interest from the frame using slicing (frame[190:236, 80:220, :]). This extracts a specific portion of the frame defined by the provided indices. Adjust these indices according to the desired region.


7.	Calculate the mean of the frames using TensorFlow's tf.math.reduce_mean function.

8.	Calculate the standard deviation of the frames after converting them to tf.float32 using tf.math.reduce_std(tf.cast(frames, tf.float32)).

9.	Normalize the frames by subtracting the mean and dividing by the standard deviation to achieve zero mean and unit variance. The normalization is performed using TensorFlow's tf.cast and mathematical operations.

10.	Return the preprocessed frames.


## The exctracted gif from the video which will be fed to the Model: 


![animation](https://github.com/itssaiii/Lip-Reading-Model/assets/73930142/f691eabf-805b-4127-9441-df3c7a67dae0)

