# Backend Basics 

## What is a Backend Server?
- A backend server is a computer that lets the client talk to the database.
- It handles requests made by clients.
- The backend server acts as a middleman.
- The client never talks directly to the database (for security reasons).

---

## Client vs Server
- **Client**: A computer or application that requests data.
- **Server**: A computer that decides what to do, fetches data, and sends it to the client.

**Simple understanding:**
- Client = asks  
- Server = decides + fetches + responds  

---

## What is HTTP?
- HTTP is a rule or protocol that tells the client how to talk to servers.
- It defines how requests and responses are exchanged.

---

## What is a HTTP method

HTTP methods are actions in an HTTP request that tell the server what to do with a resource (data).

If the request contains GET, it means:
“Hey server, please send me the data.”

If the request contains POST, it means:
“Hey server, I am sending you data, please process or store it."


## GET vs POST
- **GET**
  - Used to fetch data from the server.
  - Data is visible in the URL.
  - Example: opening a website or searching something.

- **POST**
  - Used to send data to the server.
  - Data is hidden from the URL.
  - Example: login and signup forms.

**Conclusion:**
- GET is used to fetch data  
- POST is used to send data to the server  

---

## What is a Request?
- A request is a message sent by one computer to another to ask for or send data.

---

## What is a Response?
- A response is the reply sent by the server to the client after processing the request.

---

## What is a Port?
- A port is like a door on a computer.
- To talk to a computer, another computer knocks on its door (port).
- If the door is open, data can be accessed.

**Example:**
- Port 3000 → backend server
- Port 80 → websites

---

## Summary
- Backend server handles logic and database communication
- Client sends requests
- Server processes and responds
- HTTP defines communication rules
- GET fetches data
- POST sends data
- Ports decide where the data goes
