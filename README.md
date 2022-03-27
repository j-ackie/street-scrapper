# Street Scrapper

![Demo](https://i.imgur.com/RXx4cDG.gif)

## About the Project
Developed in a week and a half with [Julio Villanueva](https://github.com/julio-villa) for a final class project, Street Scrapper is a copy of the famous Street Fighter game. It's written in C++ and uses the GE211 game engine. Players are meant to play while sitting next to each other, using the same keyboard.

Street Scrapper is not an exact copy, but it does retain the fundamental mechanics of Street Fighter, such as different game states, character and map selection, player movement and attacks, and animations.

Street Scrapper has 10 functional requirements as specified in the following [documentation](https://docs.google.com/document/d/1Y6FMmDDyXs5nOaggsxvhPSJl1z6PhruivHR6oaYs59E).

## Playing the Game
### Start Screen and Character Select Screen

![Start and character select](https://i.imgur.com/ECKHnU9.gif)

Immediately upon entering the game, the start screen is displayed. When any key or mouse button is pressed, the game progresses to the character select screen.

Players use the following set of controls in the character select screen:

| Player 1 |  Player 2   |        Action       |
| :------: | :---------: | :-----------------: |
|    A     | Left arrow  |   Move cursor left  |
|    D     | Right arrow |   Move cursor right |
|    X     |      J      |   Select character  |
|    C     |      K      |  Unselect character |
|    Y     |      Y      |      Continue       |

### Map Select Screen

![Map select](https://i.imgur.com/74g40Xk.gif)

In the map select screen, 4 maps are displayed. Each player can choose one. If both players choose the same map, then that map will be played. However, if both players choose differing maps, then a map is randomly seleccted between the two maps that the two players chose.

Players use the following set of controls in the map select screen:

| Player 1 |  Player 2   |        Action       |
| :------: | :---------: | :-----------------: |
|    A     | Left arrow  |   Move cursor left  |
|    D     | Right arrow |   Move cursor right |
|    X     |      J      |      Select map     |
|    C     |      K      |     Unselect map    |
|    Y     |      Y      |      Continue       |

### The Match

![Demo](https://i.imgur.com/RXx4cDG.gif)

In the match state, players deal damage, decreasing the health bar of the opposing player. Each player starts with 100 health, and a winner and loser are decided when a player's health bar reaches 0 or when the timer reaches 0. If both players have the same amount of health when the timer runs out, a draw is declared.

Players use the following set of controls during the match:

| Player 1 |   Player 2   |    Action    |
| :------: | :----------: | :----------: |
|    W     |  Up arrow    |  Jump        |
|    A     |  Left arrow  |  Move left   | 
|    S     |  Down arrow  |  Crouch      |
|    D     |  Right arrow |  Move right  |
|    X     |      J       |  Punch       |
|    C     |      K       |  Kick        |
|    V     |      L       |  Projectile  |
|  Shift   |    Space     |  Block       |

### After-Match Screen

The winner and loser, or neither if there is a draw, is displayed in the after-match screen.

![After match](https://i.imgur.com/Vi8FRzI.png)

Player 1 can use the X key and player 2 can use the J key to return back to the character select screen.

## Installation and Running
1. Clone the repo
```
git clone https://github.com/j-ackie/street-scrapper.git
```
2. Open the directory where the repository was cloned to.
3. Run the executable `cmake-build-debug/game`.

## Unit Tests
Unit tests for player movement, player damage, projectile collisions, and game state progression can be found in `test/model_test.cxx`.

- **Test #1:** Game progresses correctly from the start screen to the after-match screen.
- **Test #2:** Two opposing players' projectiles are destroyed when they collide. A player's projectile gets destroyed when it goes off screen.
- **Test #3:** A player moves the correct amount of distance when they walk or jump a certain direction.
- **Test #4:** The correct winner is decided (player 1) when the timer runs out and player 1 has more health.
- **Test #5:** The correct damage is dealt when a player attacks the opposing player.

## References
- Downloaded sprites for characters and projectiles from [The Spriter's Resource](https://www.spriters-resource.com/snes/supersf2/).
- Cut sprites from sprite sheets and replaced colors with transparency with [ezGIF](https://ezgif.com/sprite-cutter).
