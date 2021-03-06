Drawing Program
-------------------
A program that lets you create a canvas, draw various shapes(line, rectangle) inside it, and also allows you to fill certain area with a color(character) just like the paint application, but all this on a simple console(Command Prompt/Terminal).

This program is written using JavaScript in node.js environment and uses Mocha and chai as test frameworks.

Prerequisite
-------------
1) Node JS (version 6.0.0 or later)
2) Node Package Manager [npm] (version 4.0.0 or later)

How to run the program
--------------------------
1) Open Command Prompt [windows] (or) Terminal [mac].
2) Change directory inside the console to the downloaded project folder where app.js is located.
3) Execute command "node app.js"
4) The program will request you to "enter command: "
	Note: Currently following commands are supported:
		Create-canvas: 'C w h', 
		Draw-line: 'L x1 y1 x2 y2', 
		Draw-rectangle: 'R x1 y1 x2 y2', 
		Bucket-fill: 'B x y c', 
		Quit: 'Q'
5) Please input commands one after the other as per your preference and the program will draw the canvas as an output inside the console.
	Note: On any error or exception the program will guide you with an appropriate message.
6) Enter 'Q' as a command to exit the program.

How to test the program
--------------------------
1) Check in the console if you are in the directory location of project's app.js file (or) follow steps 1 & 2 of "How to run the program" section.
2) Execute command "npm test".
3) Total 36 test cases will be executed and the results will appear inside the same console.
	Note: I have designed these test cases while considering every possible scenario as per my understanding.

Assumptions
--------------
1) The height and width of canvas are restricted to max 75, as above this number the canvas usually appears distorted inside a console.
2) If the starting points of any command (line, rectangle or bucket-fill) are out of the canvas, then it is considered as an out of bound error.
3) If the ending points of any command (line or rectangle) are out of the canvas, then they are wrapped inside the canvas.
4) If the bucket-fill command is executed on already existing (line, rectangle or point) then the color of the point/edge(s) are changed to the bucket-fill character.
	Note: Points 2, 3 and 4 are assumed as the GUI paint tool on windows also behaves nearly in the same manner.

Architecture & File Descriptions
--------------------------------
- Main app.js handles receiving of input and printing the output.
- data_handler object & canvas object are closers written in such a way that they expose only public methods and hide private instance variables along with  private methods.
- This program is architected in such a way that only one function (/*data_handler.process_data(<command>)*/ ) handles output of the complete program. This is done to make testing easier(please observe that all the test cases are written to test this function). 





