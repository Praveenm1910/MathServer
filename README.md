Multithreaded Math Server
This project is a simple multithreaded math server built using Python's socket programming and subprocess module. It allows multiple clients to connect simultaneously and evaluate mathematical expressions. The server processes these expressions by communicating with the Unix bc (basic calculator) utility, providing users with a quick way to calculate mathematical queries.

Note: This server currently works only on Linux-based systems due to its reliance on the bc command-line tool, which is native to Unix-like environments.

Features
Multithreaded Communication: Each client connects to the server on a new thread, allowing simultaneous connections.
Math Expression Evaluation: Clients can send math expressions to the server, which will evaluate them using bc.
Interactive Interface: The server provides a basic interactive interface where users can input expressions and get results.

Graceful Exit: Users can type quit or exit to close the connection.

How It Works
When a client connects to the server, it spawns a new thread for communication using the MathServerCommunicationThread.
The server listens for mathematical expressions from the client.
The expressions are passed to the Unix bc command for evaluation.
Results are returned to the client.
The server runs indefinitely until manually stopped.

Prerequisites
Python 3.x: Ensure Python 3 is installed.
Linux-based System: The project depends on Unix-based system commands and won't work on Windows or macOS without significant modifications.
bc (basic calculator): This project relies on bc for mathematical evaluation. You can install it using:

sudo apt-get install bc
Running the Server
Clone or Download the Project:


git clone https://github.com/Praveenm1910/MathServer.git
cd MathServer

Run the Server:
Execute the Python script:
python3 Multi-Threaded_Math_Server.py

Connecting to the Server:
You can use any TCP client (like telnet, netcat, or a custom-built client) to connect to the server:

telnet <server-ip> 8111

Example
Once connected to the server, you can type mathematical expressions such as:

3 + 4 * 2
(5 * 5) + (2 * 10)

The server will return:
11
45

Usage
Type any valid math expression and press enter.
To exit the session, type quit or exit.

Future Updates
Cross-platform compatibility: Future versions may support Windows and macOS by using alternative math engines or command-line tools.
Enhanced error handling and support for additional math operations.
Support for advanced user commands.
Security improvements, such as input sanitization.
