# Session-Based Authentication Flow

##  Login Code

```js
if (existing_user.password === password) {

    // Store user ID in session so requests remain connected
    req.session.userId = existing_user._id;

    // Redirect to homepage after successful login
    res.redirect("/HOME_PAGE/home_page.html");
}
```

##  Explanation

User ID gets stored in `req.session`, and then the page is redirected to the homepage.

##  How It Works

- When the user logs in successfully, the server stores:
  
  `req.session.userId = existing_user._id`

- The server creates a **session**
- A **session ID** is generated and sent to the browser as a cookie

##  On Every Request

- The browser sends the **session ID (cookie)** to the server
- The server uses this session ID to:
  - Find the session
  - Access stored data like:
    
    `req.session.userId`

- This is how the server recognizes the user

##  Key Concept

- Session ID is like a **key**
- It connects the browser to the data stored on the server

##  Full Flow

1. User logs in
2. Server stores user ID in session
3. Server sends session ID to browser (cookie)
4. Browser redirects to homepage
5. On every request:
   - Browser sends session ID
   - Server finds session
   - Server accesses `req.session.userId`
   - Server recognizes user
   - Server sends requested data

##  Final Understanding

- Browser does NOT store actual user data
- Browser stores only the **session ID**
- Server stores the **actual user data**
- Session ID acts as a connection between browser and server

##  One-Line Summary

Session ID = Browser’s key to access data stored in backend  
Server uses this key to recognize user and send correct data
