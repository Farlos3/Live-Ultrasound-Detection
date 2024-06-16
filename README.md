# Live-Ultrasound-Detection
## Pre-Processing
#### Perform DFT on Each Color Channel :
- Split the input image into its color channels.
- Apply Discrete Fourier Transform (DFT) to each channel.
#### Create Butterworth Low-Pass Filter Mask :
- Compute the distance from the center of the frequency domain for each pixel.
- Create a Butterworth low-pass filter mask based on the specified cutoff frequency (d0) and filter order (n).
#### Apply Mask and Inverse DFT :
- Apply the Butterworth filter mask to the shifted DFT of the image.
- Perform the inverse DFT to convert the filtered frequency domain image back to the spatial domain.
#### Normalize the Result :
- Normalize the result to ensure pixel values are in the range of 0 to 255.
- Convert the result back to an 8-bit unsigned integer format.
#### Merge the Filtered Channels :
- Combine the filtered channels back into a single image.

## Model
The chosen model is YoLov9e due to its excellent prediction performance and fast inference time.
![image](https://github.com/Farlos3/Live-Ultrasound-Detection/assets/86741684/fb8bd153-847c-48d7-bf96-0a010f06a2c7)
