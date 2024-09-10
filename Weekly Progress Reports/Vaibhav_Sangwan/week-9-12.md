# Week 9-12 (31 Jul -  4 Sep) Three Utilities, Fractals and Bunny Islands

## Progress - Three Utilities

### Graphical Changes
- Added the following sprites to the Three Utilities:
    - Back Button
    - Boundary
    - Home Button


### Gameplay Developments

I created the game states for when the user completes all the 6 levels that are currently present in the game. This win screen consists of a "You Win" sprite that is made up of house and utility sprites. Moreover, I also created the game state for help menu. This is to ensure that users can take a look at what they need to do in order to complete the game.

I created a sprite class for the back button that is used in the help menu. Apart from that, I also added a home button in the levels so that users can go back to the main menu of the game.

In Week 9, I also fixed some bugs that I encountered during the testing phase of the game. One of the bugs was that the supply line wasn't being rendered if the mouse went out of intermediate screen boundary. To overcome this, I added a boundary background and made appropriate changes in the Utility class to not let mouse, and hence the supply lines out of this boundary. I also fixed positions of all the buttons that were present on level screen.

### Screenshots

![Screenshot from 2024-09-10 21-06-55](https://github.com/user-attachments/assets/67c3c377-4bbb-484c-a5b6-32fa98bac32a)

![Screenshot from 2024-09-10 21-05-53](https://github.com/user-attachments/assets/cfd421de-5a07-43ee-9462-0980554b47d5)

### Commits
- https://github.com/vaibhav-sangwan/three-utilities/commit/6fbe0b947994f0cb8c502513db952142fd01ae09


## Progress - Fractals

### Graphical Changes
- Fractal Title Background
- Slider
- Simulate Button
- Help Button
- Home Button
- Page Butotn
- Logo

### Gameplay Developments
In week 10, I added the parameter controls to the game. Now the fractal formation can be controlled with these controls
Add parameter controls. These controls consist of sliders for properties such as angle, initial angle, number of iterations and thickness. These sliders also consist of step-up and step-down buttons to enhance the user experience.

These sliders have a slider ball inside of them which can be moved using a mouse hold over them. Their x-position then changes according to the position of the mouse. The property value is calculated using a linear interpolation method. The minimum property value is attached to the leftmmost slider ball position and the maximum property value is attached to the rightmost slider ball position. To provide finer control to the users, the step buttons are provided on the sliders.

I also created sprite classes for simulate button and fractal iterator. I moved the L-system configurations from simpulator game state to the fractal iterator to make the code more modular. This fractal iterator sprite consists of change fractal buttons that can be used to switch between different fractals. The simulate button is added to let the users finalise on property values first without visualising the intermediate results.

I also added the game state for main menu. The main menu consists of an interactive game logo. When you move to touch any of the characters in the game logo, they move away and up from their original position giving a cool little effect. Instead of making different movable sprites for different characters, I made the logo such that it consists of two instances of game name's text rendered over it. Then I hide one of the instances by drawing over it using pygame's draw submodule. Whenever the user tries to move their mouse over to a character, the rectangle drawn over other instance moves downwards to the visible instance, giving an illusion that the character is moving upwards.

### Screenshots
![Screenshot from 2024-09-10 22-00-59](https://github.com/user-attachments/assets/f09941ad-cecd-43f5-8de9-8e86bd81f4a6)
![Screenshot from 2024-09-10 22-00-23](https://github.com/user-attachments/assets/e4ebd364-0922-4c72-8a0f-003fa4a630fa)

### Commits
- https://github.com/vaibhav-sangwan/fractals/commit/f9b83de8de1918bedc9e00e03b6be656822229f1
- https://github.com/vaibhav-sangwan/fractals/commit/ded5f69cb5441989180f060276e49338d501b125

## Progress - Bunny Islands

### Graphical Changes
- Blue Bunny
- Red Bunny
- Grid
- Tiles (numbered from 1 to 6) 

### Gameplay Developments
Bunny Islands is a puzzle game developed for Sugar. There are 6 pieces of a puzzle. On each piece, there's a bunny which is either colored red or green. The goal of the puzzle is to organise each piece on the board in such a fashion that the red colored bunnies and green colored bunnies are never on the same island. There are 400+ solutions to this puzzle. I initialised and setup a new repository for the Fractals activity. I added a README file for the same consisting of following subsections:
- What is this?
- How to use?
- How to run?

I added the GNU General Public License v3.0 and it's short version in every file. Also, I added a placeholder sugar activity icon (taken from Hello World Activity) and created a sugar package by adding `activity/activity.info`, `setup.py` and `activity.py` files.

The activity.py consists of a build_toolbar() method that is used to add ActivityIcon and Stop buttons to the activity toolbar. Moreover I included sugargame files to the activity as I intended to develop the simulation using pygame. I created `main.py` containing the Bunny Islands class and run() function. This is the entry point of game. This initial setup also consisted of creation of a game state manager.

I also created the game state for Puzzle Board in Week 12. Detailed information about the game state is given below.

### Puzzle Board
The puzzle board game state currently renders a grid on which all the puzzle tiles can be placed. These tiles will be automatically snapped to the grid when mouse is hovered over it. So, in the state, apart from grid, all the tiles are rendered as well as the background is filled with water.

As for game components used in this state, the major development is done on Grid class and Tile class. Each of the tiles can exist in one of the following states - 
1) Unplaced
2) Focused
3) Placed

When mouse is clicked on an unplaced tile, it is put into focus. Any tile that was previously in focus will be returned to it's previous state - whether placed or unplaced. Now, when a tile is in focused state, certain actions can be performed on it. If the tile is placed and focused, deletion from grid operation can be performed on it using 'D' key. Else if tile is focused and unplaced, rotate clockwise and rotate anticlockwise operations can be performed on it using right and left arrow keys respectively.

The tiles also have a snap method attached to them that controls their snapping to grid behaviour. The grid is divided into rows and columns. So, the snap method gets the topleft coordinate of the held tile, and makes it a multiple of row and cell height, giving the effect of snapping. Also, tint colors are added to the held tiles. A red tint suggests that the held tile cannot be placed because some or all of the underlying cells are occupied. Whereas a green tint suggests that the tile can be successfully placed.

![Screenshot from 2024-09-10 21-35-16](https://github.com/user-attachments/assets/e305990d-d2d1-4898-bfa1-b33c1c90cb58)

### Commits
- https://github.com/vaibhav-sangwan/bunny-islands/commit/276ccd2a9f3c0205517b06b88db43f55aac4bfbf
- https://github.com/vaibhav-sangwan/bunny-islands/commit/276ccd2a9f3c0205517b06b88db43f55aac4bfbf
