# Vehicle Speed Detection

![output.gif](output.gif)

Technologies used :

-   Python
-   opencv
-   dlib
    <br>

Tasks breakdown

1. Vehicle Detection
    - We are using Haarcascade classifier to identify vehicles.
2. Vehicle Tracking - ( assigning IDs to vehicles )
    - We have used corelation tracker from dlib library.
3. Speed Calculation
    - We are calculating the distance moved by the tracked vehicle
      in a second, in terms of pixels, so we need pixel per meter
      to calculate the distance travelled in meters.
    - With distance travelled per second in meters, we will get the
      speed of the vehicle.

### Features

YOLOv8 Object Detection with DeepSORT Tracking(ID + Trails)

### Dataset Used

Dataset used is myhaar.xml

### Model Details

We have used "dlib.correlation_tracker" for our project. This object lets you track the position of an object as it moves from frame to frame in a video sequence. To use it, you give the correlation_tracker the bounding box of the object you want to track in the current video frame. Then it will identify the location of the object in subsequent frames.

### Problem Statement

The model facilitates real-time vehicle speed detection, instantly alerting authorities to instances of over-speeding or violations of speed limits. This proactive system serves as a crucial preventive measure against daily occurrences of vehicle collisions attributed to high speeds, promoting road safety and averting potential accidents.

### Model Pros

1. Robust Tracking: The dlib correlation tracker is renowned for its steady performance in tracking objects across frames, which qualifies it for real-time use.
   
2. Efficiency: Its computational efficiency makes real-time tracking possible even on devices with limited resources.

3. Adaptability: The tracker ensures dependable tracking in a variety of situations by adjusting effectively to changes in the monitored object's size, orientation, and appearance.

4. Ease of Use: Researchers and developers may easily include the correlation tracker and other features of the dlib library into their work.

5. Multi-Object Tracking: It may be expanded to accommodate situations in which a video stream has to monitor several objects at once.

6. Open Source: Dlib is an object tracking task solution that is transparent and easily customisable. It is an open-source library.

## How to run project?

Follow steps:

1. Clone repo :
   `git clone ...`

2. cd (change directory) into vehicle-speed-check
   `cd 3_Vehicle-Speed-Check-Estimator`

3. Create virtual environment
   `conda create -n speed-estimator python=3.8`

4. Activate virtual environment
   `conda activate speed-estimator`

5. Install requirements
   `pip install dlib`
   `pip install opencv-python`

6. run speed_check.py script
   `python speed_check.py`

#### Note:

##### Estimating Pixels Per Metre (PPM)

The estimation of Pixels Per Metre (PPM) is a crucial step for speed calculation in our project. This process is manually performed for each specific road, as PPM values can vary significantly from one road to another. Therefore, when applying this method to different videos, adjustments to the PPM value are necessary.

##### How PPM is Estimated

The estimation involves two key measurements:

1. **Actual Road Width in Metres**: This is obtained through online resources, such as Google, to find an approximate width of the road in your country.
2. **Road Width in Pixels**: By analyzing a frame from our video footage, we determine the width of the road in pixels.

With these two measurements, we map real-world distances to those in our video frame. Pixels Per Metre (PPM) is then calculated by dividing the road width in pixels by its width in metres.

##### Calculating Speed

To estimate the speed of a vehicle, we follow these steps:

1. **Determine Pixel Distance (d_pixels)**: This represents the distance travelled by the vehicle in one frame of our video.
2. **Convert d_pixels to Metres (d_metres)**: Using our PPM value, we convert the pixel distance to metres.
3. **Calculate Speed**: The formula used is `speed = d_metres * fps * 3.6`. Here, `d_metres` is the distance travelled in one frame, and `fps` is the average frames per second obtained during video processing. The speed is initially calculated in metres per second (m/s) and then converted to kilometres per hour (km/hr) by multiplying with 3.6.
