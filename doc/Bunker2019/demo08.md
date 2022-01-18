# Handling Serialization Issues and Running the App

1. Now that we have created our controllers, we are ready to run the app.

Using the **IntelliJ** IDE, find and run the `ConferenceDemoApplication.java` file in the path `src/main/java/com/pluralsight/conferencedemo/`.

```sh
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.6.2)

2022-01-12 11:56:58.184  INFO 25475 --- [           main] c.p.c.ConferenceDemoApplication          : Starting ConferenceDemoApplication using Java 1.8.0_312 on dbmacm3 with PID 25475 (/Users/dennislwm/fx-git-pull/13springcode/src/Bunker2019/conference-demo/target/classes started by dennislwm in /Users/dennislwm/fx-git-pull/13springcode/src/Bunker2019/conference-demo)
2022-01-12 11:56:58.187  INFO 25475 --- [           main] c.p.c.ConferenceDemoApplication          : No active profile set, falling back to default profiles: default
2022-01-12 11:56:59.328  INFO 25475 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data JPA repositories in DEFAULT mode.
2022-01-12 11:56:59.402  INFO 25475 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 63 ms. Found 2 JPA repository interfaces.
2022-01-12 11:57:00.364  INFO 25475 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-01-12 11:57:00.374  INFO 25475 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-01-12 11:57:00.374  INFO 25475 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.56]
2022-01-12 11:57:00.490  INFO 25475 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-01-12 11:57:00.490  INFO 25475 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 2195 ms
2022-01-12 11:57:00.876  INFO 25475 --- [           main] o.hibernate.jpa.internal.util.LogHelper  : HHH000204: Processing PersistenceUnitInfo [name: default]
2022-01-12 11:57:00.917  INFO 25475 --- [           main] org.hibernate.Version                    : HHH000412: Hibernate ORM core version 5.6.3.Final
2022-01-12 11:57:01.128  INFO 25475 --- [           main] o.hibernate.annotations.common.Version   : HCANN000001: Hibernate Commons Annotations {5.1.2.Final}
2022-01-12 11:57:01.204  INFO 25475 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Starting...
2022-01-12 11:57:01.301  INFO 25475 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Start completed.
2022-01-12 11:57:01.314  INFO 25475 --- [           main] org.hibernate.dialect.Dialect            : HHH000400: Using dialect: org.hibernate.dialect.PostgreSQLDialect
2022-01-12 11:57:01.843  INFO 25475 --- [           main] o.h.e.t.j.p.i.JtaPlatformInitiator       : HHH000490: Using JtaPlatform implementation: [org.hibernate.engine.transaction.jta.platform.internal.NoJtaPlatform]
2022-01-12 11:57:01.849  INFO 25475 --- [           main] j.LocalContainerEntityManagerFactoryBean : Initialized JPA EntityManagerFactory for persistence unit 'default'
2022-01-12 11:57:02.453  WARN 25475 --- [           main] JpaBaseConfiguration$JpaWebConfiguration : spring.jpa.open-in-view is enabled by default. Therefore, database queries may be performed during view rendering. Explicitly configure spring.jpa.open-in-view to disable this warning
2022-01-12 11:57:03.218  INFO 25475 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-01-12 11:57:03.238  INFO 25475 --- [           main] c.p.c.ConferenceDemoApplication          : Started ConferenceDemoApplication in 5.726 seconds (JVM running for 6.326)
```

2. We will now tests our JSON REST API endpoints.

Using the **Postman** app, we set our base URL to `http://localhost:8080`. First we will test our `GET` mapping for all sessions with the endpoint `/api/v1/sessions`.

```url
GET http://localhost:8080/api/v1/sessions
```

```json
[
    {
        "session_id": 1,
        "session_name": "Keynote - The Golden Age of Software",
        "session_description": "",
        "session_length": 45,
        "speakers": [
            {
                "speaker_id": 40,
                "first_name": "Simon",
                "last_name": "Williams",
                "title": "Chief Technology Officer",
                "company": "NorthernSoft Systems",
                "speaker_bio": "Test",
                "speaker_photo": null,
                "sessions": [
                    {
                        "session_id": 1,
                        "session_name": "Keynote - The Golden Age of Software",
                        "session_description": "",
                        "session_length": 45,
                        "speakers": [
                            {
                                "speaker_id": 40,
                                "first_name": "Simon",
                                "last_name": "Williams",
                                "title": "Chief Technology Officer",
                                "company": "NorthernSoft Systems",
                                "speaker_bio": "Test",
                                "speaker_photo": null,
                                "sessions": [
                                    {
                                        "session_id": 1,
                                        "session_name": "Keynote - The Golden Age of Software",
                                        "session_description": "",
                                        "session_length": 45,
                                        "speakers": [
                                            {
                                                "speaker_id": 40,
                                                "first_name": "Simon",
                                                "last_name": "Williams",
                                                "title": "Chief Technology Officer",
                                                "company": "NorthernSoft Systems",
                                                "speaker_bio": "Test",
                                                "speaker_photo": null,
                                                "sessions": [
                                                    {
...                                                          
```

