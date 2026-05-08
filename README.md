# Intro-to-Programming-Cpp-Projects

This repository contains a semester-long collection of C++ programming projects completed for an introductory programming course. The projects show my progression from basic console-based programs to larger object-oriented applications involving games, encryption algorithms, file input, simulation logic, and simple AI decision-making.

The purpose of this repository is to document the programming concepts I learned throughout the semester and demonstrate how I applied them through projects of increasing complexity.

---

## Repository Overview

| Project | Topic | Main Focus |
|---|---|---|
| Project 1 | Focaccia Calculator | Basic C++ syntax, arithmetic, input/output |
| Project 2 | Rock-Paper-Scissors | Functions, conditionals, loops, user input validation |
| Project 3 | Classical Ciphers | String processing, modular programming, encryption/decryption |
| Project 4 | Battleship Game | Object-oriented programming, file input, game logic |
| Final Project | Elevator Simulation | Multi-class simulation, AI decision-making, system design |

---

## Technologies Used

- C++
- Standard C++ libraries
- Console-based user interaction
- Text file input/output
- Header and source file organization
- Object-oriented programming
- Xcode project files

---

# Project 1: Focaccia Ingredient and Cost Calculator

## Introduction

Project 1 is a console-based C++ program that calculates the ingredients needed to make focaccia bread for a given number of people. The user enters the number of people to serve, and the program calculates the required number of loaves, bags of flour, packages of yeast, canisters of salt, bottles of olive oil, and total estimated cost.

This project introduced the basic structure of a C++ program and focused on turning a real-world calculation problem into a working program.

## Method

The program follows a simple calculation workflow:

1. Ask the user how many people need to be served.
2. Calculate the number of focaccia loaves required.
3. Calculate the amount of each ingredient based on the number of loaves.
4. Use rounding logic so the shopping list uses whole packages.
5. Calculate the total expected cost.
6. Print a formatted shopping list.

The project also uses a helper function to handle singular and plural words in the output, such as `1 bag` versus `2 bags`.

## Result

The final program produces a complete shopping list and estimated ingredient cost based on user input. It demonstrates how programming can be used to automate a practical calculation task.

Example output:

```text
How many people do you need to serve? 10

You need to make: 3 loaves of focaccia

Shopping List for Focaccia Bread
--------------------------------
1 bag of flour
3 packages of yeast
1 canister of salt
1 bottle of olive oil

Total expected cost of ingredients: $10.77

Have a great party!
```

## Key Concepts

- Basic C++ syntax
- Variables and constants
- Arithmetic operations
- Console input/output
- Rounding calculations
- Helper functions
- Output formatting

---

# Project 2: Rock-Paper-Scissors Game

## Introduction

Project 2 is a two-player Rock-Paper-Scissors game written in C++. The program asks both players for their names, displays a menu, accepts player moves, validates input, determines the winner of each round, and announces the overall winner after multiple rounds.

This project focused on breaking a program into smaller functions and using conditional logic to manage game rules.

## Method

The program is divided into several functions, with each function handling a specific responsibility:

- Get player names.
- Display the game menu.
- Validate menu choices.
- Ask each player for a move.
- Check whether each move is valid.
- Compare two moves to determine the round winner.
- Track scores across rounds.
- Announce the final winner.

The game uses standard Rock-Paper-Scissors rules:

- Rock beats scissors.
- Scissors beats paper.
- Paper beats rock.
- Matching moves result in a draw.

The project also includes a menu option for Rock-Paper-Scissors-Lizard-Spock, but that mode is left as an under-construction feature.

## Result

The final program runs a complete text-based Rock-Paper-Scissors game through the terminal. It handles invalid input, tracks player performance, and prints the final result after the game ends.

Example output:

```text
----------------------------------------
             EECS 183
       Rock-Paper-Scissors
----------------------------------------

Player 1, enter your name: Alice
Player 2, enter your name: Bob

Menu Options
------------
1) Play rock, paper, scissors
2) Play rock, paper, scissors, lizard, spock
3) Quit

Choice --> 1

Alice, enter your move: R
Bob, enter your move: S

Alice wins the round!
```

## Key Concepts

- Functions
- Parameters and return values
- Loops
- Conditional statements
- Input validation
- Character handling
- Game logic
- Score tracking

