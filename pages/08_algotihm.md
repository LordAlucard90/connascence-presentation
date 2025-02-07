---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="2">
    of
    <span v-mark.highlight.yellow=2>Algorithm</span> 
  </span>
</h1>

::left::


````md magic-move {lines: true}
```js {all|2-4,7-8,12-13|2-4,7-8,12-13}
/*
 * the checksum is the number that allows
 * the sum of numbers of a string 
 * become divisible by 10
*/
function addChecksum(inputData){
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return inputData + mod;
}
function validateChecksum(inputData) {
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return mod == 0;
}
```

```js {all}
/*
 * the checksum is the number that allows
 * the sum of numbers of a string 
 * become divisible by 10
*/
function addChecksum(inputData){
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return inputData + mod;
}
function validateChecksum(inputData) {
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return mod == 0;
}
// how can be solved?
```

```js {16-21}
/*
 * the checksum is the number that allows
 * the sum of numbers of a string 
 * become divisible by 10
*/
function addChecksum(inputData){
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return inputData + mod;
}
function validateChecksum(inputData) {
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return mod == 0;
}
// extract the calculation logic
function calculateChecksum(inputData) {
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return mod;
}
```

```js {7-8,11-12|all}
/*
 * the checksum is the number that allows
 * the sum of numbers of a string 
 * become divisible by 10
*/
function addChecksum(inputData){
  const checksum = calculateChecksum(inputData);
  return inputData + checksum;
}
function validateChecksum(inputData) {
  const checksum = calculateChecksum(inputData);
  return checksum == 0;
}
// extract the calculation logic
function calculateChecksum(inputData) {
  const sum = sumCharsOf(inputData);
  const mod = sum % 10;
  return mod;
}
```
````


::right::

```js {all}
// calculate checksum
addChecksum("32143") // -> 321437

// verify checksum
validateChecksum("321437") // -> true

// verify checksum
validateChecksum("321432") // -> false
```

---
layout: two-cols-header
---

# Connascence of Algorithm

::left::

<br>
<br>
<p v-click>
  It occurs when 2+ components must
  <span v-mark.mark.yellow=1>agree</span> 
  <br>
  on using a
  <span v-mark.mark.yellow=1>specific algorithm</span>.
</p>
<br>
<p v-click>
    An example is the 
    <span v-mark.yellow=2>checksum</span>
    of a file,
    <br>
    it must be used the
    <span v-mark.yellow=2>same algorithm</span>
    <br>(locally and remotely).
</p>
<br>
<p v-click>
  Can be solved by correctly appling the
  <br>
  <span v-mark.mark.green=3>Don't Repeat Yourself</span>
  principle.
</p>

::right::

<Scale :l1=true :l2=true :l3=true :l4=true :l5=true :l8=true />

