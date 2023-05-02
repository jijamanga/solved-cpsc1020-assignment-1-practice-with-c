Download Link: https://assignmentchef.com/product/solved-cpsc1020-assignment-1-practice-with-c
<br>
For this assignment you are going to write a simple word game. Your program will read and store a set of data, produce a 2D matrix of characters, print instructions for the player on how to play, and determine the amount of time it took the player to find a set of words.

You will be required to write several functions for this project. I realize this seems like a lot, and you would be correct. However, you should get in the habit of writing functions that do very specific task, rather than large functions that do multiple task. Developing functions that do small specific task not only make your code clean and readable, your functions will likely be more reusable than large multitask functions.

I will put an explanation of each of these functions in the functions.h file.

void readData(FILE*, matrixInfo_t*); void printDirections(matrixInfo_t*); void printMatrix(matrixInfo_t*); int readUserInput(matrixInfo_t*); int checkWords(char*, matrixInfo_t*); void allocateLetters(matrixInfo_t*); void allocateWords(matrixInfo_t*); void readLetters(FILE*, matrixInfo_t*); void readWords(FILE*, matrixInfo_t*); void checkArguments(int); void free1DMemory(matrixInfo_t*); void free2DMemory(matrixInfo_t*);

Below is a sample data file with an explanation next to the data. You can use this data to test your program. I will test your program with this data, as well as several other test cases.

<table width="262">

 <tbody>

  <tr>

   <td width="262">These are the words I found in the gameboard. This does not mean these are the only words, they are the choices I have included in the answer.</td>

  </tr>

 </tbody>

</table>

This means the gameboard will be a 3 X 3

These are letter that will occupy the gameboard

This number represents the # of possible words found on the board.

<ol>

 <li>You must provide the following files:

  <ol>

   <li>c</li>

   <li>c</li>

   <li>makefile – your make file must provide following

    <ol>

     <li>make run</li>

     <li>make clean</li>

     <li>Readme – later in this document</li>

    </ol></li>

  </ol></li>

</ol>

I will provide the functions.h file with an explanation of each function.

<ol start="2">

 <li>Currently the struct in the .h file does not use typedef. You will need to change this to use typedef to allow the use <strong>matrixInfo_t</strong> when declaring a variable of the the struct</li>

 <li>You will, of course, need to use command line arguments that consist of two things: a. an executable</li>

 <li>the name of the data file.</li>

</ol>

<h1>DUE: OCTOBER 9, 2019, midnight</h1>

Below is a screenshot of the game after the data has been read in and the appropriate functions called to start the game.:

The player will type a word then enter. Your game will check if the word is in the list of words provided. The game board should be displayed after each iteration of a word being entered. This will ensure the user can see the matrix at all times. The game will maintain a count of the number of correct and unique words the player found. When the player believe she has found all words, she will enter “quit”. The game will display a message showing the number of correct and unique words found. “Full disclosure, when running my version of the game I realized I did not check if I guessed the same word twice. You are required to perform this check.”

Your matrix <strong>must</strong> look like the matrix above. You <strong>must</strong> use a series of “–” as well “+” and “|” to create the boxed outline of the gameboard. At a minimal, your message must be the same as pictured above. You may be creative with your message; however, you must have at least the above.

Points will be deducted for not following direction.

<ol start="4">

 <li>You must dynamically allocate the memory for the characters that go in the game. This must be a 2D matrix.</li>

 <li>You will also provide a timer to determine the amount of time it took the user to find as many words as possible. This will require you to look up the time_t data type and time() function.  You will need to read the time just prior to calling the readUserInput function and read the time after this function has returned.  This should give you appropriate information to calculate the number of seconds it took for the player to find the words. The number should be displayed in minutes and seconds.  If it took the player 80 seconds to find the words, at a minimal display the following:</li>

</ol>

<strong>The amount of time for you to find 12 words was 1 min – 20 sec.</strong>

<ol start="6">

 <li>Although the example given uses a 3X3 matrix you are to write your code such that any size matrix could be read from an input file. Ex. I could provide an input file that uses a 5X8. Your</li>

</ol>

program should be able to handle any size of matrix and any number of words.  All input files will follow the same format as the format given above.

<ol start="7">

 <li>Remember for each allocation of memory there must be a call to free. There are two functions that you will need to complete that should be called to free memory.

  <ol>

   <li>void free1DMemory(matrixInfo_t*);</li>

   <li>void free2DMemory(matrixInfo_t*);</li>

  </ol></li>

 <li>Your main should have a minimal amount of code it it. It should:

  <ol>

   <li>call checkArguments</li>

   <li>create and open a file pointer, which will be used to read the data file</li>

   <li>create any needed local variable to pass to functions</li>

   <li>call the function necessary to start the process of reading the data</li>

   <li>call the function to print the matrix</li>

   <li>call the function to print the directions for the game</li>

   <li>get the start time</li>

   <li>call the function to start reading the user input (read until the user enters quit) i. get the end time</li>

   <li>print the user time and number of words found. (See example output above.)</li>

  </ol></li>

</ol>

<strong>Extra Credit Option 1 </strong>

For each of the following 2 Extra Credit opportunities, the basic game requirements will stay the same. You may choose one of the 2 EC to complete.

After displaying the final time and # of words found.  Add some type of loop that ask the user if they want to pay again with the same set of data to try to beat their original time. After each game, continue to ask until the player says no.  You will need to keep track of their time and number of words found.  Determine the best game by determining the largest number of words found in the shortest amount of time. Display a message with this information to the player.

<strong>Extra Credit Option 2</strong>

In <strong>addition</strong> to giving the above EC option to the user, give the player a <strong>second</strong> option of playing again with a different set of data of the same size.  After each game continue to ask until the player says no, keeping track of the time and number of words found.  Display the best game by determining the largest number of words found in the shortest amount of time.  Display the message with this information to the player.