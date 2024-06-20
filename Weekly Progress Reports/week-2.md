# Week 2 (12 June - 18 June) - Tower Of Hanoi

## Progress 

### Graphical Changes
- Changed the base resolution of game from 800x400 to 640x360.
- Updated the code to position sprites accordingly.
- Added the following sprites to the game:
    - Background (updated)
    - Cursor (updated)
    - Logo
    - Buttons
    - Cloud Variants

![main-menu-background-ss](https://github.com/vaibhav-sangwan/DMP/assets/94783049/c98c2150-5cb0-4aab-8896-46adc5a4422f)
![playing-ss](https://github.com/vaibhav-sangwan/DMP/assets/94783049/701cbc80-fb76-40fc-a0cf-cea8c5f6722f)

### Gameplay Developments

I have added randomly generated moving clouds in the game. This gives the game a smoother feel, also enhancing it's visual appeal. I added 3 cloud variants to the game. Periodically, one cloud variant will be chosen at random out of the available ones, and it will be spawned outside the right bounds of screen. It will move at a slow pace towards left (eventually killed once it goes outside the left bounds of the screen), giving the game a dynamic and windy feel.

I added main menu to the game. The main menu currently consists of two buttons - Play and Help. The Play button is correctly setup with game state manager to transition to game levels. I will be working on making the help instructions page in the upcoming week as well as adding an onclick transition to the help button.

### Game State Manager

A game state refers to a particular phase or screen that the player interacts with. It could be as simple as a main menu, a pause menu, or as complex as in-game levels, cutscenes, and game-over screens. Each state has its own unique set of rules, visuals, and user interactions. By managing these game states effectively, we can control the flow of gameplay and provide players with a seamless and immersive experience.

I created a game state manager for the Tower Of Hanoi activity that can also be used in future activities. This will lead to a more object-oriented development of various game scenes that are going to be included such as Main Menu, Levels (from 1 to 7), Level Select Menu and Help Instructions page.

Furthermore, I also created game states Level 1 to Level 7 and Main Menu. Giving each level it's own game state will facilitate the creation of a level select menu in future, in case the need arises.

### Commits
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/364b17c7c505baeb3304caab67fac8ef1f573e94
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/9f32d9eaf214afcdab4e5152a9d8bc4f0c96a190
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/d1dd459db0b1899e9f253c15e4ef9977670247f2
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/05e12a82db166dc7229735d62527d14897ddd345
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/83d215dcb6a1a317087ad91fe741bf4587819a1d
