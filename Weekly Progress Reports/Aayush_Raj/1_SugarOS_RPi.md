# Sugar OS for Raspberry Pi

Please check out the [repo](https://github.com/44yu5h/sugar-rpi-os). It will provide more details than you will get here.

The repository is based off of the [pi-gen](https://github.com/RPi-Distro/pi-gen/) and the steps to run and contribute further is documented in the readme file on the repo. 

The `sugar-os v0.1` is of **1.5GB** at default compression. It includes all the packages for desktop environment, sugar, and sugar activities.

Here's the commit message:

- Generate an RPi OS with sugar shell installed
- Add some activities (default ones + tower-of-hanoi, number-guessing, flappy (by Vaibhav), turtleart-activity, and rpi_control_center)
- Temporary fix the browse-activity issue (remove v207 that comes from apt, install v208, install dependencies)
- Lacks the RPi sensor libraries for now. TODO: clone rpi-lib from my repo and paste it in python3.xx/site-packages (or as the readme directs).
