# JavaScript Observations and Learnings



# let vs var


 While experimenting in the browser console,
 let appears to work similarly to var for basic
 variable declaration and updating.


 This similarity is mostly visible in simple
 console usage.


# In real-world programs, let and var differ in:

 - Scope
 - Redeclaration rules
 - Safety


 let is block-scoped and safer, making it the
 preferred choice in modern JavaScript.



# const Arrays and Stack Behavior


 Arrays declared with const cannot be reassigned,
 but their elements can still be modified.


# Example methods:

- push() : adds elements to the end
 - pop()  : removes elements from the end


 Using push() and pop(), JavaScript arrays
 can behave like a stack (LIFO - Last In, First Out).



# Primitive Data Types in JavaScript


# JavaScript primitive data types include:

- string
- number
- boolean
- null
- undefined



# Understanding null


 null is a primitive data type that represents
 an intentional absence of value.


 However:

 typeof null returns "object"


 This is a historical bug in JavaScript kept for
 backward compatibility.


 Despite this behavior, null is NOT an object.



# undefined vs null


# undefined:

- Variable is declared
- No value has been assigned yet


# null:

- Explicitly assigned by the developer
- Indicates an empty or unknown value




# JavaScript Functions – Core Concepts


# Block of Code

 Anything written inside { } is called a block of code.
 A function is also a block of code that is written
 once and executed whenever it is called.



# Parameters vs Arguments


# Arguments:

- Values passed to a function when calling it


# Parameters:
- Variables defined inside the function
  to receive those values



# Arrow Functions


 An arrow function is a shorter and cleaner way
 to write functions in JavaScript.


# Example:


const square = x => x * x;



# Calculator Logic (Arrow Function)

const calculate = (a, b, operator) => {
   if (operator === "+") return a + b;
   if (operator === "-") return a - b;
   if (operator === "*") return a * b;
   if (operator === "/") return a / b;
   return "Invalid operator";
 };



# ARRAY OF OBJECTS (JavaScript)


# Example of an array of objects

Used commonly in backend to store multiple records


let users = [
  { name: "Naruto", role: "admin" },
  { name: "Sakura", role: "editor" },
  { name: "Sasuke", role: "user" }
];



# FRONTEND, BACKEND & DATABASE COMMUNICATION


 Communication between frontend and database
 happens via the backend.


 Communication between frontend and backend
 happens using JSON.


 JSON is the standard data format used
 to send and receive data.



# JSON EXAMPLE


# Normal JavaScript Object

let user = {
  name: "Mitali",
  age: 20
};


# JSON Version

{
  "name": "Temari",
  "age": 20
}



# JSON RULES



# 1. Keys must be inside double quotation marks
# 2. JSON contains data only
# 3. No functions or logic are allowed in JSON
