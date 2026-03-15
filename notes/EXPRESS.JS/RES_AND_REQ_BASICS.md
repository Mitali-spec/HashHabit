# Express.js – Request & Response Basics

These are the basic concepts used when building servers using **Express.js** in **Node.js**.

---

# Request & Response

When a browser communicates with a server:

Browser → Request → Server
Server → Response → Browser

In Express:

```
req = request (message from browser)
res = response (message from server)
```

---

# 1️⃣ req.body

Used when the browser sends data using a **POST request** (usually from a form).

### Example HTML Form

```html
<form action="/signup" method="POST">
<input type="text" name="username">
<input type="password" name="password">
<button type="submit">Submit</button>
</form>
```

### Example Server Code

```javascript
app.post("/signup", function(req,res){

    const username = req.body.username;
    const password = req.body.password;

    console.log(username);
    console.log(password);

});
```

### Meaning

```
req.body
```

contains the **data sent from the form**.

Example value:

```
{
 username: "rahul",
 password: "1234"
}
```

---

# 2️⃣ req.params

Used when data is sent **inside the URL path**.

### Example URL

```
/user/25
```

### Route

```javascript
app.get("/user/:id", function(req,res){

    console.log(req.params.id);

});
```

### Output

```
25
```

### Meaning

```
req.params
```

is used to read **values inside the URL path**.

---

# 3️⃣ req.query

Used when data is sent **after ? in the URL**.

### Example URL

```
/search?name=rahul
```

### Server Code

```javascript
app.get("/search", function(req,res){

    console.log(req.query.name);

});
```

### Output

```
rahul
```

### Meaning

```
req.query
```

reads **query parameters from the URL**.

---

# 4️⃣ res.send()

Used to send **text or HTML response to the browser**.

### Example

```javascript
res.send("User created successfully");
```

Browser will display:

```
User created successfully
```

---

# 5️⃣ res.json()

Used to send **JSON data to the browser**.

### Example

```javascript
res.json({
 name: "Rahul",
 age: 20
});
```

Browser receives:

```
{
 name: "Rahul",
 age: 20
}
```

This is commonly used when building **APIs**.

---

# Quick Summary

```
req.body   → data sent from forms (POST request)

req.params → data inside URL path

req.query  → data after ? in URL

res.send() → send text or HTML to browser

res.json() → send JSON data to browser
```

---

# Example Full Code

```javascript
app.post("/signup", function(req,res){

    const username = req.body.username;

    res.send("Signup successful");

});
```

Flow:

```
User fills form
      ↓
Browser sends request
      ↓
Server reads req.body
      ↓
Server sends response using res.send()
```
