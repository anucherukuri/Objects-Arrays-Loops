📝 - Arrays, Objects, Loops, and much more

**Objects**

Numbers, boolean and strings are like the atoms that compose our data. Many types of information require more complex structures, though. Objects let us group together simple data types into a single structure.

const user = {
	name: "John", // string property
	surname: "Rambo", // another string property
	age: 18, // numeric property
	isStudent: true, // boolean property
};



**Properties**

You can access to objects properties in two ways: dot notation and square brackets.

console.log(user.name); // "John"
console.log(user["name"]); // same result


In the same way you can change the values of the properties too

user.name = "Roger"; // equivalent to user["name"] = "Roger";

console.log(user.name); // "Roger"



**Delete Properties**

If you need to delete some properties from your objects you can use the reserved keyword delete in front of the object and his property

delete user.name;

console.log(user.name); // undefined


Object.assign

let obj2 = obj1 is not enough to clone an object, because there will always be an unwanted bind between the two. A preferrable way to copy all the properties from an object into another one is the following

let obj1 = {
   name: "John"
}

let obj2 = {}

Object.assign(obj2, obj1); //

console.log(obj2.name); // "John"


**Arrays**

‌JS as many other programming languages provides a way to store sequentially some data. It is called array and is written as a list of values between square brackets, each one separated by commas

let listOfNumbers = [2, 3, 5, 7, 11]; // array of numbers
let listOfNames = ["John","Arnold","Chuck"]; // array of strings
let listOfBools = [true, false, false, false, true]; // array of booleans

We can access to a specific element of the array by using its index, or position in the list, surrounded again by square brackets
N.B. arrays' indexes start from zero!

console.log(listOfNumbers[0]); // 2
console.log(listOfNumbers[1]); // 3
console.log(listOfNumbers[4]); // 11

What happens if you try to log array element with index 5 or above?


**Arrays of objects**

We can have arrays of any type, even containing advanced types like objects

const users = [
       {
  	     name: "John",
  	     surname: "Rambo",
  	   },
  	   {
  	     name: "Arnold",
  	     surname: "Schwarzenegger",
  	   },
  	   {
  	     name: "Chuck",
  	     surname: "Norris",
  	   },
]; // an array of three elements, each one of them is an object with two properties

console.log(users[0]); // {name: "John", surname: "Rambo"}
console.log(users[2].surname); // "Norris"


**Useful arrays methods**

Does it mutate?

**Push and pop** are array methods which can be used to add or remove elements to and from the end of an array

**push**
const myArray = [1,2,3]

myArray.push(4)
myArray.push(5)

console.log(myArray) // [1,2,3,4,5]

**pop**
console.log(myArray.pop()) // 5

console.log(myArray) // [1,2,3,4]


We can search for a specific value with indexOf() and lastIndexOf(), they both return the index of the first occurance if found or -1 if not found. The difference between the two is that lastIndexOf starts from the end of the array, so if two elements are duplicated it returns just the first occurance
indexOf
console.log(myArray.indexOf(1)); // 0
lastIndexOf
const myArray = [1,2,3,4,5,1,6]
console.log(myArray.lastIndexOf(1)); // 5


Slice method can be used to return just a part of an array, you can specify a start index and optionally an end index. If end index is not specified the array will be sliced till the last element
slice
const myArray = [1,2,3,4,5]

console.log(myArray.slice(2,4)); // [3,4]
console.log(myArray.slice(2)); // [3,4,5]


The concat method can be used to glue arrays together to create a new array
concat
let list = [1, 2, 3, 4,].concat([5,6,7,8]) // list becomes [1,2,3,4,5,6,7,8] 


**Loops**

Loops allow developers to shorten what could be hundreds of lines of code to just a few by repeating same or similar lines of code over multiple iterations

**While Loop**
Looping control flow allows us to go back to some point in the program where we were before and repeat it with our current program state. If we combine this with a variable that counts, we can do something like

let number = 0;
while (number <= 10) {
    console.log(number);
    number = number + 1;
}

A statement starting with the while keyword followed by parenthesis containing an expression is a loop. The loop keeps entering that statement as long as the expression produces a value that gives true

**For Loop**
For loop in JS:
for (let i=0; i<5; i++){
   console.log(i);
}

// Output:
// 0
// 1
// 2
// 3
// 4

The round parenthesis of a for loop contain three main parts. The first one is the initialization of the variable from which the loop will start "counting", the second one is the condition thta checks whether the loop must continue or not. Finally the third one is used to update the variable on each iteration of the loop


**Breaking out of a loop**

A for loop finishes usually when the condition in the round parenthesis becomes false. There is also a reserved keyword used to force exit from a loop even though the condition is still false, this keyword is break

for (let i=0; i<5; i++){
   if(i === 3) break;
   console.log(i);
}

// Output:
// 0
// 1
// 2


**Loops & Arrays**

A very convenient way to interact with arrays is by looping them over with a for loop

const myArray = [0,1,2,3,4,5]
for (let i = 0; i < myArray.length; i++) {
    let element = myArray[i];
    console.log("Hey this is the element --> ", element)
}

We use the variable i to represent the index of each element of the array. Therefore starting from index 0 (first element of the array) till index equals to length of the array - 1, we should be able to perform actions on an array accessing to each element one by one
