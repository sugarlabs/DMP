# Week 7-8 (17 Jul -  30 July) Three Utilities and Fractals

## Progress - Three Utilities

### Graphical Changes
- Added the following sprites to the Three Utilities:
    - Game Logo
    - Play Button
    - Help Button
    - Animated supply lines with a grid background

### Gameplay Developments

I had implemented the levels logic prior to the commencement of DMP 2024. But the code wasn't very modular and didn't include the concept of game states and game state manager. So I first refactored all the code to make it more modular so that more game states can be added easily. This included creation of game state manager, game states for main menu and levels, and moving all the sprites to components.

Over the two weeks, I developed the following game states - 
- Main Menu
- Level (Created game state and moved the corresponding code from `main.py`)
- Fixed a bug where solution lines were originating from a lower position than expected
- Added new fonts to the activity

### Main Menu

![image](https://github.com/user-attachments/assets/a33ee7d6-c197-4129-b5b2-19f7fb3c5663)

I created a logo and added menu buttons to play the levels and open the help menu. I also added an animated background. This really improved the visual experience exponentially. The animated background consists of a light-grey grid where the intersections of rows and columns meet to make nodes. These nodes then function as sources and sinks of supply lines. Nodes are chosen at random to work as a source of supply lines. Then a neighboring node is chosen at random to work as a sink of the supply line. A supply line is emitted from the source node and moves with a constant speed towards the sink node. The rendering of these supply lines was pretty tricky, as the supply lines could be in any of the following phases, each of which needed to be handled differently:
- Generating - line hasn't been generated to it's full length.
- Transmitting - line has completely generated and is moving towards the sink node.
- Sinking - line is falling into the sink node, with it's visible length reducing every frame.
- Destroyed - when line has completely fallen into the sink node, it's to be removed from the memory.

I also added some parameters that control the speed, and the maximum number of lines that are present on screen at any given moment.



### Commits
- https://github.com/vaibhav-sangwan/three-utilities/commit/30d518cae9c558a978c0387809a0a8ea8e5f2fa0
- https://github.com/vaibhav-sangwan/three-utilities/commit/7f65b310de492de643b1f6ac0a12efce26e3eea4
- https://github.com/vaibhav-sangwan/three-utilities/commit/48cee452f76383e179839ad444a8dd6db122f997


## Progress - Fractals

### Gameplay Developments
Fractals are fascinating patterns that look similar at various scales of magnification. If you zoom in on a fractal, no matter how close you get, you still see the same or similar shapes repeating themselves. I initialised and setup a new repository for the Fractals activity. I added a README file for the same consisting of following subsections:
- What is this?
- How to use?
- How to run?

I added the GNU General Public License v3.0 and it's short version in every file. Also, I added a placeholder sugar activity icon (taken from Hello World Activity) and created a sugar package by adding `activity/activity.info`, `setup.py` and `activity.py` files.

The activity.py consists of a build_toolbar() method that is used to add ActivityIcon and Stop buttons to the activity toolbar. Moreover I included sugargame files to the activity as I intended to develop the simulation using pygame. I created `main.py` containing the Fractals class and run() function. This is the entry point of game. This initial setup also consisted of creation of a game state manager.

### Fractal Simulator
For the generation of fractals, I came across the concept of Lindenmayor systems (or L-systems). Originally the L-Systems (short term for Lindenmayer systems) were devised to provide a formal description of the development of simple multi cellular organisms while illustrating the neighborhood relationships between plant cells. Later on, this system was extended to describe higher plants and complex branching structures. The realistic modeling of plant growth is of very high value to biology, physics and also for computer graphics (e.g. video games are using and still working on it to improve plants/forests rendering).

L-Systems consist of formal grammars which includes alphabets, constants, axioms and production rules. These L-Systems can generate sentences in an iterative manner by starting with the axiom and applying the production rules on each iteration. The generated string is very hard to interpret as is. It needs to be parsed and correctly depicted using visual elements to derive a meaningful pattern. These patterns are nothing but the fractals we are looking for.

So, I created a game state for the Fractal simulator which consists of a parameter sidebar(where the users will be able to play around with the parameters controlling how the fractal will look) and the fractal renderer. The sidebar is currently empty. The I implement Lindenmayer systems that produce the statements corresponding to different fractals. I also added the logic to correctly parse and interpret the returned statement and to present it visually on the screen. However, the output was huge and going out of the bounds of screen, so I implemented a function to scale and center it on the fractal renderer.

I added axioms, production rules and default parameters for snowflake, dragon curve, levy curve, serpinski triangle, plant fractal, binary tree fractal variation and peano curve. Moreover, I added events to increment the number of iterations, change the fractal to be rendered and to start/stop the angle incrementation.

### Screenshots
<b>Snowflake</b>
![snowflake](https://github.com/user-attachments/assets/16cef8e7-7544-49c0-a15b-f27fb1402ad1)

<b>Dragon Curve</b>
![dragon curve](https://github.com/user-attachments/assets/b6bec2ff-d143-4625-9443-d10104d9bb27)

<b>Levy Curve</b>
![levy curve](https://github.com/user-attachments/assets/c215ae2f-0074-4cea-9e9e-b185f02bcf7d)

<b>Serpinski Triangle</b>
![serpinski triangle](https://github.com/user-attachments/assets/a250c8fd-4315-4e07-96f7-47ed29c9e103)

<b>Plant Fractal</b>
![plant](https://github.com/user-attachments/assets/87303d07-1708-4fa8-b5e5-e4a3e23cf4c6)

<b>Binary Tree Fractal Variation</b>
![tree](https://github.com/user-attachments/assets/f30bf11a-8806-4d81-9165-1bfb1c6faea9)

### Commits
- https://github.com/vaibhav-sangwan/fractals/commit/88c7bfbeeab8287b9c54e6304786f52523ecf770
- https://github.com/vaibhav-sangwan/fractals/commit/383a14e1a4a1d557a7755c43b2c75f6a7a0cced4
