# Week 5-6 (3 Jul -  16 July) Number Guessing

## Progress 

### Graphical Changes
- Added filler background to the game to fill up all the blank space.
- Added the following sprites to the game:
    - Background
    - Game Logo
    - Menu Buttons for Classic, Rev Mode and Help Menu
    - Home Button
    - Flip Page Button
    - Help Menu Title

### Gameplay Developments

I had implemented the Rev Mode prior to the commencement of DMP 2024. But the code wasn't very modular and didn't include the concept of game states and game state manager. So I first refactored all the code to make it more modular so that more game states can be added easily. This included creation of game state manager, game state for rev mode moving all the sprites to components.

Over these two weeks, I developed the following game states - 
- Main Menu
- Classic Mode
- Rev Mode
- Help Menu

#### Main Menu

I created a logo and added menu buttons to play classic and rev modes and to open up the help menu. I also added a pop-on-hover effect to these buttons.

![image](https://github.com/user-attachments/assets/973a3935-662c-442e-956c-c8e3c4dd8a0f)

#### Classic Mode

In classic mode, the computer thinks of a target number that you have to guess in minimum guesses possible. You can click on any number to see its distance from the target. The color of the number box signifies how close your guess is to the target number.

<b>Color Scheme</b>
Red - Far away
Yellow - Getting closer
Green - In close proximity

The traditional method to play this game is to guess a number and then computer telling the user whether their guess is correct, too low or too high. However, using colors to represent closeness to the target seemed like a more user friendly and more engaging way to achieve the same result. To achieve this, I implemented a triple color gradient using linear interpolation. If the computer thinks of the number 23, then the number having maximum distance from it, is 99. And it is colored the darkest shade of red. As we move closer to 23, the color of number boxes first changes to shades of yellow, and then finally it changes into shades of green.

![image](https://github.com/user-attachments/assets/b3279d55-ddc0-4f3d-b4de-185c41ddac88)

<b>Particle System</b>
I wanted to add a particle eruption effect to number boxes. This would enhance the visual eaxperience of users. But while trying to add this effect, I faced multiple problems. First of all, there was no such feature provided by pygame. So I implemented a particle system in which multiple sprites would be generated and emitted from a source position. These sprites would emit in random directions at a constant speed and their size would start diminishing as they move away from the source. When their size becomes 0, they are removed from the particle group and collected by Python's Garbage Collector.

These particles, however, moved in a straight line. They were giving an effect similar to shooting stars rather than particle eruptions. To achieve the effect of eruptions, I split their velocities into x and y components using trigonometry. And every frame, an acceleration is added to the y component of velocity. This gave a similar effect to that of objects freely falling under gravity.

<b>Win Animation</b>
When the user correctly guessses the target number, all number boxes would be revealed in a layer-wise manner (from innermost to outermost). And corresponding to each reveal, a particle eruption takes place. Overlal, this creates a really nice and satisfying effect .

#### Rev Mode
In reversed mode, you have to think of a number lying between 0 and 99 (both inclusive). Then the computer will show you a collection of numbers and you need to press on Yes or No depending on whether the number you thought of is present on the screen or not. You will be shown 7 such collections and after providing appropriate answers each time, the number you thought of will be correctly guessed by the computer.

Besides improving the UI, I added instructions to the Rev Mode to enhance user experience. I also added a outline-on-hover effect to Yes, No, Reset and Home buttons.

![image](https://github.com/user-attachments/assets/099d2e35-969a-4cae-91be-0aa46a02845d)

#### Help Menu
During the creation of help menu, I realised that the help content was too much to show together. So, I split the information about rev mode and classic mode in two different pages and created a page flip button that would switch the content on help menu's screen. This approach can be implemented in future games as well where the number of pages exceed 2.

![image](https://github.com/user-attachments/assets/f2f66c2e-5319-4b88-a29f-8c8b9ce0c559)

Additionaly, I fixed 70+ flake8 issues that got introduced during development.

### Commits
- https://github.com/vaibhav-sangwan/number-guessing/commit/ea622f4ff5f402c94b7d0ffbe8d884162781dc59
- https://github.com/vaibhav-sangwan/number-guessing/commit/b10ab24b727de610a7e7372c0e731adc49786401
- https://github.com/vaibhav-sangwan/number-guessing/commit/991b3ea7bb33387a31c2e608113462ceeef00529
- https://github.com/vaibhav-sangwan/number-guessing/commit/07a41db9866dd023844cceafeeff69bf6155932c
- https://github.com/vaibhav-sangwan/number-guessing/commit/acf5955aa0507e1814430b0e788f751a3353735b
- https://github.com/vaibhav-sangwan/number-guessing/commit/95d5d5f350cabb2765b9543674db60078797d602
- https://github.com/vaibhav-sangwan/number-guessing/commit/5f90723bd4342b38b5fd615ed621b222f19d1a06
- https://github.com/vaibhav-sangwan/number-guessing/commit/388fac8f7dbfc3f6112fd635995bb520192e0e15
- https://github.com/vaibhav-sangwan/number-guessing/commit/fcc494e615f155d1953ee9d78ae10cfd4d70fcaf
