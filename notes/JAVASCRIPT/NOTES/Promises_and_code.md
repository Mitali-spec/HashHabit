# Asynchronous JavaScript – Promises Example

JavaScript is fast, but operations like:

- Opening files
- Reading files
- Calling APIs

are slow.

JavaScript does NOT wait for these operations to finish.
They run in the background and complete later.

We handle this using:
- setTimeout
- Promises
- async / await

## Concept Used

- Promise
- setTimeout
- Asynchronous execution


## Example: Simulated Login Using Promise

This example simulates a delayed login process.

Behavior:
- Waits 6 seconds
- If password is "1234" → success
- Otherwise → failure


## JavaScript Code


function login(password) {


  if (password === "1234") {

  
    return new Promise((resolve, reject) => {

    
      setTimeout(() => {

      
        resolve("success");

        
      }, 6000);

      
    });

    
  } else {

  
    return new Promise((resolve, reject) => {

    
      setTimeout(() => {

      
        reject("failure");

        
      }, 6000);

      
    });

    
  }

  
}


login("1234")


  .then((message) => {

  
    console.log(message);

    
  })

  
  .catch((error) => {

  
    console.log(error);

    
  });



## Explanation

- JavaScript does not block execution
- setTimeout simulates delay
- Promise handles success and failure
- .then() handles resolved value
- .catch() handles rejected value

## Key Takeaways

- JavaScript is non-blocking
- Slow operations run asynchronously
- Promises handle delayed results
- async / await is built on top of Promises
