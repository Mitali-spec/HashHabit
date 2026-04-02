# Understanding HTTP, Sessions, and express-session

## Concept Explanation

HTTP is stateless, which means it helps in communication between browser and server but has **zero memory**.

Because of this:
- Each request is independent
- The server does not remember previous requests

---

##  Problem

When a user interacts with a website:
- Login request → Server authenticates user
- Next request → Server forgets the user

So, requests are **unfamiliar to each other**

---

##  Solution: Session

A **session** is the server's memory about a specific user.

Using sessions:
- Requests become connected
- Server can recognize the same user across multiple requests

---

##  Security Concern

The browser cannot store user data directly because:
- It is unsafe
- Data can be modified by the user

---

##  Session ID

Instead of storing actual data:

- Browser stores a **session ID**
- It is a random string like: 123@ABC

  
---

##  How It Works

1. User logs in
2. Server creates a session (stores user data)
3. Server generates a session ID
4. Browser stores this session ID (in cookies)
5. Browser sends the session ID with every request
6. Server recognizes the session ID
7. Server retrieves the associated user data
8. Server fetches requested data and sends response back

---

##  Key Idea

- Browser stores only the **session ID**
- Server stores the **actual user data**
- Session ID connects multiple requests to the same user

---

##  express-session

We use `express-session` in Node.js (Express) to:
- Create sessions
- Store user data on server
- Manage session IDs using cookies

---

##  Final Understanding

HTTP is stateless (no memory).  
Sessions solve this by storing user data on the server.  
The browser stores only a session ID and sends it with every request.  
The server uses this ID to identify the user and return the correct data.  
`express-session` is used to implement this system in Express applications.
