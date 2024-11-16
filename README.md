# portfolio
A Collection of Cool Things


It is a game where you can find your bear instincts

# World of Bears Design Document

Designer:
Qurratul Ain Sanjida

## Classes and Data Structures



Classes and Data Structures


Main Class (Main):


Instance Variables:

WORLD_WIDTH: Integer representing the width of the world.
WORLD_HEIGHT: Integer representing the height of the world.
Purpose:

Responsible for starting the program.
Parses command-line inputs.
Manages the creation of MazeEngine and initiates either keyboard or input string mode.
MazeEngine Class:

Instance Variables:

world: Instance of the World class representing the game world.
inputSource: Instance of an InputSource (e.g., StringInputSource or KeyboardInputSource).
Purpose:

Handles user interactions and gameplay.
Interacts with the World to generate, render, and manipulate the game world.
Utilizes the InputSource interface to handle input from either strings or the keyboard.
StringInputSource Class:

Instance Variables:

input: String representing the input.
index: Integer representing the current index of the input string.
Purpose:

Implements the InputSource interface for string input.
Allows retrieving characters sequentially from the input string.
KeyboardInputSource Class:

Purpose:
Implements the InputSource interface for keyboard input using StdDraw.
Allows retrieving characters typed by the user.
World Class:

Instance Variables:

worldState: 2D array of TETile representing the current state of the world.
Purpose:

Represents the game world.
Manages the generation and rendering of the world.
Handles saving and loading of the world state.
AutograderBuddy Class:

Instance Variables:

WORLD_WIDTH, WORLD_HEIGHT: Constants representing the dimensions of the world.
Purpose:

Implements methods for interacting with the world without rendering (for autograding purposes).
Defines methods for saving and loading the world state.
Algorithms

Main Algorithm:

Parses command-line arguments.
Initializes the MazeEngine based on the mode (keyboard or input string).
MazeEngine Algorithm:

Manages the game loop, allowing the user to navigate the world.
Handles input from either the keyboard or an input string.
Calls appropriate methods in the World class to generate, render, and manipulate the world.
StringInputSource Algorithm:

Implements the InputSource interface methods for string input.
Retrieves the next character from the input string.
KeyboardInputSource Algorithm:

Implements the InputSource interface methods for keyboard input using StdDraw.
Waits for and retrieves the next typed character.
World Algorithm:

Generates the initial world based on a seed.
Renders the world and updates its state.
Handles saving and loading of the world state.
AutograderBuddy Algorithm:

Implements methods for interacting with the world without rendering (for autograding purposes).
Defines methods for saving and loading the world state.
Persistence

World Persistence:

The World class uses ObjectOutputStream and ObjectInputStream to serialize and deserialize the world state.
Saves and loads the 2D array of TETile representing the world to/from a file.
AutograderBuddy Persistence:

Utilizes the same file-saving and loading mechanism as the World class for consistency in saving and loading the world state.

Files Created:
README.md for design doc


More detailed description about BSPtree:

BSPTree Class

The BSPTree class is responsible for generating a Binary Space Partition (BSP) Tree that divides a space into leaves, creates rooms within these leaves, and generates hallways to connect the rooms. Let's break down the key components:

Instance Variables:

r: Random seed for generating random values.
root: The root leaf of the BSP Tree.
rooms: List of rooms generated in the tree.
hallways: List of hallways connecting rooms.
Constructor:

Initializes the BSP Tree with the specified width, height, number of leaves, and random seed.
Uses breadth-first search to split leaves and create rooms.
Prints the number of nodes in the BSP tree using the countNodes method.
Calls createHallway to generate hallways.
Leaf Class:

Nested class representing a leaf in the BSP Tree.
Contains information about the position, dimensions, split direction, and the room within the leaf.
The createRoom method randomly generates a room within the leaf with an 80% probability.
split Method:

Determines if a leaf should be split based on its size and existing splits.
Randomly decides the split direction (horizontal or vertical).
Splits the leaf into two child leaves with random sizes, ensuring a minimum size.
countNodes Method:

Recursively counts the number of nodes in the BSP Tree.
printNodeCount Method:

Prints the number of nodes in the BSP Tree.
createRooms Method:

Recursively creates rooms within leaves without children.
createHallway Method:

Recursively generates hallways connecting leaves with the same parent.
Determines the direction of the hallway (horizontal or vertical) based on the parent leaf's split direction.
Creates a hallway as a room connecting the centers of two leaves.
rooms and hallways Methods:

Getter methods to retrieve the generated rooms and hallways.