---

# Project 3: Classical Cipher Program

## Introduction

Project 3 is an encryption and decryption program that supports multiple classical ciphers, including Caesar cipher, Vigenere cipher, and Polybius square cipher. The user chooses a cipher type, selects encryption or decryption mode, enters a message, provides a key, and receives the converted result.

This project introduced more advanced string processing and modular programming. Each cipher is separated into its own source and header files, making the program easier to organize, test, and maintain.

## Method

The program supports three cipher methods.

### Caesar Cipher

The Caesar cipher shifts alphabetic characters by a fixed integer key.

Method:

1. Read the original message.
2. Read an integer key.
3. Shift each alphabetic character forward for encryption or backward for decryption.
4. Preserve non-alphabetic characters.
5. Return the converted message.

### Vigenere Cipher

The Vigenere cipher uses a keyword instead of a single numeric shift. Each letter in the keyword determines a different shift value.

Method:

1. Read the message.
2. Read the keyword.
3. Convert keyword letters into shift values.
4. Repeat the keyword across the message.
5. Apply different shifts to alphabetic characters.
6. Preserve spacing and non-letter characters where appropriate.

### Polybius Square Cipher

The Polybius cipher uses a grid-based substitution method. A keyword is used to generate a mixed character grid, and characters are converted into coordinate pairs.

Method:

1. Read the message.
2. Validate allowed characters.
3. Read the keyword.
4. Convert the keyword to uppercase.
5. Remove duplicate characters from the keyword.
6. Build a mixed Polybius grid.
7. Convert characters to coordinate pairs for encryption.
8. Convert coordinate pairs back to characters for decryption.

## Result

The final program works as an interactive command-line encryption and decryption tool. It allows the user to select the cipher method and transformation mode, then outputs the encrypted or decrypted message.

Example output:

```text
Choose a cipher: Caesar
Encrypt or decrypt: Encrypt
Enter a message: Hello World
What is your key: 3

The encrypted message is: Khoor Zruog
```

## Key Concepts

- String manipulation
- Character processing
- Modular programming
- Header files and source files
- User input validation
- Encryption and decryption logic
- 2D arrays
- Function testing

---

# Project 4: Battleship Game

## Introduction

Project 4 is a console-based Battleship game implemented using object-oriented programming. The user plays against a CPU opponent. The game supports loading ship grids from text files or generating grids randomly, and the user can select different CPU behavior modes.

This project was a major step from function-based programming to class-based program design. It required multiple interacting classes to represent positions, ships, players, and the overall game.

## Method

The project is organized around several major classes.

### Position Class

The `Position` class represents a coordinate on the Battleship grid. It stores row and column information and supports coordinate-based operations.

### Ship Class

The `Ship` class represents an individual ship. It stores the ship’s placement, orientation, and hit status. It helps determine whether a ship has been hit or sunk.

### Player Class

The `Player` class stores a player’s grid, ships, guesses, and game-related actions. It manages board state and player attacks.

### Game Class

The `Game` class controls the overall game flow. It manages both the human player and CPU player, processes turns, checks hits and misses, and determines when the game ends.

The game setup process includes:

1. Ask the user for their name.
2. Create a human player and CPU player.
3. Ask whether to load grids from text files.
4. Create the game board.
5. Select CPU mode.
6. Start the game loop.
7. Continue until one side wins.

## Result

The final program runs a complete Battleship game in the terminal. It demonstrates object-oriented design through multiple classes working together to represent a larger game system.

Example output:

```text
Enter your name: Zehuan

Read your grid from file grid1.txt? (y or n): y
Read CPU grid from file grid2.txt? (y or n): n

Starting game with EASY AI
```

## Key Concepts

- Object-oriented programming
- Classes and objects
- Constructors
- Encapsulation
- Header/source file separation
- File input
- Grid-based logic
- Game state management
- Player vs. CPU interaction
- Testing and debugging

---

# Final Project: Elevator Simulation

## Introduction

The final project is a building elevator simulation written in C++. The program models a building with multiple floors, elevators, and people waiting for service. The goal is to control elevator movement and pickups in a way that improves the satisfaction index and reduces passenger anger.

