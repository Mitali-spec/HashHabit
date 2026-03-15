# JavaScript Array Methods

Methods are functions that belong to an object. Array is an object.

# Some commonly used array methods are:

- push
- pop
- map
- filter


# map()


 map is used to create a NEW array
 
 It works with reference to the original array
 
 It does NOT change the original array
 
 It applies an operation to every element
 

# Example:

 let nums = [1, 2, 3]
 
 let doubled = nums.map(n => n * 2)
 
 Result: [2, 4, 6]
 
 Original array remains unchanged
 


# filter()


 filter is an array method used to select elements

 It returns a NEW array
 
 Elements are included based on a condition

 Original array is NOT changed
 

# Example:

let nums = [1, 2, 3, 4, 5]

let evenNums = nums.filter(n => n % 2 === 0)

Result: [2, 4]


# push()


 push is used to add an element at the end of an array
 
 It changes the original array


# pop()


 pop is used to remove the last element from an array
 
 It changes the original array
