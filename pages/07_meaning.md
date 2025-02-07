---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="3">
    of
    <span v-mark.highlight.yellow=3>Meaning</span> 
  </span>
</h1>

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
```js {all|3,6|all}
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

```js {all|1,4,7}
// how can be solved?
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

```js {1-3,7,10}
// Introduce meaningful constants/enums
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
<p v-click>
    It occurs when 2+ components must
    <span v-mark.mark.yellow=1>agree</span> 
    <br>
    on the
    <span v-mark.mark.yellow=1>meaning</span>
    of a specific
    <span v-mark.mark.yellow=1>value</span>
    (convention).
</p>
<br>
<p v-click>
    Even if it is
    <span v-mark.yellow=2>not strong</span>,
    it is 
    <span v-mark.yellow=2>common</span>
    and
    <br>
    <span v-mark.yellow=2>hard to find on debugging</span>.
</p>
<br>
<p v-click>
  Can be solved
  by making 
  <span v-mark.mark.green=3>convention clear</span>,
  <br>
  with the help of
  <span v-mark.mark.green=3>constants</span>
  or
  <span v-mark.mark.green=3>enums</span>.
</p>

::right::

<Scale :l1=true :l2=true :l3=true :l5=true :l8=true />

