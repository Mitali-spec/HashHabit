#  Issue Faced While Running My Website

##  Problem

I assumed that simply running my server and opening `http://localhost:3000` would make my website fully functional.

However, the website was **not working as expected** because:

* The frontend was **not sending data to the backend**
* Therefore, the backend was **not sending data to MongoDB**
* As a result, **no data was being stored**

---

##  Root Cause

```text
Frontend (UI) was not connected to Backend (Server)
```

 I was only updating the UI, not actually communicating with the server.

---

#  Solution Implemented

##  1. Connected Frontend to Backend using `fetch()`

I added the following code inside:

```js
save.addEventListener("click", async function () {
```

###  Code:

```js
// SEND DATA TO BACKEND
await fetch("/add_task", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({ add_task: task })
});
```

 This sends the task from frontend → backend.

---

##  2. Added JSON Middleware in Backend

```js
app.use(express.json());
```

 Required because:

* `fetch()` sends data in **JSON format**
* This middleware helps the server read `req.body`

---

##  3. Enabled Static File Serving

```js
app.use(express.static(__dirname));
```

👉 This allows the server to:

* Serve frontend files like `.html`, `.js`, `.css`
* Load `add_task.js` properly in the browser

---

#  Final Working Flow

```text
User clicks ADD
   ↓
Frontend (fetch request)
   ↓
Backend (Express server)
   ↓
MongoDB (stores task)
```

---

#  Key Takeaway

*  Just running the server does NOT make the app functional
*  Frontend must explicitly communicate with backend

 Always ensure:

```text
Frontend → Backend → Database
```

---

#  Outcome

After applying these changes:

* Data is successfully sent to backend
* Backend stores it in MongoDB
* Website is now fully functional

---
