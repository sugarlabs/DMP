# Week 3-4 (19 June -  2 July) Tower Of Hanoi

## Progress 

### Graphical Changes
- Added filler background to the game to fill up all the blank space.
- Added the following sprites to the game:
    - Background (updated to work with filler background)
    - Back Button
    - Pause Button
    - Help Scroll

### Gameplay Developments

I added move counter to be displayed in the levels. This helps the user keep track of how many disk move operations they have performed.

During these two weeks, I created the game states for Help Menu, Level Select Menu and Pause Menu.

For help menu, I created a scroll sprite that could be used as a background and then implemented a utility function that could render multiple lines of text on a given surface. This is not provided by pygame and I figured that this will be used in other games as well. The function doesn't return a new surface but blits the text on provided surface. The multiple line renderer function also leaves off a right-margin provided as a parameter in the call.

![image](https://github.com/user-attachments/assets/a672e33c-2d30-4f1e-8ed5-5b06d0c95cfc)

For Level Select Menu, I created a new game state that consists of buttons for all levels. These buttons have a highlight-on-hover effect attached to them. And the user can play any level right off the bat. The level number denotes how many disks would need to be moved from source rod to destination nodes. I also added back button to help menu and level select menu.

![image](https://github.com/user-attachments/assets/506e2a47-e625-41b0-afcd-966d9932c140)

The pause menu was created to ease the user if they want to restart the current level or go back to home screen. 

![image](https://github.com/user-attachments/assets/99e60313-9d56-472d-8c81-1d3e8da71b35)

Moreover, I added a fade-in and fade-out effect to clouds using interpolation so that they can work correctly with filler backgrounds. It gives a really nice feel to the game and moves it away from being static.

Over these two weeks, I also fixed various bugs and issues that were faced during testing. Some of the issues that were faced and fixed were -
1) When `main.py` is executed directly, pygame window size comes out larger than monitor screen size.
2) The methods implemented in `utils.py` were static but the staticmethod decorator wasn't used.
3) There were 100+ flake8 issues that needed to be fixed.

### Commits
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/83d215dcb6a1a317087ad91fe741bf4587819a1d
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/707942fbe41b7ee3faad9b6747926a4358616dca
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/5fa0b4e3da0bcb1a48717ee4706a692cf820a04f
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/42395e8c711c3b5734713f6ffbe40409b43e5537
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/f806c40031c392ddc32af3e9a84165885e1637f7
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/d206e507f926a14efdee4547493dea231cb849d2
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/e6c1fdf28d86b701974d199a10487a7a951472c8
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/b5a8205660daf9f6c9f11bd1118f983deadf6dae
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/691fe3ddaa00b22ab8c18da5d895631aa73e821a
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/f2b876d0cab8d789ffdce9be18de1a73daaeb53e
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/d9046576222834e8a340d1e4b589c4381c1f368a
- https://github.com/vaibhav-sangwan/tower-of-hanoi/commit/1a4a7620511fefb1219bc5a1ce1a94af9daf915d
