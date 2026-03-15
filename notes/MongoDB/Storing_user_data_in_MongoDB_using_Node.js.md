# Storing User Data in MongoDB using Node.js

After connecting **Node.js** to **MongoDB**, we need a way to **structure the data** and **send it to the database**.

For this we use **Mongoose Schema and Model**.

---

# 1️⃣ Create a Schema

A **Schema** defines **how the data will look when stored in MongoDB**.

Example:

```javascript
const schema = new mongoose.Schema({
    username: String,
    password: String
});
```

Explanation:

```
username → will store the user's username
password → will store the user's password
```

So every user document stored in MongoDB will follow this structure.

Example stored document:

```json
{
  "username": "rahul",
  "password": "1234"
}
```

---

# 2️⃣ Create a Model

A **Model** is used to **talk to MongoDB from Node.js**.

```javascript
const user = mongoose.model("user", schema);
```

Explanation:

```
"user"  → name of the collection
schema  → structure of the data
```

The model allows us to:

```
create data
save data
find data
update data
delete data
```

---

# 3️⃣ Save User Data to MongoDB

When a user submits the **signup form**, the browser sends the username and password to the server.

Inside the route:

```javascript
app.post("/signup", async function(req, res) {

    const username = req.body.username;
    const password = req.body.password;

    // Create a new user following the schema structure
    const newuser = new user({
        username: username,
        password: password
    });

    // Save user to MongoDB
    await newuser.save();

    res.send("Data stored in MongoDB");
});
```

Flow of what happens:

```
User fills signup form
        ↓
Browser sends POST request
        ↓
Server reads req.body
        ↓
New user object is created
        ↓
Mongoose saves data in MongoDB
```

---

# 4️⃣ Viewing Stored Data

To view the stored users:

1. Open **MongoDB Compass**
2. Connect to:

```
mongodb://127.0.0.1:27017
```

3. Open the database:

```
username_and_password
```

4. Open the collection:

```
users
```

Now you can see all stored users.

Example document in MongoDB:

```json
{
  "_id": "6654a7e1...",
  "username": "rahul",
  "password": "1234",
  "__v": 0
}
```

---

# Summary

Steps to store user data in MongoDB:

```
1. Connect Node.js to MongoDB
2. Create a Schema (structure of data)
3. Create a Model (talk to database)
4. Get user data from req.body
5. Create a new user object
6. Save it using save()
7. View stored data in MongoDB Compass
```
