# javascript
my notes from codeacademy

## Empty user name
```
let defaultName;
if (username) {
  defaultName = username;
} else {
  defaultName = 'Stranger';
}
//Equals
let defaultName = username || 'Stranger'; //?:

```
Truthy and falsy evaluations open a world of short-hand possibilities!

Say you have a website and want to take a user’s username to make a personalized greeting. Sometimes, the user does not have an account, making the username variable falsy. The code below checks if username is defined and assigns a default string if it is not:

## Ternary operator
```
isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');
```

## Default param in function
```
function greeting (name = 'stranger') {
  console.log(`Hello, ${name}!`)
}
```
## Arrow function
```
const squareNum = (num) => {
  return num * num;
};
//equals
const squareNum = num => num * num;
```
## Scope pollution, good scoping
```
const logSkyColor = () => {
  const dusk = true; //important
  let color = 'blue'; 
  if (dusk) {
    let color = 'pink';
    console.log(color); // pink
  }
  console.log(color); // blue 
};

console.log(color); // ReferenceError
```
Block scope is a powerful tool in JavaScript, since it allows us to define variables with precision, and not pollute the global namespace. If a variable does not need to exist outside a block— it shouldn’t! 

## Push is akward
```
const itemTracker = ['item 0', 'item 1', 'item 2'];

itemTracker.push('item 3', 'item 4');

console.log(itemTracker); 
// Output: ['item 0', 'item 1', 'item 2', 'item 3', 'item 4'];
```
## arrays
Some arrays methods that are available to JavaScript developers include: .join(), .slice(), .splice(), .shift(), .unshift(), and .concat() amongst many others. Using these built-in methods make it easier to do some common tasks when working with arrays. 

## Map
```
const numbers = [1, 2, 3, 4, 5]; 

const bigNumbers = numbers.map(number => {
  return number * 10;
});
```
## Reduce
While we have this code set up, let’s also check what happens if you add a second argument to .reduce(). The second argument acts as an initial value for the accumulator.

Add a second argument of 10 to .reduce().
```
const newNumbers = [1, 3, 5, 7];

const newSum = newNumbers.reduce((accumulator, currentValue) => {
	console.log('The value of accumulator: ', accumulator);
  console.log('The value of currentValue: ', currentValue);
  return accumulator + currentValue
}, 10)
console.log(newSum)
```

## Objects
You can acces Object's properties using dot or bracket notation.
### Bracket notation
```
let returnAnyProp = (objectName, propName) => objectName[propName];

returnAnyProp(spaceship, 'homePlanet'); // Returns 'Earth'
```
If we tried to write our returnAnyProp() function with dot notation (objectName.propName) the computer would look for a key of 'propName' on our object and not the value of the propName parameter. 
### Delete property
```
const spaceship = {
  'Fuel Type': 'Turbo Fuel',
  homePlanet: 'Earth',
  mission: 'Explore the universe' 
};

delete spaceship.mission;  // Removes the mission property
```
### Object's method
```
const alienShip = {
  invade () { 
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
alienShip.invade() 
```
### Passed by refference
Objects are passed to the function by a refference, so function mutates them.
```
const spaceship = {
  homePlanet : 'Earth',
  color : 'silver'
};

let paintIt = obj => {
  obj.color = 'glorious gold'
};

paintIt(spaceship);

spaceship.color // Returns 'glorious gold'

```
But this does not work in the case of redeclaration of the object! [link](https://discuss.codecademy.com/t/about-pass-by-reference-in-javascript/363663)

### Arrow function and objects
```
const goat = {
  dietType: 'herbivore',
  makeSound() {
    console.log('baaa');
  },
  diet: () => {
    console.log(this.dietType);
  }
};

goat.diet(); // Prints undefined
```
Arrow functions inherently bind, or tie, an already defined this value to the function itself that is NOT the calling object. In the code snippet above, the value of this is the global object, or an object that exists in the global scope, which doesn’t have a dietType property and therefore returns undefined. 

The key takeaway from the example above is to avoid using arrow functions when using this in a method! 

[global object](https://developer.mozilla.org/en-US/docs/Glossary/Global_object)
[arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)	
### Privacy
JavaScript does not have any mechanism to prevent developers to change private properties. the convention is using `_` at the begining of the property so everybody knows they should not change the property.
```
const bankAccount = {
  _amount: 1000
}
```
### Factory 
```
const monsterFactory = (name, age) => {
  return { 
    name: name,
    age: age
  }
};
//EQUALS ( property value shorthand )	
const monsterFactory = (name, age) => {
  return { 
    name,
    age 
  }
};
```
### Destructured assignment 
```
const residence = vampire.residence; 
console.log(residence); // Prints 'Transylvania' 
//EQUALS
const { residence } = vampire; 
console.log(residence); // Prints 'Transylvania'
```
### Create new object from 2 other
[link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)

## Browser compatibility
[caniuse](https://caniuse.com/#search=var)

### Babel
transpiles ES6 code to ES5
```
npm install babel-cli
npm install babel-preset-env
```

## Modules

```
let Menu = {};
Menu.specialty = "Roasted Beet Burger with Mint Sauce";

module.exports = Menu; 
```
in different file, load it with `const Airplane = require('./1-airplane.js')`

## Async
```
const inventory = {
  sunglasses: 1900,
  pants: 1088,
  bags: 1344
};

function myExecutor(resolve, reject) {
  if (inventory.sunglasses > 0){
    resolve('Sunglasses order processed.')
  }else{
    reject('That item is sold out.')
  }
}

function orderSunglasses(){
  return new Promise(myExecutor)
}
let orderPromise = orderSunglasses()
console.log(orderPromise)
```
