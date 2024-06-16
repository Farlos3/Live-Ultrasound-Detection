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
## Performance
### Detection (COCO)
| Model   | size (pixels) | mAP<sub>val</sub> 50-95 | mAP<sub>val</sub> 50 | params (M) | FLOPs (B) |
|---------|----------------|-----------------------|---------------------|------------|-----------|
| YOLOv9t | 640            | 38.3                  | 53.1                | 2.0        | 7.7       |
| YOLOv9s | 640            | 46.8                  | 63.4                | 7.2        | 26.7      |
| YOLOv9m | 640            | 51.4                  | 68.1                | 20.1       | 76.8      |
| YOLOv9c | 640            | 53.0                  | 70.2                | 25.5       | 102.8     |
| YOLOv9e | 640            | 55.6                  | 72.8                | 58.1       | 192.5     |

## Example usage with bounding box
![image](https://github.com/Farlos3/Live-Ultrasound-Detection/assets/86741684/ef184b15-6a73-49ce-af65-141e585924dd)
<br>refer : https://www.sciencedirect.com/science/article/abs/pii/S0208521618300068)
