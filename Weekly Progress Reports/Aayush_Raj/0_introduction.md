# Sugar on Raspberry Pi

Hi! I am [Aayush Raj](github.com/44yu5h), studying in 1st year at BITS Pilani Goa, India. I was selected in the DMP 2024 program offered by C4GT. [Anurag Singh](https://github.com/drLite35) (selected in GSoC) and I were selected to work together on this project.

My mentors:
- Ibiam Chihurumnaya
- Walter Bender

Walter and Ibiam were wonderful, to say the least. They gave great guidance while at the same time letting me explore and add things that I thought were necessary or a great addition. The weekly meetings were great for adjusting the course of development."\
Special thanks to Ibiam. He helped me learn a lot about the best practices and what good code should look like in production level software. Since, till this point, all my projects were small and personal, and I could do whatever I felt worked no matter the implementation. At times, he went so far as to restructure my whole messy code haha. Thanks Ibiam.

## Objectives achieved in this summer were:
 - Build OS for Raspberry Pi
 - Added a sensor library (having 10-15 sensor definitions)
 - Built a Camera (to use camera modules)
 - Built a Gallery Activity (shows media in ~/Pictures)
 - Built a Control Center to change RPi's settings via GUI
 - Added sensors to Turtle Art Activity
 - Made a setup video
 - Fixed Browser Activity

<br>

*I will be talking only about my work this summer here.\
Below are the objectives achieved this summer*

<br>

# 1. [Sugar OS for Raspberry Pi](1_SugarOS_RPi.md)

The repository lives [here](https://github.com/44yu5h/sugar-rpi-os)

We successfully developed `sugar-os v0.1` which is **1.5GB**. This would have not been possible without Ibiam.

It includes all the packages for desktop environment, sugar, and sugar activities.

**As of `SugarOS v0.1`, activities that are pre-installed are:**
- Flappy 
- RPI Control Center
- Number Guessing
- Tower of Hanoi
- Turtle Art
- Default activities (Calculate, Chat, Image Viewer, Pippy, Read, Terminal, Write and Browse)

You can edit, generate, and install your own RPi OS using the repo and detailed instructions provided there. 

<br>

# 2. [Sensors Library](2_SensorsLibrary.md)

The library lives [here](https://github.com/44yu5h/rpi_sensor_libs)

These libraries can be used globally from any activity.

### Features/Sensors implemented so far:

- Digital output
- Digital input
- PWM Output
- Delay
- Button
- HC-SR04 Ultrasonic distance sensor
- DHT11 Temperature and Humidity sensor
- OLED display
- Servo Motor
- DC Motor (not tested)

<br>

# 3. [Camera Activity](3_CameraActivity.md)

The library repo [here](https://github.com/44yu5h/rpi_camera_activity)

You can take pictures and videos with it as one would expect. It saves the media files in `~/Pictures/Camera`

### Features:
- Show/Hide the grid overlay.
- Flip the camera preview horizontally or vertically.
- Capture images by clicking the "Snap" button.
- Capture videos using "Video" button.
- Video timer indicator

<br>

# 4. [Gallery Activity](4_GalleryActivity.md)

The repo live [here](https://github.com/44yu5h/gallery_activity)

This is a simple gallery that pulls up media files from `~/Pictures`.\
The latest modified files are displayed first.

On the toolbar, next, previous and delete buttons are for navigation and deletion respectively

### Keyboard Shortcuts:
- Previous Media: <kbd>Left</kbd> or <kbd>Back</kbd> key
- Next Media: <kbd>Right</kbd> or <kbd>Up</kbd> key
- Delete Media: <kbd>Delete</kbd> key 
- Play/Pause Video: <kbd>P</kbd> key

<br>

# 5. [Control Center Activity](5_ControlCenterActivity.md)

The repo live [here](https://github.com/44yu5h/rpi_control_center)

A control center application for Raspberry Pi, designed to manage and monitor various Raspberry Pi functionalities via a user-friendly interface.


### Features:
- **GPIO Control**: Control the GPIO pins on the Raspberry Pi.
- **I2C**: View and obtain addresses of connected I2C devices.
- **SPI**: View and obtain addresses of connected SPI devices.
- **Audio**: Check and manage connected speaker and microphone.
- **Camera**: View connected cameras.
- **Settings**: Control the state (on/off) of various settings such as I2C, SPI, VNC, Boot Splash, etc.

<br>

# 6. [TurtleArt RPi Plugin](6_TurtleArtRPiPlugin.md)

The repo lives [here](https://github.com/44yu5h/turtleart-activity)\
The added plugin is [here](https://github.com/44yu5h/turtleart-activity/tree/master/plugins/rpi)

A plugin palette to add Blocks to TurtleArt to control sensors! It has a super simple installation process. Just run an "install requirements" block, wait for 2 minutes, and you are good to go!

### Added Blocks:
- install requirements (install/update dependencies)
- GPIO input
- GPIO output
- Button
- Delay (in ms)
- HIGH/LOW (1/0)
- HCSR04 sensor
- distance (for HCSR04)
- Oled display (define oled)
- display text (for oled) 
