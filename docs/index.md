# Initialisation du Projet

Allez vers [SPRING INITIALIZR](https://start.spring.io/)
## Gradle Config

Ajouter `org.springframework.boot:spring-boot-starter-web`
dans le fichier `build.gradle` dans la section `dependencies`

```groovy
dependencies {

	compile("org.springframework.boot:spring-boot-starter-web")
	
	implementation 'org.springframework.boot:spring-boot-starter'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```

## Notre 1ére Web Service
Créer la classe `HelloController.java` contenant le code suivant: 

```java

import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {

    @RequestMapping("/")
    public String index() {
        return "Hello World !!!";
    }
}

```

!!! info
    Vous remarquez que la réponse est sous format String,
    Comment on fait pour devenir sous format JSON ?
    
## Réponse JSON

Créer la classe `SimpleResponse.java` contenant le code suivant: 

```java

public class SimpleResponse {

    private String message;


    public SimpleResponse(String message) {
        this.message = message;
    }

    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }
}

```

Ajoutant une autre méthode nommé `indexJson()` dans notre controller:

```java
 @RequestMapping("/json")
 public SimpleResponse indexJson() {
    return new SimpleResponse("Hello World");
 }
``` 

## Tester le projet

Vous pouvez maintenant tester nos web services sur [http://localhost:8080](http://localhost:8080)

