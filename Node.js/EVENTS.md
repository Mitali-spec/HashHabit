# Events in Node.js

An **event** occurs when some activity happens and Node.js responds to it.

Node.js programs are **event-driven**, which means the server reacts whenever an event happens.

---

## Examples of Events

### 1. Login Event
When a new user logs in, an event occurs.

Example:
- A new user logs in
- Node.js detects the activity
- The server processes the login

This is a **login event**.

---

### 2. Request Event
When a browser requests a website from the server.

Flow:

Browser → Request → Server  
Server → Response → Browser

The browser sends a request and the server responds.  
This is called a **request event**.

---

### 3. Connection Event
When a user connects to the server or a website.

Example:
- User opens a website
- A connection is established
- The server detects the connection

This is a **connection event**.

---

### 4. Error Event
When something goes wrong in the server.

Example:
- File not found
- Database error
- Server crash

Node.js detects the problem and the server handles it.

This is called an **error event**.

---

## Summary

| Event Type | Meaning |
|------------|--------|
| Login Event | A user logs into the system |
| Request Event | Browser sends request to server |
| Connection Event | A user connects to the server |
| Error Event | Something goes wrong and the server handles it |
