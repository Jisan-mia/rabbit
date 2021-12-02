# rabbit

### There are 100 holes in a line, and there is a rabbit hidding in one of the holes
- you can only look in a hole at a time, and every time you look in a hole, the rabbit jumps to an adjacent hole
- find the rabbit
- a good solution find the right algorithm with the best O, bonus points for providing the exact number of worst case searces for 100 holes

#### Solution
```js


let pos = 50;
let len = 100;
console.log("The rabbit started", pos);
function step() {
  let prev = pos;
  if (pos === len) {
    pos--;
  } else if (pos === 0) {
    pos++;
  } else {
    if (Math.random() > 0.5) {
      pos++;
    } else {
      pos--;
    }
  }
  console.log("The rabbit jumped from", prev, "to", pos);
}

let found = false;

for (let i = 0; i < len; i++) {
  let attempt = i;
  console.log("Gonna check", attempt);
  if (attempt === pos) {
    found = true;
    console.log("Found the rabbit at", pos);
    break;
  }
  step();
}
if (!found) {
  for (let i = 1; i < len; i++) {
    let attempt = i;
    console.log("Gonna check", attempt);
    if (attempt === pos) {
      found = true;
      console.log("Found the rabbit at", pos);
      break;
    }
    step();
  }
}

```
