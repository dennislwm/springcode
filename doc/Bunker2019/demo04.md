# Working with Binary Data Types

1. Store the photo in field `speaker_photo`.

Open the file `Speaker.java` in path `src/main/java/com/pluralsight/conference-demo/models/` and add the following lines:

```java
...
import org.hibernate.annotations.Type;
...
import javax.persistence.Lob;
...
public class Speaker {
    ...
    
    private byte[] speaker_photo;
    ...

    public byte[] getSpeaker_photo() {
        return speaker_photo;
    }

    public void setSpeaker_photo(byte[] speaker_photo) {
        this.speaker_photo = speaker_photo;
    }    
}
```

2. Add annotations for large objects and binary type to the private class variable `speaker_photo` as follows:

```java
    ...
    @Lob
    @Type(type="org.hibernate.type.BinaryType")
    private byte[] speaker_photo;
    ...
```

3. Add a property so that the JPA can handle large objects.

Open the `application.properties` file in path `src/main/resources/` and add the following lines:

```properties
...
spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
```