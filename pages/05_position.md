---
layout: two-cols-header
---

<h1>
  Connascence
  <span v-click="3">
    of
    <span v-mark.highlight.yellow=3>Position</span> 
  </span>
</h1>

::left::

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

::right::


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
// to do not just move the same problem here
// -> use a builder
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


<p v-click>
  It occurs when multiple 
  <span v-mark.mark.yellow=1>component</span> 
  must be
  <br>
  <span v-mark.mark.yellow=1>adjacent</span> 
  or appear in a 
  <span v-mark.mark.yellow=1>particular order</span>.
</p>
<p v-click>
  Can be usually found in positional structures as 
  <br> <span v-mark.mark.yellow=2>arrays</span>,
  <span v-mark.mark.yellow=2>tuples</span>
  or
  <span v-mark.mark.yellow=2>lists</span>.
</p>
<br>
<p v-click>
  Can be solved by defining 
  <span v-mark.mark.green=3>custom types</span>,
  <br>
  this allows to work with
  <span v-mark.mark.green=3>expressive constructs</span>.
</p>
<p v-click>
  Another possibility
  <span v-mark.mark.green=4>encapsulation</span>,
  <br>
  this allows to 
  <span v-mark.mark.green=4>reduce the method's coupling</span>
  <br>
  (less required parameters).
</p>

::right::

<Scale :l1=true :l2=true :l5=true />

