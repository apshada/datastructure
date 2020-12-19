
objects are used to store keyed collections of various data and more complex entities.An object can be created with figure brackets {…} with an optional list of properties.A property is a “key: value” pair, where key is a string (also called a “property name”), and value can be anything
methods to create object
```
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
```
literals and property
```
let user = {     // an object
  name: "John",  // by key "name" store value "John"
  age: 30        // by key "age" store value 30
};
```
we can add values using 
 ```user.isAdmin = true```
so now object will be like
```
let user = {     // an object
  name: "John",  // by key "name" store value "John"
  age: 30        // by key "age" store value 30
  isAdmin: true
};
```
To remove a property, we can use delete operator: ```delete user.age;```
```let user = {
  name: "John",
  age: 30,
  "likes birds": true  // multiword property name must be quoted
};
```
For multiword properties, the dot access doesn’t work: ```// this would give a syntax error
user.likes birds = true```

There’s an alternative “square bracket notation” that works with any string:
```
let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];
```
## Array methods
map() - : The map() method creates a new array with the results of calling a function for every array element.This method calls the provided function once for each element in an array, in order.
syntax - : array.map(function(currentValue, index, arr), thisValue)
```
var persons = [
  {firstname : "Malcom", lastname: "Reynolds"},
  {firstname : "Kaylee", lastname: "Frye"},
  {firstname : "Jayne", lastname: "Cobb"}
];
function getFul(items){
    var fname = [items.firstname,items.lastname].join(" ");
return fname;
}
var n = persons.map(getFul);
console.log(n); //["Malcom Reynolds", "Kaylee Frye", "Jayne Cobb"]
```
```
var op = ['1','2','3',4,5,6,7];
var x = op.map(myFun);
function myFun(op){
    return op+1;
}
console.log(x);    // ["11", "21", "31", 5, 6, 7, 8]
```
concat() - :
The concat() method is used to join two or more arrays.
This method does not change the existing arrays, but returns a new array, containing the values of the joined arrays.
```
var hege = ["Cecilie", "Lone"];
var stale = ["Emil", "Tobias", "Linus"];
var children = hege.concat(stale);
```
copyWithin() - : The copyWithin() method copies array elements to another position in the array, overwriting the existing values.This method will never add more items to the array.
length of array is not chaged it's but it adds elements
Note: this method overwrites the original array.
 ```
 var fruits = ["Banana", "Orange", "Apple", "Mango", "peach", "raspberry"];
fruits.copyWithin(2, 0);
console.log(fruits); //["Banana", "Orange", "Banana", "Orange", "Apple", "Mango"]
 ```
 filter() -: The filter() method creates an array filled with all array elements that pass a test (provided as a function).
Note: filter() does not execute the function for array elements without values.
Note: filter() does not change the original array.
```
var ages = [32, 33, 16, 40];

function checkAdult(age) {
  return age >= 18;
}
var fr = ages.filter(checkAdult);
console.log(fr);  //[32, 33, 40]
```
find() - :
The find() method returns the value of the first element in an array that pass a test (provided as a function).
The find() method executes the function once for each element present in the array:
If it finds an array element where the function returns a true value, find() returns the value of that array element (and does not check the remaining values)
Otherwise it returns undefined
Note: find() does not execute the function for empty arrays.
Note: find() does not change the original array.
```
var ages = [3, 10, 18, 20];

function checkAdult(age) {
  return age >= 18;
}
var t = ages.find(checkAdult)
console.log(t); //18

```
### this operator
Objects are usually created to represent entities of the real world, like users, orders and so on:

### call,apply,bind
“this” always refers to an object.
“this” refers to an object which calls the function it contains.
In the global context “this” refers to either window object or is undefined if the ‘strict mode’ is used.

#### reduce 
The reduce() method reduces the array to a single value.
The reduce() method executes a provided function for each value of the array (from left-to-right).
The return value of the function is stored in an accumulator (result/total).

``` 
let arr = [1,2,3,4];
arr.reduce( (total,currentValue, currentIndex,nums ) => {return nums[currentIndex] += total });
```
