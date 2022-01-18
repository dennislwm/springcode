# Adding a Custom Application Property

1. Add custom version to application properties.

Open the `application.properties` file in path `src/main/resources/` and add the following lines:

```properties
...
app.version=1.0.0
```

2. We will create a controller to handle our JSON REST API home status endpoint.

Create a new Class file `HomeController.java` in path `src/main/java/com/pluralsight/conference-demo/controllers/` and add the following lines:

```java
package com.pluralsight.conferencedemo.controllers;

import org.springframework.beans.factory.annotation.Value;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

import java.util.HashMap;
import java.util.Map;

@RestController
@RequestMapping("/")
public class HomeController {
    @Value("${app.version}")
    private String appVersion;

    @GetMapping
    public Map get() {
        Map map = new HashMap<String, String>();
        map.put("app-version", appVersion);
        return map;
    }
}
```

3. We will now test our GET JSON REST API home status endpoint.

```url
GET http://localhost:8080/
```

```json
{
    "app-version": "1.0.0"
}
```
