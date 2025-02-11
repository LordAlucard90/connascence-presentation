---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="9">
    of
    <span v-mark.highlight.green=9>Name</span> 
  </span>
  <span v-click="15">
    and
    <span v-mark.highlight.blue=15>Type</span> 
  </span>
</h1>

::left::

<br>
<table>
  <thead>
    <tr>
      <th><strong v-click="15" v-mark.highlight.blue="15">Type</strong></th>
      <th><strong v-click="9" v-mark.highlight.green="9">Name</strong></th>
      <th><strong v-click="15" v-mark.highlight.blue="15">Type</strong></th>
      <th><strong v-click="9" v-mark.highlight.green="9">Name</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td> <code v-click="11" v-mark.circle.blue="14">int</code> </td>
      <td> <code v-click="4" v-mark.box.green="8">_hour</code> </td>
      <td> <code v-click="13" v-mark.circle.blue="14">int</code> </td>
      <td> <code v-click="7" v-mark.box.green="8">hour</code> </td>
    </tr>
    <tr>
      <td> <code v-click="11" v-mark.circle.blue="14">int</code> </td>
      <td> <code v-click="4" v-mark.box.green="8">_minute</code> </td>
      <td> <code v-click="13" v-mark.circle.blue="14">int</code> </td>
      <td> <code v-click="7" v-mark.box.green="8">minute</code> </td>
    </tr>
    <tr>
      <td> <code v-click="11" v-mark.circle.blue="14">int</code> </td>
      <td> <code v-click="4" v-mark.box.green="8">_second</code> </td>
      <td> <code v-click="13" v-mark.circle.blue="14">int</code> </td>
      <td> <code v-click="7" v-mark.box.green="8">second</code> </td>
    </tr>
  </tbody>
</table>

::right::

```java {all|2-4|2-4,7-9|2-4,7-9,13|all|6|6-9|all|all|all|2-4|2-4|6|all}
public class Time {
  private int _hour;
  private int _minute;
  private int _second;
  
  public Time(int hour, int minute, int second) {
    _hour = hour;
    _minute = minute;
    _second = second;
  }

  public String getFormattedTime(){
    return _hour + ":" + _minute + ":" + _second
  }
}
```

<br>
<br>
<br>

<style>
tr {
  border-bottom: 0;
}
</style>


---
layout: two-cols-header
---


# Connascence of Name and Type

::left::

<p v-click>
  These two types of connascence represent the
  <span v-mark.mark.green=1>foundations</span> 
  that made a 
  <span v-mark.mark.green=1>program work</span>, 
  <br>
  they should be the 
  <span v-mark.mark.yellow=1>only types present</span>
  in the code.
</p>

<br>
<br>

<ul v-click>
  <li>
    <strong>Connascence of Name</strong>:
    <br>
    <span v-mark.green=2>Repeat the name</span> of the variables
  </li>
</ul>

<br>
<br>

<ul v-click>
  <li>
    <strong>Connascence of Type</strong>:
    <br>
    <span v-mark.green=3>Repeat the type</span> of the variables
  </li>
</ul>

::right::

<Scale :l1=true :l2=true />

