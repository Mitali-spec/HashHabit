
# Understanding Express, Server, Ports, and Login Flow


# ------------------------------------------------------------
# Express and Server Basics
# ------------------------------------------------------------

 Express.js is used to write backend code that allows our computer to act as a server.
 Express helps create a server program on top of Node.js.

 A server listens on a network port and waits for requests.
 The computer / operating system owns the ports, not the server itself.
 A server program binds to a port provided by the OS.

# A server can:
 - Handle HTTP requests and responses
 - Handle HTTP methods such as GET and POST

# ------------------------------------------------------------
# How a Server Starts
# ------------------------------------------------------------

 1. A server program is written (for example, using Express).
 2. The program is executed, creating a process in the OS.
 3. The server program requests a port from the OS.
 4. The OS reserves that port for the server.
 5. The server starts listening on that port.
 6. The port is opened when the server starts.
 7. The server can listen forever on that port and wait for requests.

# Important notes:
 - Ports are NOT opened per request.
 - Requests simply arrive at an already-open port.

# ------------------------------------------------------------
# Login Form and Database Flow
# ------------------------------------------------------------

 I created an HTML login form.
 HTML is used only to collect user input.

 To store user data in a database, a backend server is required.

 When the user fills the login form and submits it:
 - The browser sends an HTTP POST request to the server.
 - The server program is already running and listening on a port.
 - The request arrives at that port.

 The server then:
 - Receives the request
 - Extracts the user’s data
 - Processes and validates the data
 - Communicates with the database

 The database:
 - Stores the user information

 After that:
 - The server sends an HTTP response back to the browser
 - The browser displays the result to the user

# ------------------------------------------------------------
# Complete Request Flow
# ------------------------------------------------------------

 User fills login form
   ↓
 Browser sends HTTP request (POST)
   ↓
 Server program (Node.js + Express)
 (listening on a port)
   ↓
 Server validates and processes data
   ↓
 Server communicates with database
   ↓
 Database stores data
   ↓
 Server sends response
   ↓
 Browser shows result

# ------------------------------------------------------------
# Final Summary
# ------------------------------------------------------------

# HTML collects data
# The server processes data
# The database stores data
