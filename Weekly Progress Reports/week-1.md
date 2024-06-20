# Week 1 (01 June - 07 June) - Setting Up

## About my project - Development of Mathematical Puzzle Games for Sugar
This project initially aimed to develop interactive math games for the Sugar desktop environment. The project covered the creation of Game Of Logic, Pascal's Triangle, Nim, Candy Game, Number Guessing, Latin Squares, Three Utilities, River Crossing, Tower Of Hanoi and Mystic Square. Creation of these activities consists of art generation, UI design, logic implementation, testing and bug fixing. These activities would play a crucial role in enhancing logical thinking skills of children. These games will help equip educators and parents with engaging tools to spark a lifelong love of math in young learners.

### Discussion on 31st May, 2024
Attendees - Chihurumnaya Ibiam, Devin Ulibarri, Spandan Barve, Vaibhav Sangwan, Walter Bender

There was an overlap in activities that I and Spandan have mentioned in our proposals. 
Following activities were mentioned in my proposal for DMP:  
1. Game Of Logic
2. Pascal's Triangle
3. Nim
4. Candy Game
5. Number Guessing
6. Latin Squares
7. Three Utilities
8. River Crossing
9. Tower Of Hanoi
10. Mystic Square

Following activities were mentioned in Spandan's proposal for GSoC:
1. Nim Game
2. Candy Game
3. Illusion Boxx
4. Three Utilities
5. Pascal Triangle
6. Number Guesser
7. Lewis Carrol's Logic Game
8. Latin Squares

GSoC wanted Walter to specify a bit more on the Maths Games project, hence he mentioned certain activities in the [idea list for GSoC](https://github.com/sugarlabs/GSoC/blob/master/Ideas-2024.md#math-games) and [issue ticket for DMP](https://github.com/sugarlabs/DMP/issues/6). It was natural for applicants to build their proposal around the same. However, It's important to coordinate on a weekly basis to make sure Me and Spandan aren't working on the same games.

### How has the project aim changed?
The activities that I'll be working upon might differ from those mentioned in my proposal in the upcoming weeks.


## Progress 
### Scaling and responsiveness - Absolute vs Stretch to fill vs Keep aspect ratio

I will be creating pixel art assets for all my games. However, it's complicated to make the sprites responsive to all screen resolutions and still keep the look and feel of the game that it serves on base resolution. This problem would be faced in every activity that I'll try to develop and hence it was important to find a way to achieve sprite scaling. Keeping the resolution of activities absolute would lead to a very bad experience on larger screen sizes. The playable area would be little compared to what is available. Thus, I discarded absolute approach.

#### Stretch To Fill
To decide among stretch to fill and keeping aspect ratio constant, I experimented with the Tower Of Hanoi activity. I set the mode of pygame display to RESIZABLE and implemented stretch to fill screen sizing. To achieve this for Tower Of Hanoi was pretty easy as it doesn't have any mouse events. All I had to was to blit every sprite on an intermediate surface before transforming and blitting the intermediate surface on the display surface. This approach is relatively easy to implement but it can't be implemented in activities that would require mouse events. To handle mouse events in this approach, I'll have to make a function that transforms the location of mouse events (occuring on pygame display) to what it would have been on the intermediate surface. Also it might introduce some laggyness. Also, this heavily distorts the pixels as scaling in X and Y axes is different leading to poor readability of UI.

![Screenshot from 2024-06-04 14-02-54](https://github.com/vaibhav-sangwan/DMP/assets/94783049/887af086-233b-481d-bc5d-05d4af6712f2)
![Screenshot from 2024-06-04 14-01-13](https://github.com/vaibhav-sangwan/DMP/assets/94783049/977e2700-dcbd-4d0b-a112-5734859d5ef3)


#### Keep Aspect Ratio
I implemented the keeping ratio method. I had to figure out some maths for this. It might be possible that on certain screens, the available scaling in horizontal and vertical dimensions is different. To keep the aspect ratio constant but still scale up to fill either the width, or the height of the screen, I calculated the available scaling factor in X and Y axes. And I scaled the intermediate surface by the minimum of these two values.Then I had to center the intermediate surface. This resulted in black bars being present in top-bottom or left-right based on what resolution I'm working with. The result was looking pretty good. However, the problem with mouse events is present in this method as well.


![Screenshot from 2024-06-04 14-06-41](https://github.com/vaibhav-sangwan/DMP/assets/94783049/11823a1d-4a13-49c1-96cb-d4412cf3b012)
![Screenshot from 2024-06-04 13-58-19](https://github.com/vaibhav-sangwan/DMP/assets/94783049/ea21974f-d0cc-4fcb-ac2a-5fc2083dfecf)

Instead of scaling the intermediate surface by minimum of scaling factors, we can scale it by the maximum of scaling factors as well. This fills up the entire screen leaving no black bars, but it crops out certain parts of the game.

### Design choices
I had to choose from 4:3, 16:9 and 16:10 aspect ratios. Most of the laptop and computers come equipped with with widescreen nowadays, and hence I decided to go along with 16:9. For the base resolution, I decided upon 640x360, as it abided by the aspect ratio constraints and because most of the screens in use today can work with it. Moreover, I've worked with 640x360 resolution games in the past. As for tile size, 32x32 seemed like a rational choice. It didn't limit me as much as 16x16 did and also allowed me to put 20 tiles horizontally - leading to a good enough space to work with.
- Aspect Ratio - 16:9
- Base Resolution - 640x360
- Tile Size - 32x32
