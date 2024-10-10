# Gallery Activity

This is a simple gallery that pulls up media files from ~/Pictures. This was developed in conjunction to the Camera Activity in hopes of integrating them together some day.

The media is sorted in the ascending order of their modification and presented the same. On the toolbar, there are next, previous and delete buttons are for navigation and deletion respectively.

The trash button is shifted to right side to prevent accidental clicks. In case of accidents the deleted files can be found in the trash folder and not permanently deleted.

Keyboard Shortcuts:

- Previous Media: <kbd>Left</kbd> or <kbd>Back</kbd> key
- Next Media: <kbd>Right</kbd> or <kbd>Up</kbd> key
- Delete Media: <kbd>Delete</kbd> key 
- Play/Pause Video: <kbd>P</kbd> key

<br>

# Developement 

The images are displayed using `Pixbuf` and rounded corners are drawn using drawingArea and `cairo`. The video are played using `GStreamer`

The significant blocks of code are already labeled and the code is pretty much self-explanatory. Happy exploring! 

Improvements and feats are always welcome.

<br>

# Screenshot:
<img src="https://raw.githubusercontent.com/44yu5h/gallery_activity/refs/heads/master/screenshots/ss.png">

