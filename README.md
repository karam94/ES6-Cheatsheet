# ES6-Cheatsheet
An ES6. Made by myself, for myself, based on my own requirements &amp; how my head works. If it helps someone else, then awesome! Pull requests with improvements are more than welcome.

## Table of Contents
 - [String Literals](#String-Literals)
 - [Destructuring Objects](#Destructuring-Objects)
 - [Destructuring Arrays](#Destructuring-Arrays)
 - [Object Literals](#Object-Literals)
 - [For Of Loop](#For-Of-Loop)
 - [Spread Operator](#Spread-Operator)
 - [Rest Operator](#Rest-Operator)
 - [Arrow Functions](#Arrow-Functions)
 - [Default Parameters](#Default-Parameters)
 - [Includes Method](#Includes-Method)
 - [Let & Const](#Let-&-Const)
 - [Import & Export](#Import-&-Export)
 - [PadStart & PadEnd](#PadStart-&-PadEnd)
 - [Classes](#Classes)
 - [Trailing Commas](#Trailing-Commas)
 - [Async & Await](#Async-&-Await)
 - [Sets](#Sets)

## String Literals
```js
const firstName = "Barry";
const lastName = "Chuckle";

console.log(`${firstName} ${lastName}`); // Barry Chuckle
```
```js
const firstNumber = 100;
const secondNumber = 25;

console.log(`${firstNumber + secondNumber}`); // 125
```
```js
console.log(`I don't need a 

			new line`);
```

## Destructuring Objects
```js
const personalInformation = {
	firstName: "Barry",
	lastName: "Chuckle",
	city: "Rotherham"
}

// No need to write personalInformation.firstName, personalInformation.lastName, etc.
const { firstName, lastName } = personalInformation;
console.log(`${firstName} ${lastName}`); // Barry Chuckle
```
```js
const personalInformation = {
	firstName: "Barry",
	lastName: "Chuckle",
	city: "Rotherham"
}

// No need to write personalInformation.firstName, personalInformation.lastName, etc.
const { firstName: abc, lastName: def } = personalInformation;
console.log(`${abc} ${def}`); // Barry Chuckle
```

## Destructuring Arrays
```js
let [father, mother, son] = ["Homer", "Marge", "Bart"];
console.log(father); // Homer
console.log(mother); // Marge
console.log(son); // Bart
```

## Object Literals
```js
function newSimpson(first, last){
	//OLD: const newSimpsonObj = {firstName: first, lastName: last};
	const newSimpsonObj = {first, last};
}
```
```js
function newSimpson(simpson){
	const {first, last, age} = simpson;
	const newPerson = {first, last, age};
}
```

## For Of Loop
```js
let amounts = [10, 20, 30];
let sum = 0;

for(const amount of amounts) {
	sum += amount;
}

console.log(sum); // 60
```

## Spread Operator
```js
let numbers = [1, 2, 3, 4, 5];
let sameNumbers = [...numbers]; // new array, with same values. NOT same references.
```

```js
let person = { firstName: "Homer" }; // { firstName: "Homer" }
let person2 = { ...person }; // { firstName: "Homer" }
```

## Rest Operator
```js
function print(...words){
	console.log(words);
}

print("Yo", "Hey", "Hello"); // Yo Hey Hello
```

## Arrow Functions
NOTE: By using an arrow function, you lose the instance of **this** within the function, versus using **function()**.
```js
const numbers = [1, 2, 3, 4];
const total = numbers.reduce((accumulator, currentValue) => accumulator + currentValue);
console.log(total); // 10
```

## Default Parameters
```js
// If no parameter is passed to the sum method, then default param used.
function sum(numArray = [10, 20, 30]){
...
}
```

## Includes Method
```js
const array = [1, 2, 3];
console.log(array.includes(2)); // true
```

## Let & Const
```js
const readonlyGreeting = "Hello World";
let modifiableGreeting = "Hello World";
modifiableGreeting = "Bonjour World";
```

```js
const anArray = [1, 2, 3];
anArray.push(4); // Can push to a const array, however cannot re-assign.
let anotherArray = [1, 2, 3];
anotherArray.push(4);
anotherArray = [1, 2, 3, 4, 5];
```

## Import & Export
```js
// file1.js
export const data = 1;
```
```js
// file2.js
import { data } from "./file1.js";
console.log(data); // 1
```

```js
// file3.js
exports.getName() => { return "Bob" };
exports.getAge() => { return 50 };
```
```js
// file4.js
import { getName, getAge } from "./file3.js";
console.log(getName); // Bob
console.log(getAge); // 50
```

## PadStart & PadEnd
```js
// PadStart adds to the start of a string, until the character length is met.
let aString = "hello";
console.log(aString.padStart(10, 'a')); // aaaaahello
```
```js
// PadEbd adds to the end of a string, until the character length is met.
let aString = "hello";
console.log(aString.padEnd(10, 'a')); // helloaaaaa
```

## Classes
```js
export class Animal {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}

	function makeNoise(){
		console.log("a noise");
	}

	static function printHello(){
		console.log("Hello");
	}
}
```

```js
import { Animal } from "./animal.js";

let cat = new Animal("Tiger", 3);
cat.age = 4;
cat.makeNoise(); // a noise
```

```js
import { Animal } from "./animal.js";

Animal.printHello(); // Hello
```

```js
export class Dog extends Animal {
	function makeNoise(){
		console.log("woof");
	}
}
```

## Trailing Commas
```js
function something(param,){ // no error
...
}
```
```js
const human = { name: "Bob", }, // no error
```

## Async & Await
No more promise hell! 
`await` functions that return promises.
```js
const apiUrl = "http://...";

async function makeApiCall(){
	const response = await fetch(apiUrl);
	const responseJson = await response.json();
	console.log(json[0]); 
	// Without await, this would be executed before we have a response 
	// from the API and log null.
}
```

## Sets
```js
const exampleSet = new Set([1,1,2,2,2]);
exampleSet.add(5).add(10).add(20);
console.log(exampleSet); // [1,1,2,2,2,5,10,20]
console.log(exampleSet.has(10)); // true
console.log(exampleSet.has(7)); // false
```
