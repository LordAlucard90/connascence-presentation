---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="2">
    of
    <span v-mark.highlight.orange=2>Value</span> 
  </span>
</h1>

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

```java {6,12-13|all}
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
  }
}
// ideas for the solution?
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
// ideas for solutions?
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
<p v-click>
  It occurs when multiple 
  <span v-mark.mark.orange=1>values</span> 
  are 
  <span v-mark.mark.orange=1>related</span> 
  <br>
  and/or have a 
  <span v-mark.mark.orange=1>range of validity</span>
  that is 
  <br>
  <span v-mark.mark.orange=1>not expressed </span>
  by their
  <span v-mark.mark.orange=1>primitives types</span>.
</p>
<br>
<br>
<p v-click>
  Can be solved by
  <span v-mark.mark.green=2>validating</span>
  the input values
  <br>
  or by 
  <span v-mark.mark.green=2>calculating</span>
  the dependent values.
</p>

::right::

<Scale :l1=true :l2=true :l5=true :l8=true />

