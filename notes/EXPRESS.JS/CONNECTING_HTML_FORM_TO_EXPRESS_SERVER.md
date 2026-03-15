# Connecting HTML Form to Express Server

I created a signup page and connected it to an Express server built using Node.js.

## 1. HTML Form Changes

To connect the form with the server, I modified the form like this:

```html
<form action="/signup" method="POST">
```

- `/signup` is the **route** on the server.
- `POST` method is used because the form sends data (username and password) to the server.

---

# 2. Starting the Server

My Express server listens on **port 3000**.

To start the server, I opened CMD and navigated to the project directory:

```
EXPRESS_PRACTICE
```

Then I ran:

```bash
node express_app.js
```

The terminal displayed:

```
server listening on port 3000
```

This means the server started successfully.

---

# 3. Restarting the Server

If the server is already running and I want to restart it, I must first **terminate the running server**.

In CMD:

```
Ctrl + C
```

Then start the server again using:

```bash
node express_app.js
```

---

# 4. Opening the Website

After starting the server, I opened the browser and typed:

```
http://localhost:3000
```

The **signup HTML page appeared on the screen**.

---

# 5. Submitting the Form

When the user clicks the **Submit button**, the browser sends a **POST request** to the server at the `/signup` route.

The server handles this request using:

```javascript
app.post("/signup", function(req,res){

    const username = req.body.username;
    const password = req.body.password;

    console.log(username);
    console.log(password);

    res.send("User signed up");
});
```

---

# 6. What This Code Does

Step-by-step flow:

```
User fills form
        │
        ▼
Browser sends POST request to /signup
        │
        ▼
Server receives request
        │
        ▼
Server extracts username and password from req.body
        │
        ▼
Server prints username and password in the terminal
        │
        ▼
Server sends response "User signed up" to browser
```

---

# 7. Understanding req.body

When a user submits the form:

```
username = rahul
password = 1234
```

This data is sent to the server using the **POST method**.

Express stores this data inside:

```
req.body
```

Example structure:

```
req.body = {
   username: "rahul",
   password: "1234"
}
```

So:

```
req.body.username → gives the username
req.body.password → gives the password
```

---

# 8. Request and Response

```
Browser → sends REQUEST → Server
Server → sends RESPONSE → Browser
```

Example:

```
Request: POST /signup
Response: "User signed up"
```

---

# Conclusion

I successfully connected an **HTML signup form** to an **Express server**, received form data using `req.body`, printed it in the server console, and sent a response back to the browser.
