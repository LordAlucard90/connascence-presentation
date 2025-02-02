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
```js {all|7-8,12-13|7-8,12-13}
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
```js {16-20}
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
<p>
  <span v-click="1">
    It occurs when 2+ components must 
    <span v-mark.box.yellow=2>agree</span> 
  </span>
  <span v-click="3">
    <br>
    on using a
    <span v-mark.box.yellow=4>specific algorithm</span>.
  </span>
  <br>
  <br>
  <span v-click="5">
    An example is the 
    <span v-mark.yellow=6>checksum</span>
    of a file,
    <br>
    it must be used the
    <span v-mark.yellow=6>same algorithm</span>
    <br>(locally and remotely).
  </span>
</p>
<br>
<p v-click="7">
  Can be solved by correctly appling the
  <br>
  <span v-mark.mark.green=8>Don't Repeat Yourself</span>
  principle.
</p>

::right::

<Scale :l1=true :l2=true :l3=true :l4=true :l5=true :l8=true />

<!-- FIXME: add proper timing -->

