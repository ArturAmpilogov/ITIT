# Description

Minimize code writing for boolean logic check on emptyness or zeroness.

# Solution method

Embed in the language implicit conversion to boolean

# Examples

```javascript

let a = undefiend;
let b = null;
let c = 0;

// Usual check:
if (a === undeifined || a === null ||
    b === undefined || b === null ||
    c === 0) {
    
}

// Shortened version in JS:
if (!a || !b || !c) {
  
}

```
