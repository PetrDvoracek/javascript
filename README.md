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