This was the most complex project in the course. It combined object-oriented programming, simulation logic, file-based scenarios, and AI decision-making.

## Method

The simulation is built using multiple classes that represent the main components of the system.

### Building

The `Building` class represents the full simulation environment. It manages the state of floors, elevators, people, and the progression of the game.

### Elevator

The `Elevator` class represents an individual elevator. It stores information such as the current floor, target floor, and whether the elevator is currently servicing a request.

### Floor

The `Floor` class represents one floor in the building. It stores the people waiting on that floor and provides methods to access or update floor-level information.

### Person

The `Person` class represents an individual passenger. Each person has a current floor, target floor, and anger level. The anger level is important because it affects the satisfaction score.

### Move

The `Move` class represents an action taken by the player or AI. A move may send an elevator to a floor or pick up a group of people.

### SatisfactionIndex

The `SatisfactionIndex` class tracks the performance of the elevator system. Better decisions improve the score, while poor service decisions can increase passenger anger and reduce satisfaction.

## AI Strategy

The final project includes AI decision logic to choose elevator actions based on the current building state.

The strategy follows these ideas:

1. Check whether an elevator is idle.
2. If an idle elevator is already on a floor with waiting people, pick them up.
3. Otherwise, search for the floor with the highest total anger level.
4. Avoid sending multiple elevators to the same target floor.
5. Select the available elevator closest to the selected floor.
6. During pickup, compare upward-going and downward-going passengers.
7. Pick the group with higher total anger first.

This strategy focuses on reducing the highest-risk waiting groups and improving the satisfaction index.

## Result

The final project produced a working elevator simulation with an AI strategy for choosing elevator movements and passenger pickup groups. The AI prioritizes floors with higher total anger and selects nearby available elevators, which helps reduce passenger frustration and improve the simulation score.

The project also includes multiple input scenario files, allowing the simulation to be tested under different passenger patterns and difficulty levels.

## Key Concepts

- Large-scale object-oriented programming
- Multi-class system design
- Simulation modeling
- File input scenarios
- State-based programming
- Basic AI decision-making
- Performance evaluation
- Debugging a larger codebase
- Separating interface and implementation

---

## How to Run

Clone the repository:

```bash
git clone https://github.com/zehuanyu/EECS183Projects.git
cd EECS183Projects
```

### Run Project 1

```bash
cd project-1
g++ focaccia.cpp -o focaccia
./focaccia
```

### Run Project 2

```bash
cd "project 2/project 2"
g++ rps.cpp start.cpp -o rps
./rps
```

### Run Project 3

```bash
cd project3
g++ *.cpp -o ciphers
./ciphers
```

### Run Project 4

```bash
cd project4
g++ *.cpp -o battleship
./battleship
```

### Run Final Project

```bash
cd "final project"
g++ *.cpp -o elevator_simulation
./elevator_simulation
```

Note: Some folders may include starter files, test files, or course-provided files. If a compile command causes a duplicate `main()` error, compile only the main driver file and the required implementation files.

---

## Skills Demonstrated

Through these projects, I practiced and developed:

- C++ programming fundamentals
- Console-based program design
- User input and output handling
- Arithmetic and formatted output
- Functions and decomposition
- Loops and conditionals
- String and character processing
- File input and output
- Header/source file organization
- Object-oriented programming
- Class-based design
- Game logic
- Simulation logic
- Basic AI decision-making
- Testing and debugging

---

## Learning Reflection

These projects show my progression through one semester of introductory C++ programming. I started with a simple calculator-style program and gradually moved into more complex applications involving games, encryption tools, object-oriented design, and simulation.

The biggest improvement across the semester was learning how to break a large problem into smaller components. In the earlier projects, most logic was handled through functions. In the later projects, the code became more structured through classes such as `Player`, `Ship`, `Game`, `Elevator`, `Floor`, and `Person`.

By the final project, I was able to work with a larger codebase, understand interactions between multiple classes, and implement simple AI logic based on the current state of the simulation.

---

## Recommended Repository Name

Recommended repository name:

```text
Intro-to-Programming-Cpp-Projects
```

This name is clear and professional because it explains the project content directly, even for people who are not familiar with the course number.

---

## Author

Zehuan Yu
