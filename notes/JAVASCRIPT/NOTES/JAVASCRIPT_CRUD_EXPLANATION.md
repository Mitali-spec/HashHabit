#  Task Manager (Frontend ↔ Backend Flow Explained)

##  Frontend: Handling Button Click

```javascript
save_task.addEventListener("click", async function (e) {

    e.preventDefault(); // ❌ Stop page reload (VERY IMPORTANT)

    // 👉 e is the event object (click event)

    let response = await fetch("/add_task", {
        method: "POST",
        headers: {
            "Content-Type": "application/json"
        },
        body: JSON.stringify({ add_task: task })
    });

});
```

##  Explanation

- `e.preventDefault()`
  - Stops browser’s default behavior  
  - Default for form = reload + submit  
  - ✅ Lets JavaScript handle everything manually  

- `fetch()`
  - Sends data from frontend → backend  

- `await`
  - Waits until server responds  

- `"Content-Type": "application/json"`
  - Tells server: data is in JSON format  

- `JSON.stringify({ add_task: task })`
  - Converts JS object → JSON string  
  - This is the **actual data being sent**

---

##  Backend: Receiving Data (POST)

```javascript
app.post("/add_task", async (req, res) => {
    try {
        const taskText = req.body.add_task;

        // 👉 Check if task is empty
        if (!taskText || taskText.trim() === "") {
            return res.status(400).json({ success: false });
        }

        // 👉 Create new task object (prepare for DB)
        const new_task = new Task({ add_task: taskText });

        // 👉 Save to MongoDB
        await new_task.save();

        // 👉 Send success response
        res.status(201).json(new_task);

    } catch (err) {
        console.log(err);

        // 👉 If something breaks
        res.status(500).json({ success: false });
    }
});
```

##  Explanation

- `app.post()` → listens for POST requests  
- `req.body.add_task` → gets data from frontend  

###  Validation

```javascript
if (!taskText || taskText.trim() === "")
```

- `!taskText` → nothing sent  
- `.trim()` → removes spaces  

###  If Invalid

```javascript
res.status(400).json({ success: false });
```

- **400 = Bad Request**

###  Create Task

```javascript
const new_task = new Task({ add_task: taskText });
```

- Prepares data for MongoDB  

###  Success Response

```javascript
res.status(201).json(new_task);
```

- **201 = Created**

###  Error Handling

```javascript
res.status(500).json({ success: false });
```

- **500 = Server Error**

---

##  Example Response

```json
{
  "_id": "123",
  "add_task": "Buy milk"
}
```

---

##  Frontend: Creating Task Element

```javascript
function createTaskElement(data) {

    let li = document.createElement("li");

    let span = document.createElement("span");
    span.innerText = data.add_task;

    li.appendChild(span);

    // 👉 Store MongoDB ID in HTML
    li.setAttribute("data-id", data._id);

    return li;
}
```

##  Output HTML

```html
<li data-id="TASK_ID">
    <span>Task Text</span>
</li>
```

---

##  DELETE: Remove Task

```javascript
app.delete("/delete_task/:id", async (req, res) => {
    try {
        console.log("Delete request ID:", req.params.id);

        //  Delete from MongoDB using ID
        const deleted = await Task.findByIdAndDelete(req.params.id);

        if (!deleted) {
            return res.status(404).json({ success: false });
        }

        res.json({ success: true });

    } catch (err) {
        console.log(err);
        res.status(500).json({ success: false });
    }
});
```

###  Explanation

- `app.delete()` → handles delete request  
- `req.params.id` → gets ID from URL  
- Deletes task from MongoDB  

###  If Not Found

```javascript
res.status(404).json({ success: false });
```

- **404 = Not Found**

###  Error

```javascript
res.status(500).json({ success: false });
```

---

##  PUT: Update Task

```javascript
app.put("/update_task/:id", async (req, res) => {
    try {
        const updated = await Task.findByIdAndUpdate(
            req.params.id,
            { add_task: req.body.add_task },
            { new: true } // 👉 return updated data
        );

        if (!updated) {
            return res.status(404).json({ success: false });
        }

        res.json(updated);

    } catch (err) {
        res.status(500).json({ success: false });
    }
});
```

###  Explanation

- `PUT` → update existing data  
- Uses ID to find and update  
- `{ new: true }` → returns updated task  

---

##  HTTP Methods Summary

| Method | Purpose |
|--------|--------|
| GET    | Fetch data 📥 |
| POST   | Create data ➕ |
| PUT    | Update data ✏️ |
| DELETE | Remove data ❌ |

---

##  Key Concepts Recap

- `preventDefault()` → stops reload  
- `fetch()` → frontend ↔ backend communication  
- `JSON.stringify()` → send data  
- `req.body` → receive data  
- `.trim()` → remove extra spaces  

### 📊 Status Codes

| Code | Meaning |
|------|--------|
| 200  | OK ✅ |
| 201  | Created ✅ |
| 400  | Bad Request ❌ |
| 404  | Not Found ❌ |
| 500  | Server Error 💥 |
