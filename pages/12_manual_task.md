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

<p v-click>
  Let's immagine a service that 
  <span v-mark.mark.yellow=1>consumes messages</span>.
</p>
<p v-click>
  Each message must be 
  <span v-mark.mark.orange=2>defined</span>
  in a 
  <span v-mark.mark.orange=2>configuration</span>
  <br>
  and in the 
  <span v-mark.mark.orange=2>code</span>
  with an handler.
</p>
<p v-click>
  The connascence represented by the 
  <span v-mark.mark.green=3>configuration file</span>
  <br>
  is
  <span v-mark.mark.green=3>removed </span>
  by a service's 
  <span v-mark.mark.green=3>self-configuration</span>
  at startup.
</p>
<p v-click>
  Everything works fine
  <span v-mark.mark.green=4>locally</span>..
  <br>
  but on
  <span v-mark.mark.orange=4>integration</span>,
  it is not working anymore..
</p>
<p>
  <span v-click>
  After a lot of researches ..
  </span>
  <span v-click>
    in the
    <span v-mark.mark.orange=6>
      deployment script
    </span>..
  </span>
  <br>
  <span v-click>
    there is an
    <span v-mark.mark.red=7>
    extra step to create the subscription
    </span>
     😖
  </span>
</p>
<p v-click="9">
  The 
  <span v-mark.mirk.red=9>locality</span> 
  of this connascence is
  <span v-mark.mirk.red=9> far away</span>
  from code.
</p>
<p v-click="10">
  It can be solve 
  <span v-mark.mirk.green=10>increasing </span>
  the level of
  <span v-mark.mirk.green=10>automation</span>.
</p>

::right::

<Scale v-click="8" 
  :l1=true :l2=true :l3=true :l4=true :l5=true 
  :l6=true :l7=true :l8=true :l9=true :l10=true />

