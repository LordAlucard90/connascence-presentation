---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="3">
    of
    <span v-mark.highlight.yellow=3>Execution Order</span> 
  </span>
</h1>


::left::

````md magic-move {lines: true}
```java {all|7-10}
@RequiredArgsConstructor
class BillingService {
  public void createAndSendBill(Vendor vendor,
                                Order order,
                                Cosutmer costumer) {
    var bill = new BillBuilder()
          .vendor(vendor)
          .order(order)
          .costumer(costumer)
          .pdf()
          .build();
    sendBill(bill);
  }
}
```
```java {7-10}
@RequiredArgsConstructor
class BillingService {
  public void createAndSendBill(Vendor vendor,
                                Order order,
                                Cosutmer costumer) {
    var bill = new BillBuilder()
          .pdf()
          .costumer(costumer)
          .order(order)
          .vendor(vendor)
          .build();
    sendBill(bill);
  }
}
```

```java {all}
@RequiredArgsConstructor
class BillingService {
  public void createAndSendBill(Vendor vendor,
                                Order order,
                                Cosutmer costumer) {
    var bill = new BillBuilder()
          .pdf()
          .costumer(costumer)
          .order(order)
          .vendor(vendor)
          .build();
    sendBill(bill);
  }
}
```

```java {all}
@RequiredArgsConstructor
class BillingService {
  public void createAndSendBill(Vendor vendor,
                                Order order,
                                Cosutmer costumer) {
    // how can be solved?
    var bill = new BillBuilder()
          .pdf()
          .costumer(costumer)
          .order(order)
          .vendor(vendor)
          .build();
    sendBill(bill);
  }
}
```
```java {6-7}
@RequiredArgsConstructor
class BillingService {
  public void createAndSendBill(Vendor vendor,
                                Order order,
                                Cosutmer costumer) {
    // improve the builder implementation
    var bill = new BillBuilderImpl()
          .vendor(vendor)
          .order(order)
          .costumer(costumer)
          .pdf()
          .build();
    sendBill(bill);
  }
}
```
````
<br>
<br>
<br>
<br>


::right::

````md magic-move {lines: true}
```java {all}
public class BillBuilder {
  BillBuilder vendor(vendor) { /* ... */ }
  BillBuilder order(order) { /* ... */ }
  BillBuilder costumer(costumer) { /* ... */ }
  BillBuilder pdf() { /* ... */ }
  Bill build() { /* ... */ }
}
```
```java {all}
public class BillBuilderImpl implements BillBuilder {
  // ...
}
public interface BillBuilder {
  BillBuilder vendor(vendor);
  BillBuilder order(order);
  BillBuilder costumer(costumer);
  BillBuilder pdf();
  Bill build();
}
```

```java {all}
public class BillBuilderImpl implements /* ... */ {
  // ...
}
public interface BillVendorBuilder {
  BillOrderBuilder vendor(vendor);
}
public interface BillOrderBuilder {
  BillCostumerBuilder order(order);
}
public interface BillCostumerBuilder {
  BillPdfBuilder costumer(costumer);
}
public interface BillPdfBuilder {
  BillBuilder pdf();
}
public interface BillBuilder {
  Bill build();
}
```

```java {all}
public class BillBuilderImpl implements 
  BillVendorBuilder,
  BillOrderBuilder,
  BillCostumerBuilder,
  BillPdfBuilder,
  BillBuilder
{
  BillOrderBuilder vendor(vendor) { /* ... */ }
  BillCostumerBuilder order(order) { /* ... */ }
  BillPdfBuilder costumer(costumer) { /* ... */ }
  BillBuilder pdf() { /* ... */ }
  Bill build() { /* ... */ }
}
```
````


---
layout: two-cols-header
---

# Connascence of Execution Order

::left::


<br>
<br>
<p v-click>
    It occurs when the
    <span v-mark.mark.yellow=1>caller</span> 
    of a component,
    <br>
    must have some 
    <span v-mark.mark.yellow=1>knowledge</span>
    <br>
    on the 
    <span v-mark.mark.yellow=1>order</span>
    of the methods to be called.
</p>
<br>
<p v-click>
    The code becomes
    <span v-mark.yellow=2>difficult to maintain</span>
    because the logic can be
    <span v-mark.yellow=2>hard to understand</span>
     just by reading it.
</p>
<br>
<p v-click>
  Can be solved with the help of a
  <span v-mark.mark.green=3>builder</span>
  <br>
  together with
  <span v-mark.mark.green=3>interface segregation</span>
  <br>
  to
  <span v-mark.mark.green=3>define</span>
  the correct
  <span v-mark.mark.green=3>order</span>.
</p>

::right::

<Scale :l1=true :l2=true :l3=true :l4=true :l5=true :l6=true :l8=true />

