---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="6">
    of
    <span v-mark.highlight.yellow=6>Timing</span> 
  </span>
</h1>


::left::

```java {all|1,7|1,7,10-14|1,7,10-14,16-18|1,6,11}
// production code
@AllArgsConstructor
public class TalkToExternal {
  public ExternalClient client;

  public EndData processData(InitData initData){
    var id = client.initializeData(initData);

    EndData endData;
    for (int i = 0; i < 5; i++) {
      Thread.sleep(1000);
      endData = client.fetctData(id);
      if (endData != null) { break; }
    }

    if (endData == null) {
      throw new RuntimeException("Timeout");
    }

    return endData;
  }
}
```

::right::

```java {all|1,6-7,15}
// test code
@ExtendWith(MockitoExtension.class)
public class TalkToExternalTest {
  // initialization of mock stuff

  @Test
  void givenNoData_whenFetch_thenThrowsException(){
    // given
    given(clientMock.initData(any())).willReturn(1);
    given(clientMock.fetctData(any())).willReturn(null);

    // when - then
    assertThrows(
      RuntimeException.class,
      () -> talkToExternal.processData(initDataStub)
    );
  }
}
```

---
layout: two-cols-header
---

# Connascence of Timing


::left::

````md magic-move {lines: true}
```java {all}
// production code
@AllArgsConstructor
public class TalkToExternal {
  public ExternalClient client;

  public EndData processData(InitData initData){
    var id = client.initializeData(initData);

    EndData endData;
    for (int i = 0; i < 5; i++) {
      Thread.sleep(1000);
      endData = client.fetctData(id);
      if (endData != null) { break; }
    }

    if (endData == null) {
      throw new RuntimeException("Timeout");
    }

    return endData;
  }
}
```
```java {5}
// production code
@AllArgsConstructor
public class TalkToExternal {
  public ExternalClient client;
  public Awaiter awaiter;

  public EndData processData(InitData initData){
    var id = client.initializeData(initData);

    EndData endData;
    for (int i = 0; i < 5; i++) {
      Thread.sleep(1000);
      endData = client.fetctData(id);
      if (endData != null) { break; }
    }

    if (endData == null) {
      throw new RuntimeException("Timeout");
    }

    return endData;
  }
}
```
```java {9-11|all}
// production code
@AllArgsConstructor
public class TalkToExternal {
  public ExternalClient client;
  public Awaiter awaiter;

  public EndData processData(InitData initData){
    var id = client.initializeData(initData);

    EndData endData = awaiter.await(
      5, 1000, () -> client.fetctData(id)
    )

    if (endData == null) {
      throw new RuntimeException("Timeout");
    }

    return endData;
  }
}
```
````

::right::

````md magic-move {lines: true}
```java {all}
// test code
@ExtendWith(MockitoExtension.class)
public class TalkToExternalTest {
  // initialization of mock stuff

  @Test
  void givenNoData_whenFetch_thenThrowsException(){
    // given
    given(clientMock.initData(any())).willReturn(1);
    given(clientMock.fetctData(any())).willReturn(null);

    // when - then
    assertThrows(
      RuntimeException.class,
      () -> talkToExternal.processData(initDataStub)
    );
  }
}
```
```java {10-11|all}
// test code
@ExtendWith(MockitoExtension.class)
public class TalkToExternalTest {
  // initialization of mock stuff

  @Test
  void givenNoData_whenFetch_thenThrowsException(){
    // given
    given(clientMock.initData(any())).willReturn(1);
    given(awaiterMock.await(any(), any(), any()))
      .willReturn(null);

    // when - then
    assertThrows(
      RuntimeException.class,
      () -> talkToExternal.processData(initDataStub)
    );
  }
}
```
````

---
layout: two-cols-header
---


# Connascence of Timing

::left::


<br>
<p v-click>
  It occurs when the
  <span v-mark.mark.orange=1>success</span> 
  of 2+ call
  <span v-mark.mark.orange=1>depends</span> 
  <br>
  on the
  <span v-mark.mark.orange=1>timing</span>
  they occur.
</p>
<p v-click>
  The classic example are:
  <span v-mark.orange=2>race condition</span>,
  call to 
  <br>
  <span v-mark.orange=2>wait</span>,
  <span v-mark.orange=2>sleep</span>
  or arbitrary
  <span v-mark.orange=2>timeouts</span>.
</p>
<p v-click>
  It is 
  <span v-mark.orange=3>not possible to control time</span>,
  this can create
  <span v-mark.orange=3>intermittent problems</span>
  that are hard to 
  <span v-mark.orange=3>identify</span>
  <br>
  and 
  <span v-mark.orange=3>resolve</span>.
</p>
<br>
<p v-click>
  It
  <span v-mark.mark.yellow=4>cannot be easily solved</span>
  in the production code,
  <br>
  but it is possible to 
  <span v-mark.mark.green=4>remove it from the tests</span>.
  <br>
  They should always run in 
  <span v-mark.mark.green=4>isolation</span>
  and
  <br>
  <span v-mark.mark.green=4>as fast as possible</span>.
</p>

::right::

<Scale :l1=true :l2=true :l3=true :l4=true :l5=true :l6=true :l7=true :l8=true />

