## DOMContentLoaded Event 

- A button click is an **event**.
- Similarly, **DOMContentLoaded** is also an **event**.

### What happens when a browser opens a website?

1. The browser loads the HTML.
2. It creates the **DOM (Document Object Model)** structure from the HTML.
3. Once the DOM is fully built, all elements become accessible using JavaScript.

### What does DOMContentLoaded do?

- The `DOMContentLoaded` event fires **after the HTML is completely loaded and parsed**.
- It ensures that all DOM elements are available before JavaScript runs.

### Why is it important?

- If JavaScript runs before the DOM is ready, it may not find elements (causing errors).
- Using `DOMContentLoaded` ensures your code runs at the right time.

### Example

```js
document.addEventListener("DOMContentLoaded", () => {
  const element = document.getElementById("myElement");
  console.log(element); // This will work correctly
});
