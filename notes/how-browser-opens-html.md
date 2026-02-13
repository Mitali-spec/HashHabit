# Opening an HTML file from File Explorer (No Server Involved)

 When I click an HTML file from my file explorer, it opens in my browser.
 This is similar to opening a PDF or an image file.
 The browser directly reads the HTML file from local storage.

# Protocol used:
 file://

# Important points:
 - The browser is acting as a file viewer, not as an HTTP client
 - No network communication takes place
 - No ports are used
 - No HTTP protocol is involved
 - No GET or POST requests are sent

# In this case:

 Client  -> Browser
 
 Server  -> None (my computer is NOT acting as a server)
 

# Definition of a real server:
 A server is a computer (or program) that:
 - Listens on a network port (e.g., 80, 443, 3000)
 - Understands the HTTP protocol
 - Can handle HTTP methods like GET and POST

# Conclusion:
 Opening an HTML file via file:// does NOT involve a server.
 HTTP methods like GET and POST only exist when a web server is running
 (e.g., localhost with Apache, Node.js, Python, etc.).
