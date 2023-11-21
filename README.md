# terminal-minecraft

**Overview**

This is a simple terminal-based Minecraft-like application written in C using the X11 library for keyboard input handling. The program allows the user to navigate a 3D environment, place and remove blocks, and view the scene from a first-person perspective.

**Dependencies**

Standard C libraries: stdio.h, stdlib.h, math.h

X11 library: Xlib.h

X11 Keysym library: X11/keysym.h

**Compilation**
Ensure that the X11 development libraries are installed on your system. Compile the program using a command like:

```gcc minecraft_terminal.c -o minecraft_terminal -lX11 -lm```

**Usage**
Run the compiled executable in the terminal:

```./minecraft_terminal```

**Controls** 

- W: Tilt the view up

- S: Tilt the view down

- A: Tilt the view left

- D: Tilt the view right

- Up Arrow: Move forward

- Down Arrow: Move backward

- Left Arrow: Strafe left

- Right Arrow: Strafe right

- Space: Place or remove a block

- Shift + Space: Remove a block without placing one

**Code Structure** 

**Constants** 

- X_PIXELS, Y_PIXELS: Screen dimensions

- VIEW_WIDTH, VIEW_HEIGHT: Field of view angles

- BLOCKS_X, BLOCKS_Y, BLOCKS_Z: Dimensions of the 3D environment

- EYE_HEIGHT: Height of the player's viewpoint

- BLOCK_BORDER_SIZE: Size of the block border

- BLOCK_INFILL_CHAR: Character representing the block infill

- BLOCK_BORDER_CHAR: Character representing the block border

**Data Structures**

- Vector: Structure representing a 3D vector

- Vector2: Structure representing two angles (psi and phi)

- Vector_Vector2: Structure combining a position vector and view angles

- player_pos_view: Structure representing the player's position and view angles

**Functions**
- key_is_pressed: Checks if a specified key is pressed

- vect_add, vect_scale, vect_normalize, vect_sub: Vector operations

- vect_print: Prints a vector

- init_posview: Initializes the player's position and view angles

- init_picture, init_blocks: Initializes the picture buffer and 3D blocks array

- angles_to_vect: Converts angles to a 3D vector

- init_directions: Initializes the ray directions for rendering

- ray_outside: Checks if a ray is outside the environment

- min: Returns the minimum of two numbers

- on_block_border: Checks if a position is on the border of a block

- raytrace: Performs ray tracing to determine the visible blocks

- get_picture: Generates the picture buffer based on ray tracing

- draw_ascii: Outputs the ASCII representation of the picture buffer

- update_posview: Updates the player's position and view angles based on user input

- get_current_block: Determines the current block the player is looking at

- place_block: Places a block in the environment

**Main Function**

- Initializes the picture buffer, blocks array, and player's position

- Enters a main loop for user input, rendering, and block manipulation

- Allows the user to navigate, place, and remove blocks in the environment
