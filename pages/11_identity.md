---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="3">
    of
    <span v-mark.highlight.orange=3>Identity</span> 
  </span>
</h1>

::left::

```java {all}
// Let's assume it's thread safe
public class GlobalCounter {
  private int count = 0;

  public void increment() {
    count = count + 1;
  }

  public int currentCount() {
    return count;
  }
}
```
<br>
<br>
<br>

::right::

````md magic-move {lines: true}
```java {all|4-6,10}
public class Controller {
  private GlobalCounter counter;

  public Controller(GlobalCounter counter) {
    this.counter = counter;
  }

  public void someAction() {
    // perform the action
    counter.increment();
  }
}
```
```java {4-7,11}
public class Controller {
  private GlobalCounter counter;

  // the success depends on the actual instance
  public Controller(GlobalCounter counter) {
    this.counter = counter;
  }

  public void someAction() {
    // perform the action
    counter.increment();
  }
}
```
````

---
layout: two-cols-header
---


# Connascence of Identity

::left::


<br>
<br>
<p v-click>
    It occurs when 2+ components must
    <span v-mark.mark.red=1>refer</span> 
    to a 
    <span v-mark.mark.red=1>particular instance</span> 
    of another entity to work 
    <br>
    <span v-mark.mark.red=1>correctly</span> .
  </p>
  <br>
  <p v-click>
    It is the
    <span v-mark.red=2>strongest</span>,
    form of connascence in 
    <span v-mark.red=2>code</span>,
    <br>
    it only produces errors under
    <span v-mark.red=2>certain conditions</span>
    <br>
    that depend on the 
    <span v-mark.red=2>creation context</span>.
</p>
<br>
<p v-click>
  It can be necessary to use an 
  <span v-mark.mark.green=3>external context</span>
  <br>
  or use some mechanism to 
  <span v-mark.mark.green=3>ensure the correctness</span>
  <br>
  of the current one.
</p>

::right::

<Scale 
  :l1=true :l2=true :l3=true :l4=true :l5=true
  :l6=true :l7=true :l8=true :l9=true />

