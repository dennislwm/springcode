# Creating JPA Repositories

You have a couple of choices with how you want to handle your data access layer (CRUD). Spring Data JPA has benefits provided out of the box.

1. Add a JPA repository **SessionRepository** for our data access layer.

Create a new Interface file `SessionRepository.java` in path `src/main/java/com/pluralsight/conference-demo/repositories/` and add the following lines:

```java
package com.pluralsight.conferencedemo.repositories;

import com.pluralsight.conferencedemo.models.Session;
import org.springframework.data.jpa.repository.JpaRepository;

public interface SessionRepository extends JpaRepository<Session, Long> {
}
```

> Note: The second parameter of the interface is the primary key type, i.e. `session_id`.

2. Add a JPA repository **SpeakerRepository for our data access layer.

Create a new Interface file `SpeakerRepository.java` in path `src/main/java/com/pluralsight/conference-demo/repositories/` and add the following lines:

```java
package com.pluralsight.conferencedemo.repositories;

import com.pluralsight.conferencedemo.models.Speaker;
import org.springframework.data.jpa.repository.JpaRepository;

public interface SpeakerRepository extends JpaRepository<Speaker, Long> {
}
```
