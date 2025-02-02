---
layout: two-cols-header
---

# Connascence

::left::

<br>
<table>
  <thead>
    <td><strong v-click="19" v-mark.highlight.blue="19">Type</strong></td>
    <td><strong v-click="12" v-mark.highlight.green="12">Name</strong></td>
    <td><strong v-click="19" v-mark.highlight.blue="19">Type</strong></td>
    <td><strong v-click="12" v-mark.highlight.green="12">Name</strong></td>
  </thead>
  <tr>
    <td> <code v-click="15" v-mark.circle.blue="18">int</code> </td>
    <td> <code v-click="4" v-mark.box.green="10">_hour</code> </td>
    <td> <code v-click="17" v-mark.circle.blue="18">int</code> </td>
    <td> <code v-click="8" v-mark.box.green="11">hour</code> </td>
  </tr>
  <tr>
    <td> <code v-click="15" v-mark.circle.blue="18">int</code> </td>
    <td> <code v-click="4" v-mark.box.green="10">_minute</code> </td>
    <td> <code v-click="17" v-mark.circle.blue="18">int</code> </td>
    <td> <code v-click="8" v-mark.box.green="11">minute</code> </td>
  </tr>
  <tr>
    <td> <code v-click="15" v-mark.circle.blue="18">int</code> </td>
    <td> <code v-click="4" v-mark.box.green="10">_second</code> </td>
    <td> <code v-click="17" v-mark.circle.blue="18">int</code> </td>
    <td> <code v-click="8" v-mark.box.green="11">second</code> </td>
  </tr>
</table>

::right::

```java {all|2-4|2-4,7-9|2-4,7-9,13|2-4,7-9,13|all|6|6-9|6-9|all|all|all|all|all|2-4|2-4|6|6|all}
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

These two types of connascence are the basics that made a program work, 
and should the only types that are present in the code.

<br>
<br>

- <strong>Connascence of Name</strong>:\
  <span v-mark.green=0>Repeat the name</span> of the variables

<br>
<br>

- <strong>Connascence of Type</strong>:\
  <span v-mark.green=0>Repeat the type</span> of the variables

::right::

<Scale :l1=true :l2=true />

<!-- FIXME: add proper timing -->
