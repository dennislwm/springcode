# Working with JPA Relationships

1. The tables `speakers` and `sessions` are connected via a union or join table `session_speakers`, so we need to setup a many-to-many relationship in our Models.

Open the file `Session.java` in path `src/main/java/com/pluralsight/conference-demo/models/` and add the following lines:

```java
...
import javax.persistence.JoinColumn;
import javax.persistence.JoinTable;
import javax.persistence.ManyToMany;
import java.util.List;
...

public class Session {
    ...
    private List<Speaker> speakers;


    public List<Speaker> getSpeakers() {
        return speakers;
    }

    public void setSpeakers(List<Speaker> speakers) {
        this.speakers = speakers;
    }
    ...
}
```

2. Add annotations to the private class variable `speakers` as follows:

```java
    ...
    @ManyToMany
    @JoinTable(
        name = "session_speakers",
        joinColumns = @JoinColumn(name = "session_id"),
        inverseJoinColumns = @JoinColumn(name = "speaker_id")
    )
    private List<Speaker> speakers;
    ...
```

3. Apply the inverse many-to-many relationship in our Speaker model.

Open the file `Speaker.java` in path `src/main/java/com/pluralsight/conference-demo/models/` and add the following lines:

```java
...
import javax.persistence.ManyToMany;
import java.util.List;
...

public class Speaker {
    ...
    @ManyToMany(mappedBy = "speakers")
    private List<Session> sessions;

    public List<Session> getSessions() {
        return sessions;
    }

    public void setSessions(List<Session> sessions) {
        this.sessions = sessions;
    }
    ...
}

```