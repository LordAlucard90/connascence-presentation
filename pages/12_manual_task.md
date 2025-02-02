---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="8">
    of
    <span v-mark.highlight.orange=8>Manual Task</span> 
  </span>
</h1>


::left::

<p>
  Let's immagine a service that consumes messages.
</p>
<p v-click="1">
  Each message must be defined in a configuration
  <br>
  and in the code with an handler.
</p>
<p v-click="2">
  The connascence represented by the configuration file
  is removed by a service's self-configuration at startup.
</p>
<p v-click="3">
  Everything works fine locally..
  <br>
  <span v-click="4">
    but on integration it is not working anymore..
  </span>
</p>
<p v-click="6">
  After a lot of researches...
  <span v-click="6">
    in the deployment script..
  </span>
  <br>
  <span v-click="7">
    there is a step to create the subscription 😖
  </span>
</p>
<p v-click="9">
  The 
  <span v-mark.mirk.red=9>locality</span> 
  of this connascence is far away.
</p>
<p v-click="10">
  It can be solve increasing the level of
  <span v-mark.mirk.green=10>automation</span>.
</p>

::right::

<Scale v-click="8" 
  :l1=true :l2=true :l3=true :l4=true :l5=true 
  :l6=true :l7=true :l8=true :l9=true :l10=true />

