# TechClub
Tech Club project references for students<br>
Executables can be found in each project's bin folder<br>
Check ./Source/ for quick access to source code<br>
Program details:
* [Rock Paper Scissors](#rock-paper-scissors)
* [Tic-Tac-Toe](#tic-tac-toe)
* [Pig Latin](#pig-latin)
* [Vector Adder](#vector-adder)

# Rock-Paper-Scissors
### Simple:
Allow a user to play rock-paper-scissors through the command line. The user should have their options listed to them and they should be able to choose an option by index or by name. Choosing by index and choosing by name do not need to be implemented simultaneously. The computer should randomly choose an option, which the user should be told after making their choice. The program should then say whether the user won or lost.
### Scalable:
Follow the same instructions as above, but allow for more objects to be added simply by adding a string to a list or adding items to an enum. Make sure all options are listed to the user and make sure the computer can choose from any of the listed objects.

# Tic-Tac-Toe
### Simple:
Allow two users to play Tic-Tac-Toe through the command line by entering X/Y coordinates. The coordinates should be 1-indexed ("1,2,3...", not "0,1,2...") and the user should only be able to choose coordinates that are on the board and not already filled in. The program should stop when a player gets three in a row or when there are no available spaces on the board.
### Scalable:
Follow the same instructions as above, but allow for the board to be expanded.
For extra challenge, implement the board as an object with the following properties:
* A char for the default symbol that:
  * Can be set when the object is instantiated
  * Can be read after the object is instantiated
  * Can not be changed after the object is instantiated
* A list of a list of characters representing the board (trust me, this is easier than doing a list of strings)
* An int for width/height that:
  * Can be read
  * Can be set, changing the corresponding property
* An int for the number of adjacent spaces to win that:
  * Can be read and set
  * (Optional) Is determined automatically
* A char for player 1's character
* A char for player 2's character
* The ability to index a character on the board in the form board [xPos, yPos]

And the following methods:
* void SetAll(char space)
  * Sets every character on the board to the specified character
* void ResetAll()
  * Resets every character on the board to the default character (Hint: use the SetAll() method you wrote)
* void SetSpace(int x, int y, char c)
  * Sets the character at the specified position to the specified character
* char GetSpace(int x, int y)
  * Gets the space at the specified position
  * Returns the default character if the specified position isn't on the board
* int[] AskSpace()
  * Asks the user to choose a position
  * Returns the chosen position as an int array
* int GameState()
  * Checks if either player has won
  * Returns 0 if neither player won
  * Returns 1 if player 1 won
  * Returns 2 if player 2 won
* string ToString()
  * Returns the board as a string (Hint: \n is the newline character that computers use to drop down a line)

Optionally, add an enum for spaces with three items: "empty," "player1," and "player2." Implement this in the game loop to show the current player and in the object's methods where applicable.

# Pig Latin
Write a method for taking a string and converting its contents to pig latin. The following conditions apply:<br>
1. If the word starts with a vowel, nothing should be moved.
2. If the word starts with a consonant group, the entire first consonant group should be moved to the end of the word.
3. The suffix should always be added to the end of a word.
4. The capitalization of characters in the word should not be changed (including moved characters).<br>

For extra challenge, try allowing the user to run the program with input parameters (e.g.: pigLatin.exe "this is my test string").

# Vector adder
Write a class, "Vector," which has the following properties:
* A horizontal component
* A vertical component
* A resultant
* An angle<br>

These should all be doubles or floats! Using an int will lose lots of precision.<br>
The resultant and angle should be calculated based on the horizontal and vertical components. To do this, create [get-set blocks](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/using-properties) for the resultant and angle properties. Tip: it may be helpful to create a private field for both of these properties.<br>
<br>
The class should have the following methods:
* void SetResultant(double magnitude, bool changeHPart)
  * Sets the resultant to the given magnitude
  * If changeHPart is true, the horizontal component should be changed to make the new parameter work
  * If changeHPart is false, the verctical component should be changed
* void SetAngle(double angle, bool changeHPart)
  * Same as above
* Any other methods that you think may be helpful<br>
<br>
Vectors should be able to be added and subtracted from one another using [operator overloading](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/operator-overloading).
### Equations
The equations needed for this program are here:<br>
Length of hypotenuse: ![sqrt(x^2 + y^2)](https://latex.codecogs.com/gif.latex?\sqrt{x^2&plus;y^2})<br>
Angle: ![arctan(y/x)](https://latex.codecogs.com/gif.latex?\frac{y}{x})<br>
Length of x: ![sqrt(c^2 - y^2)](https://latex.codecogs.com/gif.latex?\sqrt{c^{2}-y^{2}})<br>
Length of y: ![sqrt(c^2 - x^2)](https://latex.codecogs.com/gif.latex?\sqrt{c^{2}-x^{2}})<br>
