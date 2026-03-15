# HOW SERVER, PORT, AND ROUTE WORK 

 A server is a program that listens on a specific port.
 A port is like a door number where the server waits for requests.

# When a client (browser or app) sends a request:
 - The request is sent to the server's IP address and port.
 - The server receives the request on that port.

# The request contains:
 - HTTP method (GET, POST, etc.)
 - Route / path (e.g., /login, /logout, /signup)
 - Optional data (e.g., username, password)

 Inside the server program, there are multiple handlers (logic/functions).
 Each handler is responsible for a specific task.

# Examples:
 - If the route is /login, run login logic
 - If the route is /logout, run logout logic
 - If the route is /signup, run signup logic

 The job of a ROUTE is to decide which part of the server program (which handler or function) should handle the client request.

# Flow summary:

 Client → Port → Server → Route → Handler → Response

# In simple words:
 - Port receives the request
 - Route decides where it should go
 - Handler processes the request and sends a response
