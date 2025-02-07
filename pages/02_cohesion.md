---
layout: image-right
image: /troopers.jpg
---

# Cohesion

<p v-click>
A cohesive component solves a single problem, 
all its parts collaborate together to resolve it.
</p>
<p v-click>
  <span v-mark.mark.blue=2>Each member</span>
  of a cohesive class 
  <span v-mark.mark.blue=2>relates only</span>
  with elements that has a 
  <span v-mark.mark.blue=2>connection</span>
  with the
  <span v-mark.mark.blue=2>semantic of the class</span>
  itself.
</p>
<p v-click>
  A cohesive method 
  <span v-mark.mark.blue=3>doesn't perform</span>
  operations that have 
  <span v-mark.mark.blue=3>
  different functions or responsibilities.
  </span>
</p>
<p v-click>
  Elements are not together just because:
  <br> - Output of one is needed as input of another
  <br> - Same execution time (create/destroy)
  <br> - Same type of input/output
  <br> - etc..
</p>

<strong v-click>
"If I change element A.1,
<br>
do I have to change all other sub-elements A.2-N?"
</strong>

