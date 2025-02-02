---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="2">
    of
    <span v-mark.highlight.orange=2>Identity</span> 
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

```java {all|4-6,10|all}
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

---
layout: two-cols-header
---


# Connascence of Identity

::left::


<br>
<br>
<p>
  <span v-click="1">
    It occurs when 2+ components must
    <span v-mark.box.red=1>refer</span> 
    to a 
    <span v-mark.box.red=1>particular instance</span> 
    of another entity to work 
    <span v-mark.box.red=1>correctly</span> .
  </span>
  <br>
  <br>
  <span v-click="2">
    It is the
    <span v-mark.red=2>strongest</span>,
    form of connascence in 
    <span v-mark.red=2>code</span>,
    <br>
    it only produces errors under
    <span v-mark.red=2>certain conditions</span>
    that depend on the 
    <span v-mark.red=2>creation context</span>.
  </span>
</p>
<br>
<p v-click="3">
  To solve it, can be necessary to use an 
  <span v-mark.mark.green=3>external context</span>
  or use some mechanism to 
  <span v-mark.mark.green=3>ensure the correctness</span>
  of the current one.
</p>

::right::

<Scale 
  :l1=true :l2=true :l3=true :l4=true :l5=true
  :l6=true :l7=true :l8=true :l9=true />

<!-- FIXME: add proper timing -->




