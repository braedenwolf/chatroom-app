# chatroom-app
### Instructions for use
1. Compile Server
2. Launch Server, specifying a port number and number of chat rooms
3. Launch Client, specifying the server IP and port number
5. Enter a username and send messages
6. Change your chat room by selecting an option from the menu and clicking the Change Room button

### Command line argument formats
- Server: `./Server <portNumber> <maxRooms>`
- Client: `python ./Client.py <ip_address> <port_number>`

### Notes for chat room functionality
* Client
  * Single socket
  * Two threads: One (main program thread) for sending/GUI events and another for receiving
    * Allows the client to both wait for new messages and send messages. Both threads use the same socket.
* Server
  * Single server socket for welcoming clients
  * One socket and one thread per client
  * Synchronization: Semaphore used to prevent multiple threads from concurrently accessing the shared list of clients
