---
layout: two-cols-header
---

# Connascence



<h3 v-click="2">
  Connascence of 
  <span  v-click="3" v-mark.highlight.orange=3>Value</span> 
</h3>

::left::

````md magic-move {lines: true}
```java {all}
public class Time {
  private int _hour;
  private int _minute;
  private int _second;
  
  public Time(int hour, int minute, int second) {
    _hour = hour;
    _minute = minute;
    _second = second;
  }
}

// usage:
var time = new Time(12, 24, 42);
```

```java {13-14|all|all}
public class Time {
  private int _hour;
  private int _minute;
  private int _second;
  
  public Time(int hour, int minute, int second) {
    _hour = hour;
    _minute = minute;
    _second = second;
  }
}
// what now?
var time = new Time(42, 87, -23);
```

```java {all}
public class Time {
  private int _hour;
  private int _minute;
  private int _second;
  
  public Time(int hour, int minute, int second) {
    _hour = hour;
    _minute = minute;
    _second = second;
    if(!isTimeValid()) {
      throw new TimeNotValidException();
    }
  }
  private boolead isTimeValid(){
    // validate data correctness
  }
}
// now an exception is thrown
var time = new Time(42, 87, -23);
```
````

::right::

````md magic-move {lines: true}
```java {all}
// second example
```

```java {all}
public class Trinagle {
  private double _sideA;
  private double _sideB;
  private double _sideC;
  
  public Trinagle(double sideA,
                  double sideB,
                  double sideC) {
    _sideA = sideA;
    _sideB = sideB;
    _sideC = sideC;
  }
}
// usage
var triangle = new Trinagle(3, 4, 5);
```

```java {14-16}
public class Trinagle {
  private double _sideA;
  private double _sideB;
  private double _sideC;
  
  public Trinagle(double sideA,
                  double sideB,
                  double sideC) {
    _sideA = sideA;
    _sideB = sideB;
    _sideC = sideC;
  }
}
// is this triangle valid?
var triangle = new Trinagle(1, 1, 3);
```

```java {all}
public class Trinagle {
  private double _sideA;
  private double _sideB;
  private double _sideC;
  
  public Trinagle(double sideA,
                  double sideB,
                  double angle) {
    _sideA = sideA;
    _sideB = sideB;
    _sideC = calcualateSide(sideA, sideB, angle)
  }
  private double calcualateSide(/* ... */) {
    // validate angle and calculate last side
  }
}
// easier to insert valid data
var trinagle = new Trinagle(1, 1, 0.5);
```
````


---
layout: two-cols-header
---


# Connascence of Value

::left::


<br>
<br>
<br>
<p>
  <span v-click="1">
    It occurs when multiple values are 
    <span v-mark.box.orange=2>related</span> 
    <br>
    and have a range of
    <span v-mark.box.orange=2>validity</span>
  </span>
  <br>
  <span v-click="3">
    that is 
    <span v-mark.circle.orange=4>not expressed </span>
    by their
    <span v-mark.circle.orange=4>primitives types</span>.
  </span>
</p>
<br>
<br>
<p>
  <span v-click="5">
    Can be solved
    <span v-mark.mark.green=6>validating</span>
    the input values
  </span>
  <br>
  <span v-click="7">
    or by 
    <span v-mark.mark.green=8>calculating</span>
    the dependent values.
  </span>
</p>

::right::

<Scale :l1=true :l2=true :l5=true :l8=true />

<!-- FIXME: add proper timing -->
