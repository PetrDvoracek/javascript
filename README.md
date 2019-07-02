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
