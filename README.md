# Javascript Best Code Practices for Beginners

Some good code practices that help you to become better developers.

## 1. Meaningful variable name

Bad:
```
let a = 12;
```

Good: 
```
let studentAge = 12;
```

## 2. Use semicolon

Bad:
```
let age = 12
```

Good:
```
let age = 12;
```

## 3. Use strict equality
Strict equality compares the types between 2 different variables, which is more secure.

Bad:
```
if ('12' == 12) {}
// This returns true
```

Good:
```
if ('12' === 12) {}
// This returns false
```

## 4. Do not assign variable to undefined
When creating a new variable without assigning value to it, its value is default to undefined.
If you want to clear out value, use null. 

Bad:
```
var age = undefined;
```

Good:
```
var age = null;
```

## 5. Do not check for undefined
In Javascript, undefined always returns false. 


Bad:
```
var age;

if (age === undefined) {
    // run code
}
```

Good:
```
var age;

if (!age) {
    // run code
}
```

## 6. Do not use Eval
Eval function allows us to access Javascript's compiler. We can inject a piece of outside code into an application and execute it using eval, which leads to security risks. 
So, DO NOT USE EVAL 

## 7. Do not use short-hand condition
Javascript allows you to write short-hand conditions, but it looks confusing and hard to maintain readability.

Bad: 
```
    if (age > 21) canBuyBeer();
```

Good: 
```
    if (age > 21) {
        canBuyBeer();
    }
```

## 8. Declare array length outside of for loop
While looping through each array element, JS accesses the array length. By doing this, could lead to performance issue.

Bad:
```
    for (var i = 0; i < studentList.length; i++) {
        // run code
    }
```

Good:
```
    var arrayLength = studentList.length;
    for (var i = 0; i < arrayLength; i++) {
        // run code
    }
```

## 9. Do not use large condition
When you have too many conditions to check, extract it to a function. Code is cleaner and easier to read

Bad:
```
    if (person.age > 21 && person.money > 10 && person.hasID === true && person.driving === false) {
        canBuyBeer();
    }
```

Good:
```
    if (allowedToBuyBeer(person)) {
        canBuyBeer();
    }

    allowedToBuyBeer(person) {
        return person.age > 21 && person.money > 10 && person.hasID && !person.driving;
    }
```

## 10. Easy logic first in condition
Bad:
```
    var hasClass = true;

    if (studentList.indexOf('smith') !== -1 && student.length > 100 && hasClass) {
        // run code
    }
```

Good:
```
    var hasClass = true;

    if (hasClass && student.length > 100 && studentList.indexOf('smith') !== -1) {
        // run code
    }
```

