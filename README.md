## Network-Project

# Stateless password manager
--------------------

 - A password manager is designed to help a user store and manage online credentials. 
 - Stateless password managers do not require to store a database since the passwords are generated randomly using the master password and a key generation function.
 - The project aims to create a stateless password manager service. 
    - The client can enter the name of the website and a strong password is automatically generated. 
    - To retrieve the password, the process is the same

## Features

 - Secure Encryption using HMAC
 - Stateless password server: Does not need database.
 - One master password for all your passwords :P
 - Command line interface - Ease of use
 - High speed service - Developed in GoLang


## Working 

#### Services

 - /getPass
    - generates password given username, master secret and website name
 - /help
    - displays help message
 - /getSpec
     - prints out the specifications of the program
 - /quit
    - quit server connection

#### Client Side
- `main()`              : Creates connection with the server, calls helper functions and gets input from the client
- `handleConnection()`  : Reads the socket file and handle the connection
- `handleCommands() `   : Checks if the command is valid and if it is sends it to the server and gets the corresponding output if else does nothing


#### Server Side
 - 

 - Listen to client through the socket. 
    - Module: net.Listen(, “ip:port”)
 - Accept packet from Client using a TCP socket connection.
 - Use master password to generate new password for the server.
 - Modules
     - Generate Password (‘>/gen_pass’) 
     - Quit (>/quit)
 - Generates secure password from the genPASS(username,website, secret)

z
