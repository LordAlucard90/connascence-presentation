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
  A cohesive <strong>class</strong> has no members that relate the class with 
  other objects that has not connection with the semantic of the class itself.
</p>
<p v-click>
  A cohesive <strong>method</strong> doesn't perform operations that have 
  different functions or responsibilities.
</p>
<p v-click>
  Not grouped together just because:
  <br> - Output of one is needed as input of another
  <br> - Same execution time (create/destroy)
  <br> - Same type of input/output
  <br> - etc..
</p>

<strong v-click>
If I change element A.1,
<br>
do I have to change all other sub-elements A.2-N?
</strong>

