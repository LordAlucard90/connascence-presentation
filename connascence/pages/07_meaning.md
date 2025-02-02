---
layout: two-cols-header
---

# Connascence


<h3 v-click="3">
  Connascence of 
  <span  v-click="4" v-mark.highlight.yellow=4>Meaning</span> 
</h3>

::left::

```html {all|1,3,5,7}
<input type="checkbox" name="transport" value="1"/>
I travel by bike <br/>
<input type="checkbox" name="transport" value="2"/>
I travel by car <br/>
<input type="checkbox" name="transport" value="3"/>
I travel by train <br/>
<input type="checkbox" name="transport" value="4"/>
I travel by bus <br/>
```


::right::

````md magic-move {lines: true}
```js {all|3,6|all|all}
private setTransport(String transport){
  switch(transport) {
    case "1":
      addBike(); 
      break:
    case "2":
      addBike(); 
      break:
    // etc...
  }
}
```

```js {all}
const BIKE = "1";
const CAR = "2";
// others
private setTransport(String transport){
  switch(transport) {
    case "1":
      addBike(); 
      break:
    case "2":
      addCar(); 
      break:
    // etc...
  }
}
```

```js {all}
const BIKE = "1";
const CAR = "1";
// others
private setTransport(String transport){
  switch(transport) {
    case BIKE:
      addBike(); 
      break:
    case CAR:
      addCar(); 
      break:
    // etc...
  }
}
```
````

<br>
<br>
<br>


---
layout: two-cols-header
---

# Connascence of Meaning

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
    on the
    <span v-mark.box.yellow=4>meaning</span>
    of a specific
    <span v-mark.box.yellow=4>value</span>
    (convention).
  </span>
  <br>
  <br>
  <span v-click="5">
    Even if it is
    <span v-mark.yellow=6>not strong</span>,
    <br>
    it is common and 
    <span v-mark.yellow=6>hard to find on debugging</span>.
  </span>
</p>
<br>
<p v-click="7">
  Can be solved by making convention
  <span v-mark.mark.green=8>clear</span>
  <br>
  by using
  <span v-mark.mark.green=8>constants</span>
  or
  <span v-mark.mark.green=8>enums</span>.
</p>

::right::

<Scale :l1=true :l2=true :l3=true :l5=true :l8=true />

<!-- FIXME: add proper timing -->

