---
layout: two-cols-header
---

# Connascence

::left::

<br>
<br>
<br>
<br>
<br>
<br>

<h3 v-click="4">
  Connascence of 
  <span  v-click="4" v-mark.highlight.yellow=5>Position</span> 
</h3>

::right::

<br>

````md magic-move {lines: true}
```java {all|6-8,18}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(String recipient,
                        String sender,
                        String message) {
    var email = new Email();
    email.setTo(recipient);
    email.setFrom(sender);
    email.setBody(message);
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(recipient, sender, message);
```

```java {6-8,18}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(String recipient,
                        String sender,
                        String message) {
    var email = new Email();
    email.setTo(recipient);
    email.setFrom(sender);
    email.setBody(message);
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(sender, message, recipient);
```

```java {6-8,18}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(String recipient,
                        String sender,
                        String message) {
    var email = new Email();
    email.setTo(recipient);
    email.setFrom(sender);
    email.setBody(message);
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(message, recipient, sender);
```

```java {all}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(String recipient,
                        String sender,
                        String message) {
    var email = new Email();
    email.setTo(recipient);
    email.setFrom(sender);
    email.setBody(message);
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(recipient, sender, message);
```
````

<br>
<br>
<br>


---
layout: two-cols-header
---

# Connascence of Position

::left::

````md magic-move {lines: true}
```java {all} // [!code hl]
// ideas for solutions?
```

```java {all}
// encapsulate primitives
```

```java {all}
// encapsulate primitives
public record Recipient(
  String address
) {
}

public record Sender(
  String address
) {
}

public record Message(
  String content
) {
}
```
````



::right::


````md magic-move {lines: true}
```java {all}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(String recipient,
                        String sender,
                        String message) {
    var email = new Email();
    email.setTo(recipient);
    email.setFrom(sender);
    email.setBody(message);
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(recipient, sender, message);
```

```java {all}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(Recipient recipient,
                        Sender sender,
                        Message message) {
    var email = new Email();
    email.setTo(recipient.address);
    email.setFrom(sender.address);
    email.setBody(message.content);
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(recipient, sender, message);
```
````

---
layout: two-cols-header
---

# Connascence of Position

::left::

````md magic-move {lines: true}
```java {all} // [!code hl]
// other solutions?
```

```java {all}
// encapsulate primitives inside a single class
```

```java {all}
// encapsulate primitives inside a single class
public record Notification(
  String recipient,
  String sender,
  String message
) {
}
```

```java {all}
// encapsulate primitives inside a single class
// to do not just have the same problem here use a builder
@Builder
public record Notification(
  String recipient,
  String sender,
  String message
) {
}

// client
final var notification = Notification.builder()
    .recipient(recipient)
    .sender(sender)
    .message(message)
    .build9);
```
````

<br>
<br>
<br>


::right::


````md magic-move {lines: true}
```java {all}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(String recipient,
                        String sender,
                        String message) {
    var email = new Email();
    email.setTo(recipient);
    email.setFrom(sender);
    email.setBody(message);
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(recipient, sender, message);
```

```java {all}
@Service
@RequiredArgsConstructor
public class NotificationService {
  private final SmtpService smtpService;
  
  public void sendEmail(Notification notification) {
    var email = new Email();
    email.setTo(notification.recipient());
    email.setFrom(notification.sender());
    email.setBody(notification.message());
    smtpService.sendEmail(email);
  }
}

// client
notificationService.sendEmail(notification);
```
````

---
layout: two-cols-header
---


# Connascence of Position

::left::


<p v-click="1">
  It occurs when multiple component must be
  <br>
  <span v-mark.box.yellow=2>adjacent</span> 
  or appear in a particular 
  <span v-mark.box.yellow=2>order</span>.
</p>
<p v-click="3">
  Can be usually found in positional structures as 
  <br> <span v-mark.circle.yellow=4>arrays</span>,
  <span v-mark.circle.yellow=4>tuples</span>
  or
  <span v-mark.circle.yellow=4>lists</span>.
</p>
<br>
<p v-click="5">
  Can be solved by defining 
  <span v-mark.mark.green=6>custom types</span>,
  <br>
  this allows to work with
  <span v-mark.mark.green=4>expressive constructs</span>.
</p>
<p v-click="7">
  Another possibility
  <span v-mark.mark.green=8>encapsulation</span>,
  <br>
  this allows to 
  <span v-mark.mark.green=8>reduce the method's coupling</span>
  <br>
  (less required parameters).
</p>

::right::

<Scale :l1=true :l2=true :l5=true />

<!-- FIXME: add proper timing -->
