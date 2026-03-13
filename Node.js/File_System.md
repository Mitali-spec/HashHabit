# File System (fs) in Node.js

The **File System module** is used by servers to **read and write files on the computer**.

Servers use the file system to store information such as:

- When a user logged in
- When a user logged out
- Time and date of activities
- What file was uploaded
- What content was stored
- Database name
- API keys
- Logs and configuration data

---

## Writing Data to a File

To write data into a file, we use:

```javascript
fs.writeFile()
```

Example:

```javascript
const fs = require("fs");

fs.writeFile("data.txt","Hello from Node",function(err){
    if(err){
        console.log("Error writing file");
        return;
    }

    console.log("File saved");
});
```

This will create or update **data.txt** and write the text inside it.

---

## Reading Data from a File

To read data from a file, we use:

```javascript
fs.readFile()
```

Example:

```javascript
const fs = require("fs");

fs.readFile("data.txt",function(err,data){
    if(err){
        console.log("Error reading file");
        return;
    }

    console.log(data.toString());
});
```

This reads the content of **data.txt** and prints it.

---

## Note

For the above codes to work, file and code should be in the same folder.


## Summary

| Function | Purpose |
|--------|--------|
| `fs.writeFile()` | Writes data into a file |
| `fs.readFile()` | Reads data from a file |
