# How a Node.js Server Works

We write the **server program in Node.js**.

When the **server program starts**, a **process runs in the Operating System (OS)**.

The **OS assigns a port** to the server.  
The server **listens on that port** for incoming requests.

When a **browser sends a request**, the server processes it and **sends a response back**.

---

## Flow

Browser
   │
   │ request
   ▼
Node Server
   │
   │ response
   ▼
Hello from my server

---

## Example Code

```javascript
const http = require("http");

const server = http.createServer(function(req, res) {
    res.write("Hello from my server");
    res.end();
});

server.listen(3000);
```

---

## Example URL

```
http://localhost:3000
```

The browser sends a **request**, and the server sends a **response**.
