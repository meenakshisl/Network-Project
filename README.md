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

### Services

 - /getPass
    - generates password given username, master secret and website name
 - /help
    - displays help message
 - /getSpec
     - prints out the specifications of the program
 - /quit
    - quit server connection

### Client Side

**Functions**

- `main()`              : Creates connection with the server, calls helper functions and gets input from the client
- `handleConnection()`  : Reads the socket file and handle the connection
- `handleCommands() `   : Checks if the command is valid and if it is sends it to the server and gets the corresponding output if else does nothing

**Socket**
 - Module used : `net`
 - creation of socket connection with server : `net.Dial("tcp","<ip address>:<port>")`
 

### Server Side

**Functions**
 
 - `main()`       : Creates socket and listens for connection from clients
 - `handleConnection(net.Conn)` : Scans the socket file and handles connection with client
 - `handleMessage(string,net.Conn)` : carries out the service requested by the client
 - `getPass(string,string,string)`  : performs secure HMAC encryption and generates password given username , website and password

**Socket**

- Module Used : `net`
- socket creation and connection : `net.Listen("tcp","<ip address>:<port>")`