The resulting payload has a lot of nested structure, which is kind of a problem. This is a serialization problem that is caused by a cyclical loop over the `ManyToMany` relationship.

3. Since we defined Session as the dominant side of the `ManyToMany` bidirectional relationship, we will add an annotation to our Speaker model to prevent back serialization.

Open the file `Speaker.java` in path `src/main/java/com/pluralsight/conference-demo/models/` and add the following lines:

```java
...
import com.fasterxml.jackson.annotation.JsonIgnore;

public class Speaker {
  ...
  @ManyToMany(mappedBy = "speakers")
  @JsonIgnore
  private List<Session> sessions;
  ...
}
```

4. Rerun the ConferenceDemoApplication, and test the GET mapping again.

```url
GET http://localhost:8080/api/v1/sessions
```

```json
[
    {
        "session_id": 1,
        "session_name": "Keynote - The Golden Age of Software",
        "session_description": "",
        "session_length": 45,
        "speakers": [
            {
                "speaker_id": 40,
                "first_name": "Simon",
                "last_name": "Williams",
                "title": "Chief Technology Officer",
                "company": "NorthernSoft Systems",
                "speaker_bio": "Test",
                "speaker_photo": null
            }
        ]
    },
    {
        "session_id": 2,
        "session_name": "A Better Way to Access Data with Spring Data",
        "session_description": "",
        "session_length": 60,
        "speakers": [
            {
                "speaker_id": 4,
                "first_name": "Lori",
                "last_name": "Vanhoose",
                "title": "Java Technical Lead",
                "company": "National Bank",
                "speaker_bio": "Test",
                "speaker_photo": null
            }
        ]
    },
    {
        "session_id": 3,
        "session_name": "A Deep Dive Into Spring IoC",
        "session_description": "",
        "session_length": 60,
        "speakers": [
            {
                "speaker_id": 5,
                "first_name": "Raymond",
                "last_name": "Hall",
                "title": "Senior Developer",
                "company": "City Power and Electric",
                "speaker_bio": "Test",
                "speaker_photo": null
            }
        ]
    },
...
```

5. We will now test our GET JSON REST API endpoints for a single `id`.

```url
GET http://localhost:8080/api/v1/sessions/4
```

```json
{
    "timestamp": "2022-01-13T03:35:23.391+00:00",
    "status": 500,
    "error": "Internal Server Error",
    "path": "/api/v1/sessions/4"
}
```

There is an error due to another serialization issue. When you have a relationship in your class, hibernate adds a few stubs to the relationship to handle lazy loading of the data.

When you try to serialize your data, you will want to ignore the stubs that are added by hibernate. There are two ways to fix this issue, either globally via `application.properties` or at the class level.

**Using the Class method**

Open the file `Session.java` in path `src/main/java/com/pluralsight/conference-demo/models/` and add the following lines:

```java
...
import com.fasterxml.jackson.annotation.JsonIgnoreProperties;

@Entity(name = "sessions")
@JsonIgnoreProperties({"hibernateLazyInitializer", "handler"})
@public class Session {
  ...
}
```

Repeat the above step for the Speaker class.

**Using the Global method**

Alternatively, we could fix this globally by modifying the `application.properties` file. Open this file in path `src/main/resources/` and add the following lines:

```properties
spring.jackson.serialization.FAIL_ON_EMPTY_BEANS=false
```

6. Retest our GET JSON REST API endpoints for a single `id`.

```url
GET http://localhost:8080/api/v1/sessions/4
```

```json
{
    "session_id": 4,
    "session_name": "Building RESTful APIs with Spring Data Rest",
    "session_description": "",
    "session_length": 60,
    "speakers": [
        {
            "speaker_id": 1,
            "first_name": "Sergio",
            "last_name": "Becker",
            "title": "Senior Developer",
            "company": "MicroOcean Software",
            "speaker_bio": "Test",
            "speaker_photo": null
        }
    ]
}
```

7. We will now test our create, i.e. POST JSON REST API endpoint passing a raw JSON body.

```url
POST http://localhost:8080/api/v1/sessions
```

```json
{
  "session_name": "Dan's Great Session Extravaganza",
  "session_description": "This will be the best conference session you might attend.",
  "session_length": 45
}
```

```json
{
    "session_id": 93,
    "session_name": "Dan's Great Session Extravaganza",
    "session_description": "This will be the best conference session you might attend.",
    "session_length": 45,
    "speakers": null
}
```

8. We will now test our update, i.e. PUT JSON REST API endpoint passing a raw JSON body.


```url
PUT http://localhost:8080/api/v1/sessions/93
```

```json
{
  "session_name": "Updated Session Name",
  "session_description": "My new description.",
  "session_length": 55
}
```

```json
{
    "session_id": 93,
    "session_name": "Updated Session Name",
    "session_description": "My new description.",
    "session_length": 55,
    "speakers": null
}
```

9. Finally, we can test our delete, i.e. DELETE JSON REST API endpoint passing an `id`.

```url
DELETE http://localhost:8080/api/v1/sessions/93
```

> Note: There is no response, except for the HTTP Status. A `200` code indicates a successful delete.