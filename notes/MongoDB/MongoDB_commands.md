# MongoDB Basic Commands (mongosh)

## 1. View All Databases

```javascript
show dbs
```

Displays all databases present in MongoDB.

---

# 2. Create or Switch Database

```javascript
use db_name
```

Example:

```javascript
use schoolDB
```

If the database **does not exist**, MongoDB will **create it automatically when data is inserted**.

---

# 3. View Collections Inside a Database

```javascript
show collections
```

Displays all collections present in the current database.

---

# 4. Insert Data into a Collection

```javascript
db.users.insertOne({
  name: "Mili",
  age: 21
})
```

This inserts a document into the `users` collection.

If the collection **does not exist**, MongoDB will **create it automatically**.

---

# 5. View All Data in a Collection

```javascript
db.users.find()
```

Displays all documents stored in the `users` collection.

---

# 6. View One Document

```javascript
db.users.findOne()
```

Displays the **first document** found in the collection.

---

# 7. Update Data

```javascript
db.users.updateOne(
  { name: "Mili" },
  { $set: { age: 20 } }
)
```

Explanation:

* Finds the document where `name = "Mili"`
* Updates the age to `20`

---

# 8. Delete Data

```javascript
db.users.deleteOne({ name: "Mili" })
```

Deletes the **first document** matching the condition.

---

# MongoDB Structure Reminder

```
Database
   → Collection
        → Document
```

Example:

```
schoolDB
   → users
        → { name: "Mili", age: 21 }
        → { name: "Riya", age: 22 }
```
