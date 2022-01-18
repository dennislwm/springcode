# Connecting to the Database

1. Add a starter dependency that will include both the **Spring Data JPA** and **PostgreSQL**  libraries.

Open the `pom.xml` file in path `src/Bunker2019/conference-demo/` and add the following lines:

```xml
<dependencies>
...
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
        <groupId>org.postgresql</groupId>
        <artifactId>postgresql</artifactId>
        <scope>runtime</scope>
    </dependency>
...
</dependencies>
```

2. Connect Spring Data JPA to Postgres.

Open the `application.properties` file in path `src/main/resources/` and add the following lines:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/conference_app
spring.datasource.username=postgres
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.hibernate.ddl-auto=none
spring.jpa.hibernate.show-sql=true
```